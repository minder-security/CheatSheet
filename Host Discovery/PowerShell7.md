# NSlookup Sweep

```powershell
1..254 | ForEach-Object -Parallel {
    $ip = "192.168.0.$_"
    try {
        $dns = [System.Net.Dns]::GetHostEntry($ip)
        Write-Host "$($ip):$($dns.HostName)"
    } catch {}
} -ThrottleLimit 20
```
