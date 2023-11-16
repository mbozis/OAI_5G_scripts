# OAI_5G_scripts
Scripts and configuration files for Open Air Interface

./oaitest

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
