# Arrays
* [How to use arrays in bash script](https://linuxconfig.org/how-to-use-arrays-in-bash-script)
* [How to return an array in bash without using globals?](https://stackoverflow.com/questions/10582763/how-to-return-an-array-in-bash-without-using-globals)
* [Convert command line arguments into an array in Bash](https://stackoverflow.com/questions/12711786/convert-command-line-arguments-into-an-array-in-bash)
* [Bash: Error 'Unbound variable' when appending to empty array](http://fvue.nl/wiki/Bash:_Error_%60Unbound_variable%27_when_appending_to_empty_array)
* [Bash empty array expansion with `set -u`](https://stackoverflow.com/questions/7577052/bash-empty-array-expansion-with-set-u)

# Functions
* [How to return a string value from a Bash function](https://stackoverflow.com/questions/3236871/how-to-return-a-string-value-from-a-bash-function/38997681#38997681)
* [How do I pass a wildcard parameter to a bash file](https://stackoverflow.com/questions/19458104/how-do-i-pass-a-wildcard-parameter-to-a-bash-file)

* [How best to include other scripts?](https://stackoverflow.com/questions/192292/how-best-to-include-other-scripts)

# Variables
* [How to check if a variable is set in Bash](https://stackoverflow.com/questions/3601515/how-to-check-if-a-variable-is-set-in-bash)

Here's how to test whether a parameter is unset, or empty ("Null") or set with a value:
```
+--------------------+----------------------+-----------------+-----------------+
|   Expression       |       parameter      |     parameter   |    parameter    |
|   in script:       |   Set and Not Null   |   Set But Null  |      Unset      |
+--------------------+----------------------+-----------------+-----------------+
| ${parameter:-word} | substitute parameter | substitute word | substitute word |
| ${parameter-word}  | substitute parameter | substitute null | substitute word |
| ${parameter:=word} | substitute parameter | assign word     | assign word     |
| ${parameter=word}  | substitute parameter | substitute null | assign word     |
| ${parameter:?word} | substitute parameter | error, exit     | error, exit     |
| ${parameter?word}  | substitute parameter | substitute null | error, exit     |
| ${parameter:+word} | substitute word      | substitute null | substitute null |
| ${parameter+word}  | substitute word      | substitute word | substitute null |
+--------------------+----------------------+-----------------+-----------------+
```

### Bash script to convert from HTML entities to characters
https://stackoverflow.com/questions/5929492/bash-script-to-convert-from-html-entities-to-characters

```
cat foo.html | python3 -c 'import html, sys; [print(html.unescape(l), end="") for l in sys.stdin]'
```