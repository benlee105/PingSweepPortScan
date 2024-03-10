# PingSweepPortScan
Cmd Line Ping Sweeps and Port Scans

## Ping Sweep in CMD
```
for /L %i in (1,1,255) do @ping -n 1 -w 200 10.0.0.%i | find "TTL"
```

## Ping sweep in PowerShell
```
1..255 | % {ping -n 1 10.0.0.$_ | sls ttl}
```

## Port scan in Powershell
1..1024 | | % {echo (( new-object Net.Sockets.TcpClient.Connect("INSERT_IP_ADDR_HERE",$_)) "Port $_ is open" } 2>$null
