# OAI_5G_scripts
![](./Diagram1n.png)

Scripts and configuration files for Open Air Interface SA testbed with two hosts.

This branch contains the files for gNB and 5G core network host.
The files for the UE host are in the **master_ue** branch.

Start by installing the Open Air Interface software following the tutorial in the following link:

https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads

To pull the 2.0.1 version of OAI 5GCN containers  follow the guidelines form the following link:

https://gitlab.eurecom.fr/oai/cn5g/oai-cn5g-fed/-/blob/master/docs/RETRIEVE_OFFICIAL_IMAGES.md?ref_type=heads

Add to your /etc/hosts file the correct IP assignments for the oaiue host and 5gcn host (it is the same ip as gnbhost if gnb and core network run on the same host) . Also make any needed changes to VARIABLES SECTION in each script to be in line with your local network setup.

Scripts have been tested in Ubuntu 22.04 LTS environment. 

Use **./5gcn** to deploy core network containers, then run script **./startgnb** or **./startgnbsim** to start gNB with SDR device or RF simulator respectively. Finally run **./startue** or **./startuesim** to connect to gNB. The **./oaitest** script is for testing the interconnection of software modules and to perform measurements of throughput and RTT values. The 1.51 version of core network containers is setup with PLMN 00101 and the 2.0.1 version with 20295.

**./oaitest**

Testing tool for E2E 5G SA system using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and gNB respectively, connected to USRP N310 SDR devices.

Usage:  ./oaitest [OPTION]... [+VALUE] 

  -c, --checkue            check UE registration status to 5G Network  

  -C, --checkngi           check RAN connection to core network

  -u, --uplink [value]     create traffic to uplink. Value needs to be in bps
                           example for 30Mbps: -u 30M 
                             
  -d, --downlink [value]   create traffic to downlink. Value needs to be in bps
                           example for 30Mbps: -d 30M
                           
  -t  --time [value]      time to execute downlink and uplink tests (used with '-d' and '-u' arguments) 
                           [value] is in seconds. If not defined default value is 10
                           
  -r, --rtt                measure rtt executing ping commands in both uplink and
                           downlink
                           
  -h, --help               print this help message

  --dmax                   get downlink throughput

  --umax                   get uplink trhoughput 

**./startgnb**

Tool to start gnb softmodem for a particular scenario using USRP N310 SDR device
or 2 hosts running OAI nrUE and nrgNB respectively.

The ethernet link between the host and SDR needs to be at least 10Gbps 

Usage:  ./startgnb [OPTION]... [+VALUE] 

  -s, --scenario [value]   start gnb softmodem executing scenario number [value]
                           YOU NEED TO RUN WITH SUDO PRIVILAGES FOR "-s" OPTION
                           value is from the following table

                               ------------------------------------------------------------------
                              | 1 | standalone mode band 78 with 51prb (SISO)                    |
                              | 2 | standalone mode band 78 with 106prb (SISO)                   |
                              | 3 | standalone mode band 78 with 106prb TDD 1 slot configuration |
                              |   | with 7 DL, 2 UL, 1 FL slots, Periodicity=10 Slots (SISO)     |
                              | 4 | standalone mode band 78 with 106prb TDD 2 slot configuration |
                              |   | with 2 DL, 1 UL, 1 FL slots, Periodicity=4 Slots  (SISO)     |
                              | 5 | standalone mode band 78 with 106prb and radio packets        |
                              |   | capture with T Tracer  (SISO)                                |
                              | 6 | standalone mode band 78 with 106prb (MIMO 2x2)               |
                              | 7 | standalone mode band 78 with 133prb (MIMO 2x2)               |
                              | 8 | standalone mode band 78 with 133prb (SISO)                   |
                              | 9 | standalone mode band 78 with 162prb (SISO)                   |
                              -------------------------------------------------------------------

 -p, --plmn               PLMN selection
                                 1 (default) --> 00101
                                 2           --> 20295   

  -i, --info                 show Open Air Interface version
  -h, --help               print this help message

**./startgnbsim**

Tool to start gnb softmodem for a particular scenario using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and gNB respectively.
the ethernet link between the 2 hosts  needs to be at least 10Gbps 

Usage:  ./startgnbsim [OPTION]... [+VALUE] 

  -s, --scenario [value]   start gnb softmodem executing scenario number [value]
                           YOU NEED TO RUN WITH SUDO PRIVILAGES FOR "-s" OPTION
                           value is from the following table
                           

                           -----------------------------------------------------------------
                          | 1 | physical layer test with one slot assigned for downlink      |
                          | 2 | extended phy layer test with parameters changed              |
                          |   | (parameters need to be changed directly to script code)      |
                          | 3 | do-ra mode                                                   |
                          | 4 | standalone mode band 66                                      |
                          | 5 | standalone mode band 78 with 106prb (SISO)                   |
                          | 6 | standalone mode band 78 with 51prb  (SISO)                   |
                          | 7 | standalone mode band 77 with 273prb (2x2 MIMO)               |
                          | 8 | standalone mode band 78 with 106prb TDD 1 slot configuration |
                          |   | with 7 DL, 2 UL, 1 FL slots, Periodicity=10 Slots            |
                          | 9 | standalone mode band 78 with 106prb TDD 2 slot configuration |
                          |   | with 2 DL, 1 UL, 1 FL slots, Periodicity=4 Slots             |
                          | 10| standalone mode band 78 with 106prb and radio packets        |
                          |   | capture with T Tracer                                        |
                          | 11| standalone mode band 78 with 106prb (2x2 MIMO)               |
                          | 12| standalone mode band 78 with 133prb (2x2 MIMO)               |
                          | 13| standalone mode band 78 with 162prb (2x2 MIMO)               |     
                          | 14| standalone mode band 78 with 217prb (2x2 MIMO)               |                      
                          | 15| standalone mode band 78 with 133prb (SISO)                   |                      
                          | 16| standalone mode band 78 with 162prb (SISO)                   |      
                          | 17| standalone mode band 78 with 217prb (SISO)                   |                  
                          -------------------------------------------------------------------

 -p, --plmn               PLMN selection
                                 1 (default) --> 00101
                                 2           --> 20295  
  -o, --scope              use nr-scope tool                                    
  -i, --info               show Open Air Interface version
  -h, --help               print this help message

**./5gcn**

Tool to deploy and stop OAI Core Network containers

Usage:  ./5gcn [OPTION]... [+VALUE] 

-d, --deploy                       start 5G Core Network containers 
-s, --stop                            stop 5G Core Network containers
-v, --version [value]         specify version of containers to deploy or stop

​                                           1   version 1.51  (default)

​                                           2   version 2.0.1

​                                           example: ./5gcn -d -v 2   

  -h, --help               print this help message
