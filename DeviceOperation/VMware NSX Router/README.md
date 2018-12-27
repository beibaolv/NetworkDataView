# NSX Device Level Operation

Data Source + Key Variable + Golden Baseline + Follow up

## Show Version
To display version information for NSX Distributed Logical Router or NSX Edge Gateway.

### Data Source:
```
NSX-edge-34-1> show version 
Name:                 vShield Edge
Version:              6.2.5
Build number:         4597866
Kernel:               3.14.4
```

### Key Variable:  
* [str] Version: `6.2.5` - NSX software version.

* [int] Build number: `4597866` - NSX build number.

* [str] Kernel: `3.14.4` - NSX operation kernel version.

### Golden Baseline:

### Follow Up:  

----

## Show System Memory
To display memory information for NSX Distributed Logical Router or NSX Edge Gateway.

### Data Source:
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

### Key Variable:  
* [int] MemTotal: `503816` kB - Total memeory of NSX.

* [int] MemFree: `291516` kB - Free memeory of NSX.

* [int] MemAvailable: `379188` kB - Available memeory of NSX.

### Golden Baseline:

### Follow Up:  