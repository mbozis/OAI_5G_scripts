# OAI_5G_scripts
Scripts and configuration files for Open Air Interface

**./oaitest**

Testing tool for E2E 5G SA system using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and gNB respectively, connected to SDRs.


Usage:  ./oaitest [OPTION]... [+VALUE] 

  -c, --check              check UE registration status to 5G Network 
  
  -u, --uplink [value]     create traffic to uplink. Value needs to be in bps
                           example for 30Mbps: -u 30M
                           
  -d, --downlink [value]   create traffic to downlink. Value needs to be in bps
                           example for 30Mbps: -d 30M
                           
  -t  --time [value]       time to execute downlink and uplink tests (used with '-d' and '-u' arguments) 
                           [value] is in seconds. If not defined default value is 10
                           
  -r, --rtt                measure rtt executing ping commands in both uplink and
                           downlink
                           
  -h, --help               print this help message
  
  --dmax                   get downlink throughput
  
  --umax                   get uplink trhoughput 

**./startgnb**

Tool to start gnb softmodem for a particular scenorio using USRP N310 SDR device
or 2 hosts running OAI nrUE and nrgNB respectively.
the ethernet link between the host and SDR needs to be at least 10Gbps 

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
                          ------------------------------------------------------------------
                          
  -i, --info               show Open Air Interface version
  
  -h, --help               print this help message

  **./startue**

Tool to start UE softmodem for a particular scenorio using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and nrgNB respectively.
the ethernet link between the 2 hosts  needs to be at least 10Gbps 

Usage:  ./startue [OPTION]... [+VALUE] 

  -s, --scenario [value]   start UE softmodem executing scenario number [value]
                           YOU NEED TO RUN WITH SUDO PRIVILAGES FOR "-s" OPTION
                           value is from the following table
                           
                           -----------------------------------------------------------------
                          | 1 | standalone mode band 78 with 51prb (SISO)                     |
                          | 2 | standalone mode band 78 with 106prb  (SISO)                   |
                          | 3 | standalone mode band 78 with 106 prb TDD slot configuration 1 |
                          |   | with 7 DL, 2 UL, 1 FL slots, Periodicity=10 slots             |
                          | 4 | standalone mode band 78 with 106 prb TDD slot configuration 2 |
                          |   | with 2 DL, 1 UL, 1 FL slots, Periodicity=4 slots              |
                          | 5 | standalone mode band 78 with 106prb and radio packets         |
                          |   | capture with T Tracer                                         |
                          | 6 | standalone mode band 78 with 106prb (MIMO 2x2)                |
                          | 7 | standalone mode band 78 with 133prb (MIMO 2x2)                |
                          | 8 | standalone mode band 78 with 133prb (SISO)                    |
                          | 9 | standalone mode band 78 with 162prb (SISO)                    |
                          ------------------------------------------------------------------
                          
  -i, --info               show Open Air Interface version
  
  -h, --help               print this help message

**./startgnbsim**

Tool to start gnb softmodem for a particular scenorio using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and nrgNB respectively.
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
                          ------------------------------------------------------------------
                          
  -i, --info               show Open Air Interface version
  
  -h, --help               print this help message

  **./startuesim**

Tool to start UE softmodem for a particular scenario using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and nrgNB respectively.
the ethernet link between the 2 hosts  needs to be at least 10Gbps 

Usage:  ./startuesim [OPTION]... [+VALUE] 

  -s, --scenario [value]   start UE softmodem executing scenario number [value]
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
                          ------------------------------------------------------------------
                          
  -i, --info               show Open Air Interface version
  
  -h, --help               print this help message
