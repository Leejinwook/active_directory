# 01. Installing the Domain Controller

1. Use `sconfig` to:
    - Change the hostname
    - Change the IP address to static
    - Change the DNS server to our won IP address

2. Install the Active Directory Windows Feature

```shell
Install-WindowsFeature AD-Domain-Service -IncludeManagementTools
```



# 02. Management Server
```powershell
Start-Service WinRM
get-item wsman:\localhost\Client\TrustedHosts
set-item wsman:\localhost\Client\TrustedHosts -value 192.168.126.100

$dc = New-PSSession $ip -Credential $cred
```
