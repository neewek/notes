## tools:

[FTK Imager](https://accessdata.com/product-download/ftk-imager-version-4-2-0)

[FRedline](https://www.fireeye.com/services/freeware/redline.html)

DumpIt.exe

win32dd.exe / win64dd.exe

Offline machines - %SystemDrive%/hiberfil.sys

```
volatility -f MEMORY_FILE.raw imageinfo
```
-- figure out profile

```
volatility -f MEMORY_FILE.raw --profile=PROFILE pslist
```

-- test profile/ list processes

```
volatility -f MEMORY_FILE.raw --profile=PROFILE netscan
```

-- active network connections

```
volatility -f MEMORY_FILE.raw --profile=PROFILE psxview
```

-- view intentionally hidden processes (false = bad)

```
volatility -f MEMORY_FILE.raw --profile=PROFILE ldrmodules
```

-- greater focus on processes (false = most likely injection)

```
volatility -f MEMORY_FILE.raw --profile=PROFILE apihooks
```

-- view unexpected patches in standard DLLs (Hooking module: <unknown> = bad)

```
volatility -f MEMORY_FILE.raw --profile=PROFILE malfind -D <Destination Directory>
```
  
-- find malicious injected code

```
volatility -f MEMORY_FILE.raw --profile=PROFILE dlllist -D <Destination Directory>
```
  
-- list all DLLs in memory

```
volatility -f MEMORY_FILE.raw --profile=PROFILE --pid=PID dlldump -D <Destination Directory>
```
  
-- pull out DLLs
