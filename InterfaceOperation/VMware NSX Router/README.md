# NSX Interface Level Operation

Data Source + Key Variable + Golden Baseline + Follow up

## Show Interface
To display interfaces statistics for NSX Distributed Logical Router or NSX Edge Gateway.

### Data Source:
```
NSX-edge-34-1> show interface 
Interface vNic_0 is up, line protocol is up
  index 2 metric 1 mtu 1500 <UP,BROADCAST,RUNNING,MULTICAST>
  HWaddr: 00:50:56:93:64:a0
  inet 172.1.1.1/24 broadcast 172.1.1.255
  inet6 fe80::250:56ff:fe93:64a0/64
  proxy_arp: disabled
  Full-duplex, 10000Mb/s
    input packets 3730549, bytes 358298420, dropped 75, multicast packets 28
    input errors 0, length 0, overrun 0, CRC 0, frame 0, fifo 0, missed 0
    output packets 6303887, bytes 462326620, dropped 0
    output errors 0, aborted 0, carrier 0, fifo 0, heartbeat 0, window 0
    collisions 0
Interface vNic_4 is down
  index 3 metric 1 mtu 1500 <BROADCAST,MULTICAST>
  HWaddr: 00:50:56:93:3e:90
  proxy_arp: disabled
  Half-duplex, 0Mb/s
    input packets 0, bytes 0, dropped 0, multicast packets 0
    input errors 0, length 0, overrun 0, CRC 0, frame 0, fifo 0, missed 0
    output packets 0, bytes 0, dropped 0
    output errors 0, aborted 0, carrier 0, fifo 0, heartbeat 0, window 0
    collisions 0
```

### Key Variable:
* [table] 

   | Interface | Status | MTU | Duplex | Speed | in_bytes | in_drops | in_errors | CRC | out_bytes | out_drops | out_errors |
   | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
   | vNic_0  | up | 1500 | Full-duplex | 10000 | 358298420 | 75 | 0 | 0 | 6303887 | 0 | 0 |
   | vNic_4  | down | 1500 | Half-duplex | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

  1. [str] Interface `vNic_0` is `up`. - Interface name and operation status
  2. [int] mtu `1500` <UP,BROADCAST,RUNNING,MULTICAST> - MTU information.
  3. [str] `Full-duplex` - Interface duplex information.
  4. [int] `10000`Mb/s - Interface speed information.
  5. [int] input packets 3730549, bytes `358298420`, dropped `75` - Interface input bytes and dropp counts.
  6. [int] input errors `0`, length 0, overrun 0, CRC `0`, - Interface input errors and CRC counts.
  7. [int] output packets 6303887, bytes `462326620`, dropped `0` - Interface output bytes and drop counts.
  8. [int] output errors `0` - Interface output error counts.

### Golden Baseline:
* In-Used interfaces status should be both `up`, and None-Used interfaces should be both `administratively down` for security purpose.

* Standard MTU is **1,500** bytes, and Jumbo frames are used on local area networks that support at least 1 Gbps and can be as large as **9,000** bytes.

* Most of time the interface duplex should set `Full-duplex` have the best transmition.

* In ideal situation, the **delta** of `input errors`, `output errors` and other error/drop variables should be 0.


### Follow Up:  