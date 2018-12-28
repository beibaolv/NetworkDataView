Cisco IOS Device Level Operation
=====

## Show Processes CPU Sorted
The output shows how busy the CPU has been in the past 5 seconds, the past 1 minute, and the past 5 minutes. The output also shows the utilization percentage that each system process has used in these periods. 

### Data Parser:
```
Router#show processes cpu sorted
CPU utilization for five seconds: 0%/0%; one minute: 0%; five minutes: 0%
 PID Runtime(ms)     Invoked      uSecs   5Sec   1Min   5Min TTY Process 
  87      748392    95844227          7  0.16%  0.27%  0.28%   0 Ethernet Msec Ti 
 248      105792    15520795          6  0.08%  0.04%  0.05%   0 MMA DB TIMER     
 166        2040      305516          6  0.08%  0.00%  0.00%   0 Ethernet PM Moni 
  92      105076    15520845          6  0.08%  0.04%  0.03%   0 VRRS Main thread 
  45       21128     1073335         19  0.08%  0.01%  0.00%   0 Net Background   
  89        6508     1017125          6  0.08%  0.00%  0.00%   0 mDNS             
 193       27728     1011672         27  0.08%  0.01%  0.00%   0 ADJ background   
 374      244804    440n86817          5  0.08%  0.14%  0.13%   0 MFIB_mrib_write  
   8           0           1          0  0.00%  0.00%  0.00%   0 DiscardQ Backgro 
  10           8         201         39  0.00%  0.00%  0.00%   0 WATCH_AFS  
```
 
* CPU utilization for five seconds: `0`%/`0`%. 
  
  1.[int:5s_cpu_util] The first number tells how busy the CPU was in the past 5 seconds.
  
  2.[int:5s_cpu_hi_util] The second number shows the percentage CPU time spent servicing/handling hardware interrupts.

* [int:1min_cpu_util] one minute: `0`% - The average utilization for the last 1 minute.

* [int:5min_cpu_util] five minutes: `0`% - The average utilization for past 5 minutes.

### Data View:  

1.[device-unit] [logic:Range] **1min_cpu_util** 

### Golden Baseline:  
CPU Utilization depends on network enviroment scope / operation time, so it is various.

### Follow Up:  
The more instances running, the greater the CPU utilization. Some conditions with High CPU Utilization :
* Spanning Tree Convergence.
* IP Routing Table Updates.
* Heavy commands output, such as `debug`, `show tech`.
* HSRP flapping.


## Show Processes Memory Sort
This command is often used to check the amount of a network device free memory. Each process maintains its own heap memory, which is taken from the system memory in blocks. The process reuses this memory as required. If all the memory that was requested in a block is no longer in use, then the process can return the memory block to the system. 

### Data Parser:
```
Router#show processes memory sort
Processor Pool Total:  356640420 Used:   62461080 Free:  294179340

 PID TTY  Allocated      Freed    Holding    Getbufs    Retbufs Process
   0   0  118633760   65017296   47260744          0          0 *Init*          
 332   0    1406912      30424    1389568          0          0 EEM Server      
   0   0   11187192    7901376    1057096    1709135          0 *Dead*          
 380   0     585888       2288     490896          0          0 BGP Router      
   0   0          0          0     394848          0          0 *MallocLite*    
 206   0  243985576  235824864     338776          0          0 PIM Process     
 108   0  267416336  177109584     327624          0          0 CDP Protocol    
   1   0     298784          0     311864          0          0 Chunk Manager   
 313   0     286536       4992     298624     100548          0 EEM ED Syslog   
  38   0     266240       1664     277448          0          0 RF SCTPthread   
 275   0     260296          0     277376          0          0 QOS_MODULE_MAIN 
 279   0     201768          0     226848          0          0 VOIP_FMD_MAIN   
 314   0     211600       4992     223688      67468          0 EEM ED Generic  
 375   0     196600       1120     222648          0          0 MFIB_mrib_read  
 ```

* [int:proc_mem_total] Processor Pool Total: `356640420` - Total amount of memory, in kilobytes, held for the Processor memory pool.

* [int:proc_mem_used] Used:  `62461080` - Total amount of used memory, in kilobytes, in the Processor memory pool. 

* [int:proc_mem_free] Free: `294179340` -  Total amount of free memory, in kilobytes, in the Processor memory pool. 

### Data View:  

1.[device-unit] [logic:Range] **proc_mem_usage** =  (proc_mem_used/proc_mem_total)*100%. 

### Golden Baseline:  
Memory depends on network device / process / configuration, so it is various.
