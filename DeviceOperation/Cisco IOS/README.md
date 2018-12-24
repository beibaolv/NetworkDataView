Cisco IOS Device Level Operation
====
## CLI Output + Key Variable + Baseline Value

### show processes cpu sorted
The output shows how busy the CPU has been in the past 5 seconds, the past 1 minute, and the past 5 minutes. The output also shows the utilization percentage that each system process has used in these periods. 

```
Router#show processes cpu sorted
CPU utilization for five seconds: `0%/0%`; one minute: 0%; five minutes: 0%
 PID Runtime(ms)     Invoked      uSecs   5Sec   1Min   5Min TTY Process 
  87      748392    95844227          7  0.16%  0.27%  0.28%   0 Ethernet Msec Ti 
 248      105792    15520795          6  0.08%  0.04%  0.05%   0 MMA DB TIMER     
 166        2040      305516          6  0.08%  0.00%  0.00%   0 Ethernet PM Moni 
  92      105076    15520845          6  0.08%  0.04%  0.03%   0 VRRS Main thread 
  45       21128     1073335         19  0.08%  0.01%  0.00%   0 Net Background   
  89        6508     1017125          6  0.08%  0.00%  0.00%   0 mDNS             
 193       27728     1011672         27  0.08%  0.01%  0.00%   0 ADJ background   
 374      244804    44086817          5  0.08%  0.14%  0.13%   0 MFIB_mrib_write  
   8           0           1          0  0.00%  0.00%  0.00%   0 DiscardQ Backgro 
  10           8         201         39  0.00%  0.00%  0.00%   0 WATCH_AFS        
```
