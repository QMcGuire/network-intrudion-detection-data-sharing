## IoT & Security
Diversity and heterogeneity makes IoT systems security more crucial. IoT systems differes from traditioal systems security due to the following reasons:
- IoT systems are constrained in terms of computational capability, memory capacity, battery kife and network bandwidth. Hence it is not possible to deploy existing traditional security solutions which are often resource intensive
- IoT systems are heavilty distributed and heterogeneous. Thus, centralized traditional soltion may not be suitable. Moreover, the distributed aspect of IoT add more difficulties and constrains in their protection
- IoT systems are deployed in a physical environment which is unpredictable
- IoT systems are connected to Internet since each device has access is Ip address. Hence, there is one more panelof threats related to Internet.
- IoT systems are composed of a large number of constrained objects that generate huge amount of data. So it is easy to flood and attack these small devices on the one side and the limited bandwidth of the networks on the other side
- IoT systems cover a large number of heterogenous protocols and technologies in the system. Hence, the proposed IoT security solution must take into consideration the large panel of these protocols and technologies in the same proposal

## Datasets:
### NSL-KDD: https://www.unb.ca/cic/datasets/nsl.html
  - Advantages: a better version of KDD99, overcome KDD(( limitations, no duplicates records in the training and test sets
  - Disadvantages: lack of modern low foot print attack scenarios, not for IoT systems
 
### USNW-NB15: https://research.unsw.edu.au/projects/unsw-nb15-dataset
  - Advantages: hybrid real modern normal activities and synthetic contemporary attack behaviors, provide network traffic (PCAP) and CSV files, it has 9 types of attacks, namely Fuzzers, Analysis, Backdoors, DoS, Exploits, Generic, Reconnaissance, Shellcode and Worms
  - Disadvantages: it is more complex than the KDD99 datasets due to the similar behaviors of the modern attack and normal network traffic
### Silvanathan et al:
  - Advantage: network traffic IoT dataset, reflects real world IoT systems, povide network traffic (PCAP) and CSV files
  - Disadvantages: Unlabeled data, for IoT devices proliferation and traffic characterization, no attack data
### CICDS:https://www.stratosphereips.org/datasets-iot23
- Advantages:
  - Labeled network flows
  - For machine learning and deep learning purpose
  - Provide network traffic and CSV files
  - Implements attacks such as Brute Force FTP, Brute Forcee SSH, DoS, HeartBleed, Web Attack, Infiltration, Botnet and DDoS
- Disadvantages:
  - Not public
  - Not for IoT systems
### CIC-IDS2018
- Advantages: 
  - Labeled network flows
  - For ML and deep learning purpose
  - Implements Bruteforce, Heartblood, Botnet, DoS, DDoS, Web attacks and Local network infiltration attacks
  - Dynamicallly generated datasets
  - It is modifiable, extensible and reproducible
- Disadvantage:
  - Not public
  - Not for IoT systems


## Open-Source NIDS:
- Snort
- Suricata
- Bro-IDS tool
- Kismet
- Open WISP-ng
- Security Onion
- Sagan
## Free, Open Source Network Sniffers
- Tcpdump
- Wireshark
- Ettercap
- Argus
- EtherApe
