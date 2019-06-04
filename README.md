# BB-Gen

BB-Gen paper executável desenvolvido na disciplina IA369Z - Reprodutibilidade em Pesquisa Computacional - FEEC - Unicamp

## About BB-Gen
BB-Gen is simple CLI based packet crafter written in Python over Scapy library to generate packet flows formatted as PCAP files by taking user-defined parameters as inputs based on the headers defined in a P4<sub>14</sub> program. It can natively crafts packets for different standard and custom protocols. It aims to create PCAP files to be used with a wide set of Traffic Generators (e.g., pktgen-dpdk, NFPA, TCPDUMP, etc.) helping network developers to validate the network and execute performance tests over the targets.


## Installation  
step 1: $ `sudo apt-get install git`  
step 2: $ `git clone --recursive https://github.com/intrig-unicamp/BB-Gen.git`  
step 3: $ `cd BB-Gen`    
step 4: $ `sudo ./dependencies.py`  
step 5: $ `cd p4-hlir`    
step 6: $ `sudo python setup.py install`    
step 7: $ `cd ..`      
step 8: $ `python main.py`  

BB-Gen generates a PCAP and Trace files.
The PCAPs can be used for testing together with tools such as NFPA.
## Usage

    main.py [-h] [-p] [-t] [-n] [-nm] [-rnip] [-rnmac] [-rnport] [-pkt]
            [-p4] [-u] [-udata] [-perf] [-d] [-v]

BB-Gen PCAP generator

    optional arguments:  
    -h, --help            show this help message and exit
    -p , --protocol       Type of packet:
                           ipv4, ipv6, vxlan, gre, l2
                           Default: ipv4
    -t , --tansport       Specifies the transport protocol:
                           tcp or udp
                           For VXLAN and GRE is the encapsulated protocol
                           Default: tcp
    -n , --number         Number of entries
                           Default: 100
    -nm , --name          PCAP name
                           Default: ipv4
    -rnip                 Random IP
                           Default: False
    -rnmac                Random MAC
                           Default: False
    -rnport               Random Port
                           Default: False
    -pkt , --packetsize   Specify here the required packetsize
                           In case of more than one, separated the list with coma
                           e.g. 64,215,514.
                           Default: 64
    -p4                   Specify a P4 code to autogenerates the traces
                           Default: none
    -u , --usecase        Use Case:
                           macsad
                           Default: none
    -udata , --userdata   User Specified Data
    -perf, --performance  Performance PCAPs
                           64, 128, 254, 512, 1024, 1280, 1518 pkt size
                           Default: False
    -d, --debug           Debug enable
    -v                    show program's version number and exit

## Running BB-Gen

Designed for simplicity, BB-Gen delivers an intuitive CLI based interface. By specifying only a few flags, can be created a set of traces files.

### Examples:

Generation of 100 vxlan traces with packet size of 64B:

$ `python main.py -p vxlan -n 100`

Generation of random 1k IPv4 traces for performance test:

$ `python main.py -p ipv4 -n 1000 -rnip -rnmac -rnport --performance`

MACSAD use case:

$ `python main.py -u macsad`

Using a P4<sub>14</sub> code to autogenerate 100 traces:

$ `python main.py -p4 examples/p4_src/l3_fwd_ipv6.p4 -n 100`

## Supported Protocols:
  - Ethernet
  - IPv4 / IPv6
  - UDP
  - TCP
  - GRE
  - VXLAN
