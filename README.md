# PingSweepPortScan
Cmd Line Ping Sweeps and Port Scans

## Ping Sweep in cmd.exe
```
for /L %i in (1,1,255) do @ping -n 1 -w 200 10.0.0.%i | find "TTL"
```

## Ping Sweep in powershell.exe
Powershell window will appear inactive, just be patient.
```
1..255 | % {ping -n 1 10.0.0.$_ | sls ttl}
```

## Port Scan in powershell.exe
Note that scanning from 1 to 1024 takes a SUPER LONG TIME.
Narrow down to just a few ports instead.
```
1..1024 | % {echo ((new-object Net.Sockets.TcpClient).Connect("INSERT_IP_HERE",$_)) "Port $_ is open" } 2>$null
```
