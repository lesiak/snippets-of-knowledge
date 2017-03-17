Clean Containers:
```sh
> Get-Container | where State -eq "exited" | foreach {$_.ID; Remove-Container $_.ID}
> Get-Container | Where-Object State -eq "exited" | Remove-Container
> Get-Container | where State -eq "exited" | Remove-Container
```

Second Command:
