# NSX Device Level Operation

## Show Version
To display version information for NSX Distributed Logical Router or NSX Edge Gateway.

### Data Parser:
```
NSX-edge-34-1> show version 
Name:                 vShield Edge
Version:              6.2.5
Build number:         4597866
Kernel:               3.14.4
```

* [str:version] Version: `6.2.5` - NSX software version.

* [int:build_num] Build number: `4597866` - NSX build number.

* [str:kernel] Kernel: `3.14.4` - NSX operation kernel version.

### Data View:
1.[device-unit] [logic:Equals] **version**

2.[device-unit] [logic:Equals] **build_num**

3.[device-unit] [logic:Equals] **kernel**

### Follow Up:  

----

## Show System Memory
To display memory information for NSX Distributed Logical Router or NSX Edge Gateway.

### Data Parser:
```
NSX-edge-34-1> show system memory 
MemTotal:         503816 kB
MemFree:          291516 kB
MemAvailable:     379188 kB
Buffers:           21888 kB
Cached:            65672 kB
SwapCached:            0 kB
Active:           102276 kB
Inactive:          39588 kB
Active(anon):      56368 kB
Inactive(anon):       60 kB
```
  
* [int:mem_total] MemTotal: `503816` kB - Total memeory of NSX.

* [int:mem_free] MemFree: `291516` kB - Free memeory of NSX.

### Data View:
1.[device-unit] [logic:Range] **mem_util** = [(mem_total - mem_free)/mem_total] * 100%

### Follow Up:  