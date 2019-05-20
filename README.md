#BB-Gen

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
