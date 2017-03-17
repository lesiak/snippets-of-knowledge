Clean Containers:
```sh
> Get-Container | where Status -like 'Exited*' | foreach {$_.ID; Remove-Container $_.ID}
```

Second Command:
