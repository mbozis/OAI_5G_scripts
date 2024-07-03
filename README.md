# OAI_5G_scripts
Scripts and configuration files for Open Air Interface. This branch is for files to be installed in oaiue host.

To explore the use cases and measurements performed with  this testbed you can read the paper "A Versatile 5G Standalone Testbed  Based On Commodity Hardware" under the following link

https://ieeexplore.ieee.org/document/10497086

This branch contains the files for UE host. The files for the gNB host are in the **master_gnb** branch.

Scripts were tested in Ubuntu 22.04 LTS environment.

Before running the scripts, you need to make all necessary changes to environment variables stored in **ueconfig.ini** file to match you network setup.  The values of those variables will be imported from scripts at runtime.

Run script **./startue** or **./startuesim** to start OAI nrUE with SDR device or RF simulator respectively.

After a successful connection of the UE to 5G netowrk you can switch your internet connection through the 5G protocol stack running the script **./switch5G** . To go back to your broadband connection run **./switchBB** script.

  **./startue**

Tool to start UE softmodem for a particular scenorio using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and nrgNB respectively.
the ethernet link between the 2 hosts  needs to be at least 10Gbps 

Usage:  ./startue [OPTION]... [+VALUE] 

  -s, --scenario [value]   start UE softmodem executing scenario number [value]
                           
                               ------------------------------------------------------------------
                              | 1 | standalone mode band 78 with 24prb  (SISO)                   |                                
                              | 2 | standalone mode band 78 with 51prb  (SISO)                   |                          
                              | 3 | standalone mode band 78 with 106prb (SISO)                   |
                              | 4 | standalone mode band 78 with 133prb (SISO)                   |                      
                              | 5 | standalone mode band 78 with 162prb (SISO)                   |      
                              | 6 | standalone mode band 78 with 217prb (SISO)                   |  
                              | 7 | standalone mode band 77 with 273prb (SISO)                   |   
                              | 8 | standalone mode band 78 with 106prb TDD 1 slot configuration |
                              |   | with 7 DL, 2 UL, 1 FL slots, Periodicity=10 Slots            |
                              | 9 | standalone mode band 78 with 106prb TDD 2 slot configuration |
                              |   | with 2 DL, 1 UL, 1 FL slots, Periodicity=4 Slots             |                     
                              | 10| standalone mode band 78 with 106prb (2x2 MIMO)               |
                              | 11| standalone mode band 78 with 133prb (2x2 MIMO)               |
                              | 12| standalone mode band 78 with 162prb (2x2 MIMO)               |     
                              | 13| standalone mode band 78 with 217prb (2x2 MIMO)               |  
                              | 14| standalone mode band 77 with 273prb (2x2 MIMO)               |
                              | 15| standalone mode band 66 with 106prb (SISO,FDD)               |        
                              -------------------------------------------------------------------

  -p, --plmn               PLMN selection

​                           1 (default) --> 00101

​                           2           --> 50501

​                           3           --> 20295 

  -i, --info               show Open Air Interface version

  -l, --log                write nr-uesoftmodem output to a log file with date and time stamp in scripts/logs folder

  -o, --scope              use nr-scope tool 

  -c, --command_line       exit script, copy selected scenario command to file COMMAND in current folder

​                           and start a new terminal in OAI binaries folder. 

​                           -To view command before executing it type cat COMMAND in the command line. 

​                           -To start gNB softmodem copy and paste command to new terminal window in OAI binaries folder

​                           To go back to scripts folder type exit

  -h, --help               print this help message



​                           

  **./startuesim**

Tool to start UE softmodem for a particular scenario using Open Air Interface with RFsimulator
or 2 hosts running OAI nrUE and nrgNB respectively.
the ethernet link between the 2 hosts  needs to be at least 10Gbps 

Usage:  ./startuesim [OPTION]... [+VALUE] 

  -s, --scenario [value]   start UE softmodem executing scenario number [value]
                 
                           

                               ------------------------------------------------------------------
                              | 1 | standalone mode band 78 with 24prb  (SISO)                   |                                
                              | 2 | standalone mode band 78 with 51prb  (SISO)                   |                          
                              | 3 | standalone mode band 78 with 106prb (SISO)                   |
                              | 4 | standalone mode band 78 with 133prb (SISO)                   |                      
                              | 5 | standalone mode band 78 with 162prb (SISO)                   |      
                              | 6 | standalone mode band 78 with 217prb (SISO)                   |  
                              | 7 | standalone mode band 77 with 273prb (SISO)                   |   
                              | 8 | standalone mode band 78 with 106prb TDD 1 slot configuration |
                              |   | with 7 DL, 2 UL, 1 FL slots, Periodicity=10 Slots            |
                              | 9 | standalone mode band 78 with 106prb TDD 2 slot configuration |
                              |   | with 2 DL, 1 UL, 1 FL slots, Periodicity=4 Slots             |                     
                              | 10| standalone mode band 78 with 106prb (2x2 MIMO)               |
                              | 11| standalone mode band 78 with 133prb (2x2 MIMO)               |
                              | 12| standalone mode band 78 with 162prb (2x2 MIMO)               |     
                              | 13| standalone mode band 78 with 217prb (2x2 MIMO)               |  
                              | 14| standalone mode band 77 with 273prb (2x2 MIMO)               |
                              | 15| standalone mode band 66 with 106prb (SISO,FDD)               |    
                              | 16| do-ra mode: simualated 5G NSA connection with only 5G        |
                              |   | terminals being present                                      |                      
                              | 17| physical layer test with one slot assigned for downlink      |
                              | 18| extended phy layer test with parameters changed              |
                              |   | (parameters need to be changed directly to script code)      |        
                              -------------------------------------------------------------------


  -o, --scope              use nr-scope tool

  -p, --plmn               PLMN selection

​                           1 (default) --> 00101

​                           2           --> 50501                          

​                           2           --> 20295 

  -i, --info               show Open Air Interface version

  -h, --help               print this help message



**./ueconfig**

Tool to configure UE softmodem for a particular scenario using Open Air Interface SA Testbed
-the 2 hosts run OAI nrUE and nrgNB respectively.
-the ethernet link between the hosts and USRP N310 devices must be at least 10Gbps 

Usage:  ./ueconfig [OPTION]... [+VALUE] 
UOP - DCS LAB author Manolis Bozis 2023
Tool to configure UE softmodem for a particular PLMN using Open Air Interface
-the 2 hosts run OAI nrUE and nrgNB respectively.
-the ethernet link between the hosts and USRP N310 devices must be at least 10Gbps 

Usage:  ./ueconfig [OPTION]... [+VALUE] 

  -p, --plmn               PLMN selection

​                           1 (default) --> 00101

​                           2           --> 50501

​                           3           --> 20895 

  -e, --editor             choose editor

​                           1 (default) --> nano

​                           2           --> gedit                                                        

  -i, --info               show Open Air Interface software version

  -h, --help               print this help message
