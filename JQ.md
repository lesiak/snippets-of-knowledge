* [Use JQ to select specific, arbitrarily nested objects from JSON](https://stackoverflow.com/questions/47891145/use-jq-to-select-specific-arbitrarily-nested-objects-from-json)

For small to modest-sized JSON input, you're on the right track with .. but it seems you want to select objects, like so:
```
.. | objects | select(.class=="FINDME"?) | .id
```
For JSON documents that are very large, this might require too much memory, so it may be worth knowing about jq's streaming parser. Unfortunately it's much more difficult to use, so I'd suggest trying the above, and if you're interested, look in the usual places for documentation about the --stream option

* [getting all the values of an array with jq](https://stackoverflow.com/questions/45523425/getting-all-the-values-of-an-array-with-jq)

Evidently one of the items in the array is a string. If your jq supports "?", then one possibility would be to use it:
```
.response[].text?
```
Another would be to check the type explicitly, e.g.:
```
.response[] | objects | .text
```
Yet another possibility:
```
.response[] | select(type=="object" and has("text")) | .text
```
If you want to have a placeholder value when there is no "text" field:
```
.response[] | if type=="object" and has("text") then .text else null end
 ```
So it really depends on your requirements and perhaps the version of jq that you are using.

Example query
```
cat rep.json| jq '.. | objects | select(.picks[]?.barcodes==[])'
```