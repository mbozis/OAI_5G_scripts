# OAI_5G_scripts
Scripts and configuration files for Open Air Interface. This branch is for files to be installed in oaiue host.

Scripts were tested in Ubuntu 22.04 LTS environment.

Run script **./startue** or **./startuesim** to start OAI nrUE with SDR device or RF simulator respectively.

After a successful connection of the UE to 5G netowrk you can switch your internet connection through the 5G protocol stack running the script **./switch5G** . To go back to your broadband connection run **./switchBB** script.

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

-p, --plmn               PLMN selection

​                                1 (default) --> 00101

​                                2                 --> 20295

​                                3                 --> 20895  

 -i, --info               show Open Air Interface version



  -h, --help               print this help message



​                           

  **./startuesim**

Tool to start UE softmodem for a particular scenario using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and nrgNB respectively.
the ethernet link between the 2 hosts  needs to be at least 10Gbps 

Usage:  ./startuesim [OPTION]... [+VALUE] 

  -s, --scenario [value]   start UE softmodem executing scenario number [value]
                           YOU NEED TO RUN WITH SUDO PRIVILAGES FOR "-s" OPTION
                           value is from the following table
                           

                               -------------------------------------------------------------------
                              | 1 | physical layer test with one slot assigned for downlink       |
                              | 2 | extended phy layer test with parameters changed               |
                              |   | (parameters need to be changed directly to script code)       |
                              | 3 | do-ra mode                                                    |
                              | 4 | standalone mode band 66                                       |
                              | 5 | standalone mode band 78 with 106prb (SISO)                    |
                              | 6 | standalone mode band 78 with 51prb (SISO)                     |
                              | 7 | standalone mode band 77 with 273prb (2x2 MIMO)                |
                              | 8 | standalone mode band 78 with 106 prb TDD slot configuration 1 |
                              |   | with 7 DL, 2 UL, 1 FL slots, Periodicity=10 slots             |
                              | 9 | standalone mode band 78 with 106 prb TDD slot configuration 2 |
                              |   | with 2 DL, 1 UL, 1 FL slots, Periodicity=4 slots              |
                              | 10| standalone mode band 78 with 106prb and radio packets         |
                              |   | capture with T Tracer                                         |
                              | 11| standalone mode band 78 with 106prb (2x2 MIMO)                |
                              | 12| standalone mode band 78 with 133prb (2x2 MIMO)                |
                              | 13| standalone mode band 78 with 162prb (2x2 MIMO)                |
                              | 14| standalone mode band 78 with 217prb (2x2 MIMO)                |
                              | 15| standalone mode band 78 with 133prb (SISO)                    |
                              | 16| standalone mode band 78 with 162prb (SISO)                    |
                              | 17| standalone mode band 78 with 217prb (SISO)                    |
                              --------------------------------------------------------------------

  -o, --scope              use nr-scope tool



  -p, --plmn               PLMN selection



​                                  1 (default) --> 00101

​                                  2                 --> 50501

​                                  3                 -->  20895

 -i, --info               show Open Air Interface version

 -h, --help               print this help message



**./ueconfig**

Tool to configure UE softmodem for a particular scenario using Open Air Interface SA Testbed
-the 2 hosts run OAI nrUE and nrgNB respectively.
-the ethernet link between the hosts and USRP N310 devices must be at least 10Gbps 

Usage:  ./ueconfig [OPTION]... [+VALUE] 
  -s, --scenario [value]   edit gnb softmodem configuration file for a specific scenario
                           value is from the following table

                           -------------------------------------------------------------------
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
                          --------------------------------------------------------------------



 -p, --plmn               PLMN selection

​                           1 (default) --> 00101

​                           2           --> 20295 

  -e, --editor             choose editor

​                           1 (default) --> nano

​                           2           --> gedit                                                        

  -i, --info               show Open Air Interface software version

  -h, --help               print this help message
