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
                           
                           -----------------------------------------------------------------
                          | 1 | standalone mode band 78 with 51prb                         |
                          | 2 | standalone mode band 78 with 106prb                        |
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
                          | 1 | standalone mode band 78 with 51prb                         |
                          | 2 | standalone mode band 78 with 106prb                        |
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
                          | 1 | physical layer test with one slot assigned for downlink    |
                          | 2 | extended phy layer test with parameters changed            |
                          |   | (parameters need to be changed directly to script code)    |
                          | 3 | do-ra mode                                                 |
                          | 4 | standalone mode band 66                                    |
                          | 5 | standalone mode band 78 with 106prb                        |
                          | 6 | standalone mode band 78 with 51prb                         |
                          | 7 | standalone mode band 77 with 273prb (2x2 MIMO)             |
                          ------------------------------------------------------------------
                          
  -i, --info               show Open Air Interface version
  
  -h, --help               print this help message

  **./startuesim**

Tool to start UE softmodem for a particular scenorio using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and nrgNB respectively.
the ethernet link between the 2 hosts  needs to be at least 10Gbps 

Usage:  ./startuesim [OPTION]... [+VALUE] 

  -s, --scenario [value]   start UE softmodem executing scenario number [value]
                           YOU NEED TO RUN WITH SUDO PRIVILAGES FOR "-s" OPTION
                           value is from the following table
                           
                           -----------------------------------------------------------------
                          | 1 | physical layer test with one slot assigned for downlink    |
                          | 2 | extended phy layer test with parameters changed            |
                          |   | (parameters need to be changed directly to script code)    |
                          | 3 | do-ra mode                                                 |
                          | 4 | standalone mode band 66                                    |
                          | 5 | standalone mode band 78 with 106prb                        |
                          | 6 | standalone mode band 78 with 51prb                         |
                          | 7 | standalone mode band 77 with 273prb (2x2 MIMO)             |
                          ------------------------------------------------------------------
                          
  -i, --info               show Open Air Interface version
  
  -h, --help               print this help message
