# Miscellaneous

## Visibility Model

Originally, units created data items \(FCIF, MDS or eval type, for example\) in each squadron. Although they appear the same, each item is a separate instance in the database. This created redundancies and complicated moving people between squadrons. The visibility model handles this by creating a single database instance of the item. The user then selects which squadrons have visibility to the item. However… 

!!! danger "WARNINGs:"

    * Changing the item will affect all squadrons with visibility to that item. For example, your database has an Eval Requisite of “Vis Recce” and visibility is selected for multiple squadrons. If you change the item to “Visual Recce” it will appear as such in al squadrons, not just yours. This includes squadrons using the item to which you may not have permission. 
    * Because these edits can break data standards for a community which, in turn, negatively impact seamless data transition during Personnel export/import and squadron changes, any edits to Visibility data entries should be coordinated with the database PEX Admin and all using squadrons. 
    * In this example, the database has a single instance of the Eval Type "TAC." The 11RS, 130IS, 132IS and 742MS do not have visibility to TAC. The 80FS and 165AS do have visibility to TAC. If someone in the 80FS changes TAC to TACTICAL, it is changed for the 165AS as well. 

![binders](PEX/img/../../img/Miscellaneous/Eval Types.jpg){: style="height:100%;width:100%"}

## How to Configure SIPR to NIPR Connections

All of this is on the SIPR release db 

1. Add '80 FS' or whatever squadron you're exporting: 
    1. Navigate to Squadrons Module. 
    2. Right-click Add. 
    3. Fill in the first and second columns with 80 FS, Eglin AFB. 
 
2. Need to make the MDS \(F-22A in the 80 FS example\): 
    1. Navigate to Aircraft Module. 
    2. Right-click Add in the upper table.
    3. Fill in first available column with F-22. 
    4. Fill in the next column with A. 
3. Setup > Squadrons add F22A to show MDS in dropdown \(it's a column on the Squadrons grid far to the right\). 
4. Setup -> Personnel > Setup. 

5.  Ensure that the Squadron is set to 80 FS. 

6.  Majcom3 -> add "C" with description of "Charlie". 

7.  Majcom3 -> add "A" with description of "Alpha". 

8.  Majcom4 -> add "N" "N"." 

9.  Majcom4 -> add "E" "E". 

    1. SIPR Machine 

        1. Data Drive \(usually D:\) 

            1. Create a folder called Readiness. 

                1. Right-click and select Share With. 

                    1. Share With Pex Service Host Read/Write permissions. 

                    2. Share With Domain Users Read/Write permissions. 

        2. Export Certificate to the D:\\Readiness folder \(No Private Keys\). 

            1. Using MMC go to File>Add/Remove Snap-in. 

            2. Select Certificates on the left panel. 

            3. Click on the Add > button. 

            4. Select Computer Account. 

            5. Click Next. 

            6. Click Finish. 

            7. Click on the OK button at the bottom right of the dialog. 

            8. Expand Certificates. 

            9. Expand Personal. 

            10. Click on the Certificates Folder. 

            11. Right click on the certificate that is present in the center panel. 

            12. Select Export... 

            13. Click Next on the Welcome to the Certifcate Export Wizard. 

            14. Select No, do not export the private key radio button. 

            15. Click Next. 

            16. Keep the default option and click Next. 

            17. Click on the Browse button. 

            18. Find the D:\\Readiness folder (from the same machine). 

            19. Click the Open button. 

            20. Give the file a next \(usually <the machine name>.cer is sufficient\). 

            21. Click the Save button. 

            22. Click Next on the File to Export button 

            23. Click Finish to complete the action. 

            24. Click on the Ok button to dismiss the success dialog. 

        3. Go to PEX Service Host>Readiness Exchange tab. 

            1. Browse to Import Watch Path using the Browse button \(the ellispis next to the SIPR Certificate textbox\) - D:\\Readiness. 

            2. Select the machine's certificate using the Browse button \(the ellispis next to the SIPR Certificate textbox\). 
            
            3. Restart the PEX Service Host. 

    2. NIPR Machine 

        1. Using MMC go to File > Add/Remove Snap-in. 

        2. Select Certificates on the left panel. 

        3. Click on the Add > button. 

        4. Select Computer Account. 

        5. Click Next. 

        6. Click Finish. 

        7. Click on the OK button at the bottom right of the dialog. 

        8. Expand Certificates. 

        9. Expand Personal. 

        10. Click on the Certificates Folder. 

        11. Right click on the certificate in the center box \(it should be empty\). 

            1. Select All Tasks > Import.. from the context menu. 

            2. Click Next on the Certificate Import Wizard dialog. 

            3. Click on the Browse button. 

            4. Find the SIPR machine and select the Readiness folder `(\\<machine name>\Readiness)`. 

            5. Select the certificate that resides there and click Open. 

            6. Click Next. 

            7. Touching nothing else, click Next again. 

            8. Click Finish. 

            9. Click Ok to dismiss the Certificate Import Wizard dialog. 

            10. You should see a folder in the center panel. 

        12. Go to PEX Service Host>Readiness Exchange Tab. 

            1. On the NIPR settings section: 

                1. Set the Path save export file to: (using the Browse button -- the ellipsis) to  `\\<SIPR machine name>\Readiness`. 

                2. Select the SIPR Public Key Certificate using the el ipsis button to the SIPR Machine's Certificate from the step completed above. 

            2. Go to Scheduled Tasks Tab. 

                1. On the Export Readiness Data to file line, change to every 3 minutes using the gear next to the Interval column for that line. 

            3. Click the Apply button. 

            4. Restart the PEX Service Host. 

        3. How to Test 

            1. Ensure that the same squadrons are present on both databases \(SIPR and NIPR. 

            2. Log in to the NIPR instance of PEX. 

            3. Go to Setup>Squadrons and select a squadron common to both databases \(NIPR and SIPR. 

            4. Slide the screen over until you can see the Include Readiness Data in Export checkbox on the desired squadron and put a check in the box \(by clicking on the box\). 

            5. Go to the Scheduler module on the NIPR machine and Add an Event. 

            6. Go to the Scheduler module on the SIPR machine and wait for the event to appear \(it should appear within 3 minutes\). 

            7. Go to the D:\\Readiness folder on the SIPR machine. Files will temporarily populate this folder until moving to the appropriate subfolder; Failed, PendingDelete, or Processed. 

## Filters 

### Filter Wizards 

Filters allow you to control what kind of data to show, for example, instead of seeing all people in your unit, perhaps you want to see only those of a selected crew position. PEX includes filters for personnel, training tasks, and commitments. To use the filter, click on the Filter Wizard icon, which looks like a funnel \(ePEX and WinPEX\) or a magic wand \(WinPEX only\), depending on the module you are in. 

### Funnel Filter Wizard 
![binders](PEX/img/../../img/Miscellaneous/Funnel.png){: style="height:10%;width:10%"}

* Create a Filter.  Select the Personal or Squadron radio button. Personal – only you can see. If the filter you are building would be useful to others, select Squadron. Click the New button for either a Personnel filter or Task filter. Select the Filter Items and click Next. Select the specific filter elements and click Next until the summary displays. Enter a name for the filter and click save. 

* Edit a Filter.  Highlight a Filter and click the Edit button. Select the specific filter elements and click Next> until complete, then click Save. 

* Delete a Filter.  Highlight a Filter and click the Delete button. Click the Delete button if you are sure. 

* Apply Filter\(s\).  Executes the filter. 

* Details.  Opens the Filter Details dialog that lists the Filter name and a Summary of Selected Options. 

### Magic Wand Filter Wizard 
![binders](PEX/img/../../img/Miscellaneous/Magic Wand.png){: style="height:10%;width:10%"}

* Create a Filter.  Click the Create button. Select the Filter Items and click Next. Select the specific filter elements and click Next> until Finish button appears. Click Finish. Enter a title for the filter and select whether the filter is to be made available to all PEX users \(by checking Global\) or just yourself \(by not checking it\). Enter a description of the filter. Click Finish. 

* Edit a Filter.  Highlight a Filter and click the Edit button. Select the specific filter elements and click Next> until complete, then click Finish. Check the Global checkbox if desired. Click Finish. 

* Delete a Filter.  Highlight a Filter and click the Delete button. Click OK to the warning dialog. 

* Apply.  Executes the filter. 

* Details.  Opens the Filter Details dialog that lists the Filter description and Filter elements. 

## LAN Out Procedures 

Use this procedure if the Local Area Network \(LAN\) is down for an extended period of time that wil impact your operations. 

!!! caution "Caution"
    If you have multiple squadrons on the same database, this procedure works for each squadron to conduct PEX operations independently off LAN. However, when the LAN is back operational, only one squadron’s data can be used to update the overal database. The data the other squadrons entered into their independent instance of PEX wil not merge back in. 

!!! note "notes" 
    * The process requires about two hours to accomplish and about two hours to bring your main server back up to date when the LAN is restored. 
    * The PEX Database Manager includes its own help file. Open the Database Manager and click the Help button, or refer to the PEX Database Manager User Manual on the installation disc \(documents folder\) or PEX web site. 

1. Go to the PEX server, use the PEX Database Manager to backup the PEX database, and copy the backup file to a CD/DVD. Use SQL Enterprise Manager to take the PEX database and its archive database offline. 

2. Take this CD/DVD to a computer in your squadron that will become your interim PEX server. This machine must be set up as a PEX server according to the PEX Install Guide \(i.e., operating system, SQL, Internet Explorer, IIS, MS Office, .NET, PEX DB Manager, etc.\). This setup can be done ahead of time. 

3. On the interim computer, use the PEX Database Manager to restore the PEX database from the backup file. Name this interim database something other than what your original database was called, e.g., primary DB name: "PEXVPS"; interim DB name: "PEXVPSTemp". 

4. Install ePEX \(if required\) on the interim computer machine. 

5. Create a smal \(off LAN\) network with the interim computer acting as the PEX server and ePEX web server. Connect a printer\(s\) to this network. 

6. Provide the new Connect To information to your users on the smal network so they can log into the database. 

7. Use PEX as normal on this interim system until the LAN is operational. 

## LAN Returns to Operation Procedures \(Single squadron, pick one\) 

1. On the interim computer, use the PEX Database Manager to backup the PEX database, and copy the backup file to a CD/DVD. 

2. Go to your main PEX server and use the PEX Database Manager to rename your previous PEX 

3. database to something like PEXVPS\_OLD. Then, restore the PEX database from your backup file and give it the original database name, e.g., PEXVPS. Tell your users that PEX is back up. 

4. The data for that squadron will be current. The data for all other squadrons will be what it was when the LAN went out. 

## Use PEX While Entire Unit Deployed 

!!! abstract "Concept" 
    When your entire unit deploys, there are options on how best to employ PEX. The best option depends upon your circumstances. Regardless of the option you employ, realize up front that there is no way to re-integrate any deployed sortie data from a different database back into your home station database upon your return. Specifically, if while deployed you use PEX in a database on a different server or with a different name from the one which continues to be in use at the home station, that deployed sortie data will never be merged with your home station database. A combination of the options below is possible too. The PEX Help Desk can assist in your decision making. 

### Options 

1. Deploy and Use Home Station PEX 

    1. Reasons For: 

        * You do not supply hardware or software 

        * Your deployment package does not include supporting assets 

        * No installation required at deployed location 

        * PEX processes are not subject to local procedures 

        * Home station has complete visibility 

        * Host location command and control can be granted access to your schedule, etc. 

    2. Reasons Against: 

        * If the deployed schedule is classified this solution will not work 

        * Requires connectivity from a potentially austere location 

        * Operations difficult to combine with other flying units using PEX at deployed location 

        * Probably have to double enter a partial schedule in another system at deployed location 
        
2. Deploy with Your Database on Your Own Hardware 

    1. Reasons For: 

        * PEX is set up as desired before deployment 

        * No installation required at deployed location 

        * PEX processes are not subject to local procedures 

        * This is an approved configuration for a classified environment 

    2. Reasons Against:

        * You must supply additional hardware and software 

        * If the environment is classified, your supporting hardware will return classified 

        * You must account for the additional hardware in your deployment package 

        * You wil probably not be integrated into the existing network, thus you wil have no single flying operations solution 

        * Probably have to double enter a partial schedule in another system at deployed location 
        
3. Deploy with Your Database, Install on Host Hardware 

    1. Reasons For: 

        * You do not supply additional hardware or software 

        * Your deployment package does not need to include supporting assets 

        * Minimal installation required at deployed location 

        * A large amount of the preparation can be accomplished ahead of time 

        * PEX processes are not subject to local procedures 

        * Can work for either a classified or unclassified environment 

        * Determine in advance home station visibility, dependent on host network configuration 

        * Host location access is limited only by the status of their network; command and control can be granted access to your schedule, etc. 

    2. Reasons Against: 

        * Assumes the host is supplying all required software \(SQL Server\) 

        * You may not have a single flying operations solution 

        * Probably have to double enter a partial schedule in another system at deployed location 
        
4. Add Your Unit to Existing PEX Database 

    1. Reasons For: 

        * Established PEX processes at the deployed location 

        * Thoroughly integrated operations, single flying schedule solution and command visibility 

        * No dual entry 

        * No need to provide hardware or software 

        * No need to account for hardware in your deployment package 

    2. Reasons Against: 

        * Nothing is set up before arrival, much unit validation data will have to be tailored 
        
## Detailed Instructions For Using Pex with Entire Squadron Deployed

### Deploy and Use Home Station PEX 

Verify with your Communications Squadron the VPN solution in place. The usual solution is Microsoft Terminal Services, but there are others. Some of these other solutions may require supporting software at the deployed location. You may find your base has no solution installed. 

Verify with the deployed location that they can access your VPN solution. This should be accomplished by having them attempt to connect from a machine you wil be using during your deployment. It is possible that the network configuration at the deployed location could limit your access. These connectivity issues cannot be resolved through PEX. 

### Deploy with Your Database on Your Own Hardware 

Configure a computer to function as a database server and another to function as a web server. This is done before you install any component of PEX. Refer to the PEX Installation Guide for minimum hardware requirements. Essentially, you need a mid-level processor and memory capability. If you are going to network the hardware on your arrival, then the full version of SQL is recommended. If the entire PEX application is to be run from the one machine, then SQL Express wil suffice. In either case the PEX Installation Guide should be read first to ensure you adhere to some specific settings required of SQL. An IIS web server is not required if you do not intend to network PEX. On a stand-alone computer, all you need is WinPEX. 

Install the PEX DB Manager, PEX Service Host, \(ePEX, if networked\), and WinPEX. Refer to the Installation Guide. After you have your home station database as current as possible with deployed information go to your server, use the PEX DB Manager and back up your database. Do this at the last minute before you deploy so that you have the most current scheduling data, Stan/Eval data, training data, etc. Take the backup file and copy it to your deploying server, then use the DB 

Manager to restore it \(see the help files for specific steps\). 

!!! note "note"
    If you are deploying and you were given leftover hardware/software, you may have a SQL compatibility issue. For example, you can restore a DB created in SQL Server 2005 into an instance of SQL Server 2008, but not the other way around. SQL Server 2005 wil not be able to restore a DB created in SQL Server 2008. 

Log into the new database on the deploying machine to confirm operation/functionality. Then: 

* Delete extraneous squadrons you don’t need for the deployment 

* Delete extraneous validation items that you don’t need for the deployment 

* Add validation items you need for the deployment 

* Delete extraneous aircraft tail numbers you don’t need for the deployment \(or un-check Show in Drop Down\) 

* Add aircraft tail numbers you need for the deployment 

* Delete extraneous users you don’t need for the deployment 

* Add new users you need for the deployment and set permissions 

* Move extraneous personnel you don’t need for the deployment to the PCS Squadron 

* Add personnel you need for the deployment 

* Add locations you need for the deployment \(delete or hide unneeded ones\) 

* Change user permissions needing to be added or removed for the deployment 

* Change the log file paths for the following: ARMS imports and exports; ATO imports; and ACO 

* Delete missions you don’t need for the deployment 

### Deploy with Your Database, Instal on Host Hardware 

Verify the version of SQL Server running at the deployed location is the same or newer than the one you are using at home station. If they are running a version of SQL Server older than the one you are running, you will not be able to restore your database on their server. The only solutions would be to upgrade the deployed location SQL Server or use a different option. 

Verify the PEX version at the deployed location. PEX implements compatibility checks and will work only when all aspects of the program are the same version. I.e., the database, PEX Database Manager, ePEX, and WinPEX all have to be the same version. If the deployed location is running a different version of PEX, the only solutions would be to upgrade the deployed location PEX version or use a different option. 

After you have your home station database as current as possible with deployed information go to your server, use the PEX DB Manager and back up your database. Do this at the last minute before you deploy so that you have the most current scheduling data, Stan/Eval data, training data, etc. 

Take the backup file and copy it to your deploying server, then use the DB Manager to restore it \(see the help files for specific steps\). 

Log into the new database on the deploying machine to confirm operation/functionality. Then: 

* Delete extraneous squadrons you don’t need for the deployment 

* Delete extraneous validation items that you don’t need for the deployment 

* Add validation items you need for the deployment 

* Delete extraneous aircraft tail numbers you don’t need for the deployment \(or un-check Show in Drop Down\) 

* Add aircraft tail numbers you need for the deployment 

* Delete extraneous users you don’t need for the deployment 

* Add new users you need for the deployment and set permissions 

* Move extraneous personnel you don’t need for the deployment to the PCS Squadron 

* Add personnel you need for the deployment 

* Add locations you need for the deployment \(delete or hide unneeded ones\) 

* Change user permissions needing to be added or removed for the deployment 

* Change the log file paths for the following: ARMS imports and exports; ATO imports; and ACO imports 

* Delete missions you don’t need for the deployment 

### Add Your Unit to Existing PEX Database 

1.  Launch the Squadrons module and add the units/squadrons that wil be using PEX plus a "PCS" squadron to which you will eventually move people that have left your unit. 

2.  Once the squadrons are entered, personnel data can be added through the ARMS Interface or manual y through the Personnel module. 

3.  If your unit does not use ARMS, in the Personnel module, Setup tab, pick a unit and customize your lists. Once you are done with one squadron, you can use the right-click "Send To" command to copy the lists over to other units. 

4.  In the Personnel module, add your personnel manual y. 

5.  Launch the Aircraft module and enter your aircraft MDSs and tail numbers. 

6.  In the Users & Permissions module, assign other PEX users and grant them levels of access to the various PEX applications. 

### Use PEX Deployed, Integrated Squadrons 

This assumes the flying schedule is not built in unclassified PEX beforehand, but that you are entering data into PEX after flight for flying hours and training accomplishments. Our recommendation is; use home station database via ePEX for everything, except when the jet and crew come from different bases, and then use paper 781s. 

1.  When you arrive at the deployed location, login to your ePEX, and add the other squadron crew to your Personnel module \(just minimum information\), in your squadron. When the deployment is over, move them to the PCS squadron. In the Personnel module, on the Details tab, for the other squadron crew, check the box for "Do Not Export 781 Data" and enter their 781 Flying ORGN. 

2.  During deployment, as soon as possible after the sortie lands, login to the home station ePEX for the unit that owns the tail number. Using the ePEX Flying Schedule, Sorties tab, add the sortie and on the sortie, enter MDS, Tail Number, Mission Number, Mission Symbol \(MUC\), Takeoff Location, Land Location, Flight Auth Number, and associate the sortie to a flying hours account. Al this can be done in ePEX \(don't need Mission Board\). On the Crew tab, schedule the crew \(from either squadron\) and in Crew Details, enter the crew Duty Position and Pay status. Get this done before MX debrief. 

3.  AFTO 781. At MX Debrief, have a computer with access to both units' ePEXs. An icon for each on the desktop works well. When the crew arrives at MX Debrief, cal up the ePEX for the unit that owns the tail number. Go to the Squadron Daily Schedule \(SDS\) and the sortie will show up with a 781 link and a TAR link. The crew would click on the 781 link, fill out the electronic 781, get a MX Review and initials, and print out the 781 for MX. 

    1.  If the crew and jet belong to the same unit, done. The flight managers can export the PEX 781 data to ARMS. \(No need for a paper 781 for ARMS\) 

    2.  If the crew does not belong to the same unit as the jet, they wil need to bring a copy of the 781 to their flight managers for direct entry of Aircrew Data into ARMS. 

4.  TAR. If the crew belongs to the same unit as the tail number, the crew, on the SDS, clicks on the TAR link and fil s out the TAR. If the crew belongs to the other unit, the crew wil need to open up the other ePEX \(theirs\) and navigate to Training> Continuation> Reporting tab> and Person hyperlink and fill out the TAR. 

### Use PEX on NIPR and SIPR \(Deployed\) 

If your missions are classified but your other PEX data is unclassified, usually as a result of deployed operations, we recommend the following implementation: 

1.  Use SIPR PEX for ATO scheduling, sortie execution, and aircraft maintenance data. 

2.  Use NIPR PEX for Go/No-Go, FCIF, PRF, and Stan Eval. 

3.  When a unit deploys to your location, the home station flight management office would use their PEX Personnel module to export to file each person's PEX data. They would ensure the files make it to your location, where each person's data would be imported into both your SIPR and NIPR PEX databases. This would provide the NIPR and SIPR databases al the current PEX data on each deployed person. 

4.  Each day, double-enter, minimum, unclassified, sortie data into the NIPR PEX so that NIPR AFTO 781s and continuation training data could be logged. This minimum data would be: 

    1.  MDS 

    2.  Tail Number 

    3.  Mission Number 

    4.  Mission Symbol 

    5.  Takeoff Location 

    6.  Land Location 

    7.  Sched T/O Time \(can be bogus\) 

    8.  Sched Land Time \(can be bogus\) 

    9.  Assign Crew 

5.  When the crew gets back from flying, they would use your NIPR Squadron Daily Schedule page to enter their AFTO 781 data and to log their training events. The deployed squadron flight management would then use your NIPR PEX to audit, approve, and export to ARMS the 781 and training data. No 781s or training events would be logged on your SIPR side. 

6.  Once the 781 data and training events are pushed from the NIPR PEX into ARMS, the deployed flight management office would run the three Jaspersoft browsers we provide to extract data from ARMs. They would then import the three resultant .CSV files into both the NIPR and SIPR databases. This would keep both databases \(NIPR and SIPR\) current with aircrew flying time \(to track maximum flying hours\) and training currencies. Having the data in both systems is important so you have current and matching data for aircrew scheduling \(SIPR\) and Go/No-Go \(NIPR\). 

7.  When a unit heads back home, the deployed flight management office would use the NIPR 

PEX Personnel module to export to file each person's PEX data. They would ensure the files make it to home station, where each person's data would be imported into the NIPR PEX back home. 

### Use Your Logo Instead of US DoD 

Although the U.S. Department of Defense \(DoD\) is the primary user of PEX, you may be from another U.S. department, e.g., Dept. of Homeland Security, or from another country, e.g., Australia, Poland, or Oman. You should swap the DoD logo that appears throughout PEX with the one of your department or country. Even within DoD, you may want to swap the logo with that of your wing or group. 

1.  At the ePEX web server, the DoD image is stored at: `C:\inetpub\wwwroot\epex\images\DoD.gif`

2.  At each WinPEX client, the image is stored at: `Program Files/Patriot Excalibur/ePEX/Images/DoD.gif` 

3.  Rename the existing file to "DoD\_old.gif." 

4.  Save your desired image in .gif format at approximately the same size as the DoD image, about 1.5 inch square, and save your desired image as "DoD.gif" in the ePEX/Images directory. 

447 

Miscellaneous 

Abbreviations and Acronyms 

Accomplished 

Acc 

Actual 

Act 

Air Force Technical Order 

AFTO 

Air Refueling 

AR 

Aircraft 

Acft 

Aircrew Position Indicator 

API 

Airspace 

A/S 

Airspace Control Order 

ACO 

Air Tasking Order 

ATO 

Altitude 

Alt 

Ascending 

Asc 

Associate 

Assoc 

Attempts 

Att 

Availability 

Avail 

Availability Enabled 

Avail Enabled 

Calculation 

Calc 

Cancelled 

Cnx 

Category 

Cat 

Certification 

Cert 

Civilian 

Civ 

Commander 

Cmdr 

Configuration 

Cnfg 

Continuation Training 

Cont Tng or CT 

Continued 

Cont'd 

Control 

Cntl 

Control Air Force Specialty Code 

CAFSC 

Coordinating 

Coord 

Crew Position 

CP 

Currency 

Curr 

Date 

Dt 

Decertification 

Decert 

Deputy 

Dep 

Descending 

Desc 

Distance 

Dist 

Duration 

Dur 

Duty Air Force Specialty Code 

DAFSC 

Engine 

Eng 

Evaluation 

Eval 

Experience 

Exp 

Experience Indicator 

Exp Ind 

Expiration 

Expire 

Flight 

Flt 

Frequency 

Freq 

Hours 

Hrs 

448 

Indicator 

Ind 

Initial 

INIT 

Instructor 

INSTR 

Intelligence 

Intel 

Knowledge Level 

Know Lvl 

Letter 

Ltr 

Letter of Xs 

Ltr of Xs or LoX 

Location 

Loc 

Maintenance 

Mx or MX 

Maximum 

Max 

Minimum 

Min 

Mission 

Msn 

Mission Planning Sheet 

MPS 

Mission Ready Status 

Msn Rdy Status 

Operation 

Oper 

Organization 

Org 

Passport Expiration Date 

Passport Exp 

Period 

Per 

Point 

Pt 

Position Qualification Indicator 

PQI 

Primary 

Pri 

Primary Air Force Specialty Code 

PAFSC 

Priority 

Pri 

Proficiency 

Pro 

Proficiency Level 

Pro Lvl 

Projected Loss 

Proj Loss 

Qualification 

QUAL 

Qualification Code 

Qual Code 

Qualification Training 

Qual Tng 

Ready 

Rdy 

Reason 

Rsn 

Receiver 

Rcvr 

Recertification 

Recert 

Remaining 

Rem 

Remarks 

Rmks 

Requalification 

RQ 

Request 

Req 

Required 

Req 

Requisite 

Req 

Reverse 

Rev 

Scheduled 

Sched 

Secondary 

Sec 

Security 

Sec 

Self-Assessment Program Manager 

SAPM 

Sequence 

Seq 

449 

Miscellaneous 

Signature 

Sig 

Simulator 

SIM 

Spare 

Sp 

Special Experience Identifier 

SEI 

Squadron 

Sq 

Standardization 

Stan 

Start 

St 

Takeoff 

T/O 

Tanker 

Tnkr 

Trainer 

Trnr 

Training 

Tng 

Unit Manning Document 

UMD 

Unit Task Code 

UTC 

Volume 

Vol 

Warning 

Warn 

Weather 

WX 

Weather Category 

WX Cat 



Users with Multiple CACs 

You may encounter users with multiple ways to logon to the network domain, usual y through one of two Common Access Cards \(CAC\). This typically happens in Reserve or Guard units when a person has a crewmember CAC and another contractor CAC. The question arises, which CAC should be associated to their PEX account? 

Our recommendations: 

• This individual should be identified in the Personnel module only once. 

• This individual should be identified in the Users module only once. 

• The Person and User should be associated in the Users module. 

• The User should be associated to only one network account \(CAC\) in the Users module. 

That CAC should be the one they use the most. When they use the other CAC to logon the network, they would not be able to logon to PEX. 

CAUTION: Despite our recommendation, if you think the individual real y needs to access PEX using both network accounts \(CACs\), then: 

• This individual should be identified in the Users module twice. 

• Each User should be associated to only one network account \(CAC\) in the Users module. 

• This individual should be identified in the Personnel module only once. 

• Associate one user account \(the military one\) with the Personnel record. 

• Do not associate the other user account \(the contractor one\) with any Personnel record. 

• Via policy \(PEX can’t enforce this\), one User/Person combination should be used to manage the individual’s schedule, training, and Stan Eval. The other User account would be used for the individual to accomplish PEX administrative duties, for example. 

450 

Security Identifier 

The PEX Security Identifier is used to sign off FCIFs, proctor tests, and pilot review AFTO 781s. The Security Identifier is defaulted to the person’s ID number \(typically, the Social Security Number\). The Security Identifier can be changed only by the user and requires six to nine characters, case-sensitive. 

Change your Security Identifier 

1.  From My Page, click My Preferences. 

2.  In the Security Identifier fields, enter 6-9 characters and re-enter the same characters to confirm your change. Using the same number as your CAC PIN, so you don’t have to remember another password, is acceptable. 

3.  Click Save Preferences. 

If you forget your Security Identifier, click the “Reset to Personal ID Number” button. This resets your Security Identifier to the Personal ID Number \(usual y SSN\) saved in the Personnel module. 



451 


# Document Outline

+ PEX  
	+ How to get help  
		+ Help Desk 
		+ Within the PEX Main Menu: 

	+ How to use PEX Help  
		+ Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Controls 
			+ Workspace 
			+ Workflow 
			+ Setup 
			+ Processes 
			+ TTPs 
			+ Key words explained 


	+ New in 5.16.1  
		+ 21 August 2019 
		+ Ops  
			+ Go / No-Go 

		+ Training, Continuation  
			+ Web Service ARMS 

		+ Training, Mission  
			+ Most Common Grades on a Course 

		+ Scheduler Reports  
			+ ICBM Reports 


	+ What is PEX?  
	+ WinPEX Menu  
		+ File 
		+ Edit 
		+ View  
			+ Tools 
			+ Window 
			+ Help 


	+ New PEX Modules 
	+ PEX Environment 

+ Headquarters  
	+ Headquarters Overview  
		+ Introduction 
		+ Controls 
		+ Build Continuation Training tasks for units 
		+ Send Continuation Training tasks to units 
		+ Register units with the HQ system 

	+ Build Continuation Training Tasks  
		+ Introduction 
		+ Build HQ Continuation Training Unit Tasks 
		+ Export the tasks to a file 
		+ Import TACTICS data 

	+ Rollup Continuation Training Tasks  
		+ Introduction 
		+ Navigation 
		+ Use the rollup  
			+ Create a view on the Continuation Training Rollup Overview tab 
			+ Add a status to a view 
			+ Edit a status in a view 
			+ Delete a status in a view 
			+ View status details 
			+ Get the latest data 
			+ Use the Tasks page 



+ Displays  
	+ Calendar Viewer  
		+ Introduction 
		+ Permissions 
		+ Setup the Calendar Viewer 
		+ Use the Calendar Viewer 
		+ Background colors 
		+ Calendar Viewer differences between ePEX and WinPEX 

	+ My PEX  
		+ My PEX Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Controls 
			+ Workspace 

		+ Utilizing My PEX  
			+ Check for Issues 
			+ Check your Go/No-Go status 
			+ Check your Continuation Training status 
			+ Check your Schedule on the Home page 
			+ Check your Schedule in the Calendar 
			+ Check your required Action Items/signatures 
			+ Check and update your Preferences 
			+ TTPs  
				+ Sign off a FCIF 
				+ Log continuation training on a non-mission TAR 
				+ View/Email your To Do List 
				+ Take a NoGo test 
				+ If logging into PEX opens the legacy My Page 



	+ My Page  
		+ Introduction 
		+ Header information 
		+ My Data 

	+ Resources Rainbow  
		+ Introduction 
		+ Permissions 
		+ Setup the Resources Rainbow 
		+ Use the Resources Rainbow 
		+ Background colors 
		+ Resources Rainbow differences between ePEX and WinPEX 

	+ Sortie Viewer  
		+ Introduction 
		+ On the IIS server 
		+ On the client 
		+ Sortie Viewer Menu 


+ Ops  
	+ Binders  
		+ Introduction 
		+ Permissions 
		+ Rules 
		+ Module Notes 
		+ Workspace 

	+ Setup- Configure Binders  
		+ Setup tab  
			+ Binder Types 
			+ Documentation Folders  
				+ Add a Documentation Folder to a Binder Type 
				+ Edit a Documentation Folder in a Binder Type 
				+ Delete a Documentation Folder in a Binder Type 



	+ Binders- Managing Your Binders  
		+ Binders tab  
			+ Add a Binder 
			+ Edit Binder Details 
			+ Delete a Binder 
			+ Assign Alternates to a Binder 
			+ Unassign Alternates to a Binder 
			+ Review Actions  
				+ Document a Binder Review 
				+ View a Binder’s Review History 

			+ Import a Binder 
			+ Export a Binder 
			+ Manage Folders in Binders  
				+ Add Folders to a Binder 
				+ Add Folders to Multiple Binders 
				+ Delete Folders from a Binder 
				+ Reorder Folders in a Binder 

			+ Manage Documentation in Binders  
				+ Add Documentation to a Binder 
				+ Edit Documentation in a Binder 
				+ Delete Documentation in a Binder 
				+ Reorder Documentation in a Folder 

			+ Manage Observations in Binders  
				+ Add an Observation 
				+ View/Edit an Observation 
				+ Delete an Observation 



	+ FCIF  
		+ Introduction 
		+ Permissions 
		+ Controls 
		+ Workspace 
		+ Review and sign FCIF read files 

	+ Go NoGo  
		+ Go/No-Go Basics  
			+ Introduction 
			+ Indicators  
				+ Basic 
				+ Effective Msn Rdy Status 

			+ Permissions 
			+ Module Notes 
			+ Controls 
			+ Workspace 

		+ Configuring Your Go/No-Go Board  
			+ Setup  
				+ Views 
				+ Select an existing View for a Squadron 
				+ Create a new View 
				+ Edit a View or create a copy of a View 
				+ Delete a View 
				+ Create a new Go/No-Go Item 
				+ Edit or Delete a Go/No-Go Item 
				+ Setup Training Tasks to be No-Go or Priority 1, or to allow manual override 
				+ Effective and Assigned Mission Ready Status 
				+ Aviation Service Code \(ASC\) 


		+ Utilizing the Go/No-Go Board  
			+ Board  
				+ Filters 
				+ Column settings \(vertical ellipsis\) 
				+ Person Status Summary 
				+ Overall 
				+ DNIF 
				+ FCIF 
				+ TNG 
				+ TEST 
				+ S/E 
				+ FLY 
				+ HRS 
				+ Msn Rdy Status 
				+ Effective Msn Rdy Status 
				+ IN/OUT 
				+ Custom items 
				+ Update Multiple Statuses 
				+ NIPR to SIPR Pre-Calculated Data 



	+ Letter of X  
		+ Letter of X Basics  
			+ Introduction 
			+ Permissions 
			+ Module Notes 
			+ Definitions 
			+ Controls 
			+ Workspace 
			+ Workflow 

		+ Setup- Configuring the LoX  
			+ Preliminary Setup 
			+ Setup  
				+ Categories 
				+ Status 
				+ Certifications  
					+ Visibility 
					+ Associate Training Tasks to Certification 



		+ Manage Your Certifications and LoX  
			+ Letter of X  
				+ LoX Filtering 
				+ Create a LoX Template 
				+ Assign Certifications, Unassign Certifications, Display, Print, or Export the Letter of X 
				+ Manage Certification for a person 
				+ Assign Certification to Multiple Personnel at the same time 
				+ Unassign Certification from Multiple Personnel at the same time 
				+ Manage MAJCOM Quals 
				+ Managing Draft Changes 
				+ Manually Calculate Display Effective Mission Ready Status 
				+ View Qualification and Certification Totals 
				+ Print or Save LoX Report 
				+ Produce, Print and Save a LoX Currency Capacity Report 
				+ Identify Missing Training Tasks Setting a Person's Certification Status to DsubT 



	+ Squadron Daily Schedule  
		+ Overview 
		+ Permissions 
		+ Module Notes 
		+ Controls 
		+ Workspace 
		+ Configure Squadron Daily Schedule for Your Unit 
		+ Grid Customization 

	+ ORM  
		+ Setup ORM  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Controls 
			+ Setup Overview 
			+ Setup other PEX modules for ORM 
			+ Setup the ORM module 
			+ Workspace 

		+ ORM Workflow  
			+ Introduction 
			+ Workspace 
			+ Determine Risk 


	+ Waterfall  
		+ Waterfall Basics  
			+ Overview 
			+ Permissions 
			+ Module Notes 
			+ Controls 
			+ Workspace 

		+ Waterfall  
			+ Setup Waterfall for Squadron 
			+ Display Setup Waterfall for Squadron and Generate GTIMS report 


	+ Weapons  
		+ Weapons Inventory 
		+ Weapons Loads and SCLs 
		+ Weapons Training 

	+ AFTO Form 781  
		+ Introduction 
		+ Setup 
		+ Implement 
		+ Fill out the PEX AFTO 781 


+ Scheduling  
	+ ATO - Import an Air Tasking Order  
		+ Introduction 
		+ Best Practice 
		+ Import an ATO into PEX 
		+ Associate your PEX Squadron to an ATO Unit  
			+ PEX Missions 
			+ PEX Sorties 
			+ Takeoff and Land Locations 
			+ Takeoff and Land Times 
			+ Controlled \(Frozen\) Times 

		+ ATO Changes 
		+ Troubleshooting – Not All ATO Missions Show Up 

	+ Bids and Availability  
		+ Bids and Availability- Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Controls 
			+ Workspace 

		+ Bids and Availability- Setup  
			+ Personnel Availability Type 
			+ Personnel Commitment Type 
			+ Squadrons Availability 
			+ Personnel Availability 

		+ Bids and Availability for Schedulers  
			+ Two-monitor Setup 
			+ Scheduler Opens/Close Bids 
			+ Accepting/Rejecting Bids 
			+ Adding notes to Bids 
			+ Add a Bid 
			+ Remove a Bid 
			+ Re-prioritizes Bids 


	+ Commitments Board  
		+ Commitments Board- Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Workspace 

		+ Commitments Board- Setup  
			+ Setup  
				+ Display 


		+ Managing Personnel Commitments  
			+ Personnel tab  
				+ View Personnel Commitments 
				+ Add a Personnel Commitment 
				+ Add a Person/People to a Commitment 
				+ Add a Crew Template to a Commitment 
				+ Fill in Crew Template with Desired Qualifications 
				+ Remove a Crew Template from a Commitment 
				+ Set Up a Recurring Commitment 
				+ Edit a Commitment 
				+ Remove Personnel from a Commitment 
				+ Delete a Commitment 


		+ Managing Crew Templates  
			+ Crew Templates  
				+ Create a Crew Template 
				+ Edit a Crew Template 
				+ Change which Squadrons use a Crew Template.  
				+ Delete a Crew Template 


		+ Managing Equipment Commitments  
			+ Commitment Board – Equipment Setup  
				+ Schedule Equipment 
				+ Add an Equipment Type 
				+ Add a Piece of Equipment 

			+ Edit Equipment Types and Equipment Lists  
				+ Edit an Equipment Type 
				+ Edit a Piece of Equipment 

			+ Delete an Equipment Type or a Piece of Equipment  
				+ Delete an Equipment Type 
				+ Delete a Piece of Equipment 
				+ Add an Equipment Commitment 
				+ Associate Equipment to a Commitment 
				+ Edit, Replicate, or Delete Equipment Commitments 
				+ Remove equipment from an Equipment Commitment 


		+ Managing Events  
			+ PEX Events  
				+ Add an Event 
				+ Associate a Commitment to an Event 
				+ Print the Event Report 
				+ Edit an Event 
				+ Remove a Commitment from an Event 
				+ Delete an Event 


		+ Mission Planning Sheet  
			+ Setup the Mission Planning Sheet \(MPS\) 
			+ How to Use the Mission Planning Sheet  
				+ Legend 



	+ Flying Hours  
		+ Flying Hour Basics  
			+ Introduction 
			+ Permissions 
			+ Controls 
			+ Workspace 
			+ Definitions 
			+ Workflow 

		+ Flying Hour Setup  
			+ AF Model Forecast 

		+ Flying Hours, Quick Setup 
		+ Flying Hours, Advanced 
		+ Flying Hours, Associate Units 
		+ Flying Hours, Monitor Execution  
			+ Overview Page 
			+ Daily Page \(Single Account Only\) 
			+ Graphs Page 
			+ View Summary Data 
			+ Day-to-Day Use 

		+ REMIS- Reconcile your hours  
			+ REMIS, Setup and Download File  
				+ Setup 
				+ Download REMIS Data Files from AF Portal 

			+ REMIS – Import File and Reconcile  
				+ Import REMIS .CSV File into PEX 
				+ Reconciliation, Identify Discrepancies 
				+ Reconciliation, Edit PEX Data 
				+ FY Progress from REMIS 



	+ Flying Schedule  
		+ FS - Setup  
			+ Introduction  
				+ Setup Pre-Sortie Crew Rest 
				+ Setup Post-Sortie Crew Rest 
				+ Setup Post-Mission Crew Rest 1-to-3 Rule 


		+ FS - Sorties  
			+ Setup the Sorties page 
			+ Difference between a Mission and a Sortie 
			+ Add a single sortie 
			+ Add a formation 
			+ Add a sortie to an existing mission or formation 
			+ Copy an existing mission to another day 
			+ Enter actual takeoff and land times 
			+ What’s the difference between deleting a mission and cancelling it?  
			+ Delete missions 
			+ Cancel missions 
			+ Use all the different page controls  
				+ Squadrons 
				+ Calendar 


		+ FS - Crew  
			+ Setup the Crew tab 
			+ Pick the sorties to work on 
			+ Schedule crew members onto sorties 
			+ Enter flight authorization and 781 data for the crew 
			+ Hide Tail Numbers for No-Go personnel 
			+ Add Crew Rest 
			+ Build and use Crew Templates 
			+ Build and use Hard Crews \(Crew Set\) 
			+ Schedule ground commitments from here 

		+ FS - Loads  
			+ Setup the Loads tab 
			+ Assign an individual load item to a sortie 
			+ Assign an SCL to a sortie 
			+ Auto-build an SCL number from individual load items 
			+ Page Controls 

		+ FS - ICBM Schedule  
			+ What logic does PEX use to build the alert schedule?  
			+ Set this up 
			+ Generate the alert schedule 
			+ Pull someone off alert 
			+ Delete a mission 

		+ FS - DMO  
			+ Register my squadron 
			+ We’re registered. How do we see another unit’s schedule 
			+ Send a support request 
			+ Temporarily suspend sending my scheduling data 
			+ Turn it back on 


	+ Long Range Schedule  
		+ Long Range Schedule Basics  
			+ Introduction 
			+ Permission Roles 
			+ Rules 
			+ Controls 
			+ Workspace 
			+ Definitions  
				+ For Supervisor or Shift commitments 
				+ For all other commitment types \(e.g., Leave or TDY\) 


		+ Long Range Schedule Setup  
			+ Views  
				+ Warning Flags 
				+ Settings 


		+ Use the Long Range Schedule  
			+ Check for scheduling issues 
			+ Check for undermanned shifts 
			+ Check for excessive commitments 
			+ Check personnel by Qualifications & Certifications 
			+ Add a commitment 
			+ Edit a Commitment 
			+ See all commitment details for a single day 
			+ Email the schedule to people 


	+ Mission Board  
		+ Setup 
		+ Build Sorties 
		+ Mission Events 
		+ Sortie Events 
		+ Schedule AR Tracks 
		+ Scheduling Supervisors 
		+ Lock Schedule 
		+ Track Changes 
		+ Tail Number Denial 
		+ Export to TAP 
		+ Distance, Time, and Fuel 
		+ Miscellaneous 
		+ Custom Flight Schedule 

	+ Personnel Availability  
		+ Displaying Personnel Availability Data 
		+ Updating Personnel Availability Electronically 
		+ Adding Personnel Availability Data Manually 
		+ Removing Personnel Availability Data Manually 
		+ Editing Personnel Availability Data Manually 
		+ Personnel Availability Menu 

	+ RPA Schedule  
		+ RPA Schedule Basics  
			+ Introduction 
			+ Permissions 
			+ Module Notes 
			+ Controls 
			+ Workspace 
			+ Page Display Menu \(upper right\) 
			+ Right-Click Menu 
			+ Workflow 

		+ RPA Schedule Setup  
			+ Setup tab  
				+ Add Ground Control Stations \(GCS\) 
				+ Add Other Mission Units 


		+ RPA Scheduling  
			+ Add Vulnerability Periods 
			+ Display Personnel by shifts or personnel filters 
			+ Shifts 
			+ Filters  
				+ Manage Crewmembers on missions 



	+ Shift Schedule  
		+ Shift Schedule Basics  
			+ Introduction 
			+ Permissions 
			+ Controls 
			+ Workspace 
			+ Workflow 

		+ Shift Schedule Setup  
			+ Squadron Management Setup  
				+ Setup- Personnel module 
				+ Setup- Letter of X module 
				+ Setup- Identify conflicts 
				+ Setup- Shift Types 
				+ Setup- Shift Template 
				+ Delete a Shift Template 
				+ Setup- Crew Template 
				+ Delete a Crew Template 
				+ Setup- Crew Set 
				+ Delete a Crew Set 
				+ Setup- Shift Patterns 
				+ Edit Shift Patterns 
				+ Delete Shift Patterns already created 


		+ Shifts- Managing Your Shifts  
			+ Use a Shift Template 
			+ Add/Create a Shift Manually 
			+ Copy a shift 
			+ Edit a Shift on the schedule 
			+ Delete a Shift on the schedule 
			+ Schedule Personnel 
			+ Schedule Personnel– Crew Set or Crew Template 
			+ Use a Shift Pattern 


	+ Scheduling Reports  
		+ Flying Schedules - General 
		+ MADO \(Missile Alert Duty Order\) 
		+ Range Report  
			+ How do I run the report?  

		+ AF 4327, ARMS Fighter Flight Authorization  
			+ How do I generate the 4327?  

		+ AF 4327a, Crew Flight Authorization 
		+ AFSOC 40, Mission Summary Report 
		+ Flying Schedules 
		+ Personnel Fly Hours 
		+ Personnel Schedule 
		+ AFSOC 108, Weekly / Daily Aircraft Utilization Schedule 
		+ RPA Schedule Report 

	+ Scheduler  
		+ Scheduler Basics  
			+ Overview 
			+ Permissions 
			+ Module Notes 
			+ Controls 
			+ Workspace 
			+ Time Zone Selection 
			+ Filters 
			+ Terms 

		+ Squadron Management Setup  
			+ Setup- Event Templates  
				+ Edit or delete an Event Template 
				+ Add an Event Template \(Mission, Event or Production Request\) to the schedule 

			+ Setup- Resource Templates 
			+ Edit or delete a Resource Template 
			+ Add a Resource Template to a Mission, Event or Production Request 
			+ Setup- Resource Status Type Requirement 
			+ Setup- Lookup Lists  
				+ Edit or delete a Lookup List 

			+ Setup– Draft and Publish 
			+ Set Publish on/off mode for the Schedule 
			+ Publish a Draft Mission/Event/Production Request 
			+ Unpublish a draft Mission/Event/Production Request 
			+ Publish all items in a day or range of days 
			+ Unpublish all items in a day or range of days 
			+ Setup- Custom Fields 
			+ Add a Custom Field 
			+ Edit a Custom Field 
			+ Delete a Custom Field 

		+ Common Scheduler Functions  
			+ Add a Person Resource 
			+ Manage Resource Roles On a Sub-Event 
			+ Set Resource Time Tracking 
			+ Use Resource \(Crew\) Templates to find qualified personnel 
			+ Group Resources 
			+ Add a Resource Status Type Requirement 
			+ Enter actual start/end times 
			+ Add attachment\(s\) to a Mission, Event or Production Request 
			+ Delete attachment\(s\) to a Mission, Event or Production Request 
			+ Add Categories to a Mission, Event or Production Request 
			+ Delete Category\(s\) from a Mission, Event or Production Request 
			+ Display a Mission/Event/Production Request in Timeline mode 
			+ Workspace 
			+ Display a Mission/Event/Production Request in Hierarchy mode 

		+ Scheduler Event - Functions  
			+ Add an Event 
			+ Add a Sub Event 
			+ Edit an Event 
			+ Delete an Event 
			+ Add a Person or other Resource to an Event 
			+ Add a Resource Group to an Event 
			+ Remove a Person or other Resource from an Event 
			+ Copy an Event 74675 NEW IN 5.16 
			+ Edit the frequency of a recurring event 
			+ Create a Group Event 
			+ Edit a Group Event 

		+ Scheduler Mission - Functions  
			+ Add a Mission  
				+ Single-sortie Mission 
				+ Add Sortie 

			+ Add a formation mission 
			+ Add a trip mission 
			+ Add aircraft to a sortie 
			+ Offset Sub Event times from the Mission start or end time 
			+ Add Take Off/Land Locations 
			+ Delete Take Off/Land Locations 
			+ Add Aircraft to a sortie 

		+ Scheduler Production Request - Functions  
			+ Add a Production Request 
			+ Edit a Production Request 
			+ Delete a Production Request 
			+ Setup a recurring Production Request 
			+ Edit the frequency of a recurring Production Request 


	+ Scheduler Reports  
		+ Scheduler Reports Basics  
			+ Introduction 
			+ Permissions 
			+ Controls 
			+ Workspace 

		+ Delivered Scheduler Reports  
			+ RPA Schedule 
			+ Missile Operations Personnel Schedule 
			+ Missile Operations Locations Schedule 



+ Training  
	+ Continuation Training  
		+ Continuation Training Basics  
			+ Introduction 
			+ Permissions 
			+ Module Notes 
			+ Controls 
			+ Workspace 

		+ PEX - ARMS Interface  
			+ PEX-ARMS Interface Overview  
				+ Overview 
				+ Permissions 
				+ Rules 
				+ Controls 
				+ Workspace  
					+ Settings 
					+ Import 
					+ Export 


			+ Setup - Configure the PEX-ARMS Interface  
				+ New in PEX 5.16.1.  
				+ Web Services Network Setup Interface 
				+ Setup the import from ARMS to PEX 
				+ Setup the Virtual Account export from PEX to ARMS 

			+ Import ARMS data to PEX  
				+ New in PEX 5.16.1.  
				+ Workflow 
				+ ARMS Personnel data sent to PEX 

			+ Export PEX data to ARMS  
				+ New in PEX 5.16.1.  
				+ Workflow 
				+ PEX Training data sent to ARMS 


		+ Setup CT  
			+ Configure RAP  
				+ Introduction 
				+ RAP Requirements 
				+ SIM RAP/MSN Rdy 
				+ RAP O&M TDY 
				+ MRS Calc Options 

			+ Guest Personnel in your Database 
			+ ARMS- Configure your PEX-ARMS Interface  
				+ Introduction 
				+ Settings 
				+ Import  
					+ ARMS Export – ODAC Setup 

				+ Export 

			+ Setup- Configure Continuation Training  
				+ Setup tab  
					+ Setup Workspace 
					+ Lists 
					+ Unit Tasks 
					+ Unit Settings 
					+ ARMS Tasks 



		+ Reporting Completed Training Tasks \(TAR\)  
			+ Reporting tab  
				+ Report by Person 
				+ Report by Mission 
				+ Report by Commitment 
				+ Generate AF 1522 \(Group Report\) 
				+ Overview 


		+ Unit Task Assignment  
			+ Unit Task Assignment tab  
				+ Assign Unit Tasks to Individuals 
				+ Manage Unit Tasks to Individuals 
				+ Check Assigned 
				+ View Historical Training 


		+ Worksheet Builder- Create TARs and MARs  
			+ Worksheet Builder tab  
				+ Create a New Worksheet 
				+ Edit a Worksheet 
				+ Delete a Worksheet 


		+ Auditing Reported Training Tasks and AFTO 781 Data  
			+ Audit tab  
				+ TAR 
				+ AFTO 781 


		+ Import ADLS Data  
			+ ADLS tab  
				+ Setup 


		+ TACTICS- JTAC Training  
			+ TACTICS tab  
				+ Setup 
				+ Use 


		+ Training Tasks- Track all Personnel and all Tasks  
			+ Training Tasks tab 

		+ Overview- Track Unit Training Progression  
			+ Overview tab 


	+ Master Training Plan  
		+ MTP - Basics  
			+ Overview 
			+ Permissions 
			+ Module Notes 
			+ Controls 
			+ Workspace 

		+ Workflow 
		+ Managing Your MTP  
			+ Plan Management tab  
				+ Create a MTP and add Milestones 
				+ Edit a MTP 
				+ Delete a MTP 

			+ Assign & Unassign tab  
				+ Assign a MTP 
				+ Unassign a MTP 

			+ Personnel Tracking tab  
				+ View Trainee’s progress in a MTP 
				+ View and Print a Progress Report 



	+ Qualification Training  
		+ Qualification Training Overview  
			+ Mission Homepage 
			+ OJT Homepage 

		+ Popular Topics  
			+ By Courses  
				+ Courses 
				+ Topics 

			+ By Task Lists  
				+ Task Lists 
				+ Topics 

			+ By Signatures  
				+ Signatures 
				+ Topics 


		+ Overview Rainbow  
			+ Select a Course 
			+ Enrolled Students 
			+ View Preferences 
			+ BOI View 
			+ Date View 
			+ BOIs 
			+ BOI Dates 
			+ Regression Explanations 
			+ Unaccomplished Tasks & Explanations 

		+ Students/Trainees  
			+ View Students/Trainees 

		+ Student Details  
			+ View a student's course canvas  
				+ Phase Overview 
				+ Unaccomplished Tasks 
				+ MFR 
				+ Closeout 
				+ Summary 


		+ Mission  
			+ Mission Training \(Courses\) Overview  
				+ Introduction 
				+ Controls 
				+ Workspace 

			+ Setup Mission Training  
				+ Add a Grade Set 
				+ Add a Task List 
				+ Set Review Options 
				+ Add Gradesheet Reminders 
				+ Create links between BOIs and STS Task lists 
				+ Edit existing links between BOIs and STS Task lists 
				+ Add Phases 

			+ Create a Course  
				+ Add a new course 
				+ Activate a course 
				+ Edit an activated course 
				+ Copy as a Local Course 
				+ Create a New Version 
				+ Delete a course 

			+ Build a Course 
			+ Manage Courses  
				+ Enroll and withdraw students 
				+ Modify a student’s training plan 
				+ Review a Training Folder 
				+ Add an MFR 
				+ Sign an MFR 
				+ Apply Multiple MFRs 
				+ Close enrollment 
				+ Complete/closeout a student’s training program 
				+ Apply attachments to a BOI 
				+ Apply a Filter 

			+ Manage Instructors  
				+ Assign instructors to a course 
				+ Assign primary, secondary, and continuity instructors to a student 
				+ Assign a planned instructor to a BOI 
				+ Assign an actual instructor to a BOI 
				+ Rapidly Replace Trainers and Certifying Officials 

			+ Gradesheet- Grade BOIs and Tasks  
				+ Open the Gradesheet 
				+ Gradesheet Workspace 
				+ Grade Tasks 
				+ Grade BOI 

			+ Mobile Gradesheet Basics  
				+ Overview 
				+ Permissions 
				+ Module Notes 
				+ Controls 
				+ Workflow 

			+ Transfer BOIs to/from Your Mobile Device  
				+ Download BOIs from your PEX database to your mobile device 
				+ Upload BOIs from your mobile device to your PEX database 

			+ Mobile Gradesheet- Grade BOIs and Tasks  
				+ Open the Mobile Gradesheet 
				+ Gradesheet Workspace 
				+ Grade Tasks 
				+ Grade BOI 


		+ OJT  
			+ On-the-Job Training \(OJT\) Overview  
				+ Controls 
				+ Workspace 

			+ Setup OJT  
				+ Setup PEX 623s.  
				+ Import a task list 
				+ Create a task list from scratch 
				+ Create a copy or new version of a task list 
				+ Edit, delete, or export a task list 
				+ Edit, delete, reapply, or deactivate a workcenter 

			+ 623a Usage  
				+ Assign trainees 
				+ Manage trainees 
				+ Manage 623a entries 

			+ 623a Transcription  
				+ Transcribe a task list 
				+ Validate a Transcription 

			+ 623a Miscellaneous  
				+ Print a 623a 
				+ View the Proficiency Code Key 
				+ Sending a Workcenter to another Squadron 
				+ Printing a Workcenter 
				+ Editing Trainers and Certifying Officials.  



	+ Training Folder  
		+ Training Folder Routing Checklists  
			+ Create editable checklist templates of reviewers 
			+ Assign a routing checklist to people 
			+ Add a checklist by course 
			+ Review and acknowledge a checklist 
			+ View completed checklists 
			+ Copy checklist 


	+ Training Reports  
		+ Currency Report 
		+ TAR Report 
		+ RAP Probation Status Report 
		+ Sortie Type Report 
		+ AF Form 1522 
		+ Course Details Report 
		+ Student Progress Report 


+ Stan Eval  
	+ FCIF Admin  
		+ FCIF Admin Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Controls 
			+ Workspace 

		+ Manage Your FCIF Program- Add, Edit, Rescind  
			+ Setup FCIF Admin 
			+ Add an FCIF 
			+ Edit an FCIF 
			+ Rescind an FCIF 
			+ Delete an FCIF 
			+ Auto Unsign 
			+ Print an FCIF 
			+ Print an FCIF Index 
			+ Print an FCIF card \(AF Form 4121\) 
			+ Workflow 


	+ Stan Eval Management  
		+ SEM Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Workspace 

		+ Setup- Configuring SEM  
			+ Setup tab  
				+ Setup  
					+ Eval Prefixes 
					+ Eval Types 
					+ Eval Requisites 
					+ Weapons Events 

				+ Preferences  
					+ Desired Months Settings 
					+ Signature Due 
					+ Notification Mail 
					+ Stan Eval Rules 
					+ Periodic Evaluation Expiration 
					+ Eligibility Zone 
					+ Default Eval Form 
					+ Eval Form Signature Mode 
					+ Display MDS Series Letter 
					+ Email Zone Notification Template and Email Late Requisites Template 
					+ Additional Eval Reviews 
					+ Restriction Templates 

				+ Assoc Eval Types/Reqs 
				+ Mission Description 
				+ Eval Forms 
				+ Eval Criteria  
					+ Evaluation Criteria Tool tab 
					+ Evaluation Criteria tab 



		+ Overview- Manage Your Stan Eval Program  
			+ Overview tab  
				+ Rainbow 
				+ Requisites 
				+ Awaiting Signatures 
				+ Trending  
					+ Trend by Discrepancies 

				+ Status 
				+ Additional Training 
				+ Notifications 
				+ Auto-Open Evaluations 
				+ Eval Criteria Details 


		+ Personnel- SEM Workspace  
			+ Personnel tab  
				+ Name Search 
				+ Advanced Search 
				+ Import Forms 
				+ Person Details  
					+ Header 
					+ Menu 
					+ Qualifications 
					+ Open Evaluations 
					+ Add an evaluation 
					+ Edit an evaluation 
					+ Additional Training 
					+ Current Restrictions and Complete Restrictions History 
					+ Eval Forms/MFR 
					+ AF 942 
					+ AF 4349 
					+ Certifications 
					+ Major Discrepancies 
					+ Minor Discrepancies 

				+ Eval Details  
					+ Header 
					+ Edit 
					+ Set Eval EQ 
					+ View Form 
					+ Primary Eval 
					+ Evaluation Form Ready For Final Edits 
					+ Sign 
					+ Release for Signatures 
					+ Complete Eval 
					+ Worksheets 
					+ Requisites 
					+ Eval Scheduled 
					+ Completed Requisite Exams 
					+ Completed Requisite Worksheets 
					+ Additional Training 
					+ Restrictions 
					+ Mission Descriptions 
					+ Discrepancies 
					+ Comments 



		+ TTPs- Administering Evals and Use Cases  
			+ Auto open Evaluations  
				+ Open the evaluation without edits 
				+ Open the evaluation with edits 

			+ Administer a Basic Evaluation 
			+ Qualification Level grade of 3/1 
			+ Administer a Recheck Evaluation after a Q3  
				+ Ground Recheck 
				+ Flight Recheck 

			+ Administer a Commander-Directed Downgrade or SIO-Directed Downgrade 
			+ Evaluation Form Signature Process  
				+ Pre-Signature Reviews 
				+ Set Signature Blocks for the Reviewing and Final Approving Officers 
				+ Remarks, Concur and Not Concur for Reviewing and Final Approving Officers 
				+ Manual Signatures 
				+ Digital Signatures 
				+ Digital Signatures Outside of PEX 
				+ Post-Signature Reviewer 

			+ Ground Only Evaluation 
			+ Certifications  
				+ Add a certification 
				+ Add a certification from the Letter of X 
				+ Edit a certification 
				+ View an AF Form 1381 or 4348 
				+ Sign a certification 
				+ Convert certifications to a scanned AF4348 
				+ Import a certification form 

			+ Upgraded or Obsolete Qualifications 
			+ Waivers 
			+ Evaluation Folder Discrepancies  
				+ Major Discrepancies 
				+ Minor Discrepancies 
				+ Add a minor discrepancy 
				+ Edit a minor discrepancy 
				+ Delete a minor discrepancy 
				+ Import a minor discrepancy 
				+ View the minor discrepancy log 

			+ Evaluation Criteria  
				+ Create Evaluation Criteria 
				+ Import Evaluation Criteria 
				+ Save Evaluation Criteria 
				+ Apply Evaluation Criteria 
				+ Adding Profiles 

			+ Import Forms  
				+ Multiple people 
				+ One person 

			+ Export/Import an Eval Folder/FEF 


	+ Testing  
		+ Testing Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Controls 
			+ Workspace 
			+ Workflow 

		+ Testing- Taking and Reviewing Exams as an Examinee  
			+ Testing tab  
				+ Take an exam 
				+ Take a practice exam 
				+ Review an exam 
				+ TTPs 


		+ Testing- Reviewing, Adjusting and Entering Exams as an Examiner  
			+ Testing tab  
				+ Review an exam 
				+ Adjust an exam 
				+ Enter an Off-Line exam \(an exam taken outside of PEX\) 



	+ Testing Admin  
		+ Testing Admin Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Workspace 
			+ Workflow 

		+ Overview- Manage Your Testing Program  
			+ Overview tab  
				+ Assigned Exams 
				+ Completed Exams 


		+ QDB, Questions and Exams- Creating and Assigning  
			+ QDB tab  
				+ List QDBs 
				+ Create QDB 
				+ Export QDB 
				+ Delete a QDB 
				+ Import QDB 

			+ Questions tab  
				+ List Questions 
				+ Create a question 
				+ Edit a question 
				+ Delete a question 
				+ Copy Questions 

			+ Exam tab  
				+ List Exams  
					+ Create an exam 
					+ View exam questions 
					+ Edit Exam 
					+ Copy exam 
					+ Print products 

				+ Assign Exams  
					+ Person to Exam\(s\) 
					+ Exam to People 
					+ Unassign an exam or multiple exams from an individual 

				+ Unassign Exams 
				+ TTPs 


		+ Trending Exams  
			+ Trending tab  
				+ Select Trending Criteria by QDB/Exam 


		+ Setup- Configuring Testing Admin  
			+ Setup tab  
				+ Subjects, References, & Media 
				+ Trending Preferences 
				+ Upload/Delete Media 
				+ QDB Source & Exam Types 
				+ Proctors 



	+ Stan Eval Reports  
		+ Open Evals Report  
			+ Overview 
			+ Access 
			+ Data 

		+ Completed Evals Report  
			+ Overview 
			+ Access 
			+ Categories displayed 

		+ No-Notice Report  
			+ Overview 
			+ Access 

		+ Testing Report  
			+ Overview 
			+ Access 
			+ Data 

		+ Eval Issues Report  
			+ Overview 
			+ Access 
			+ Data 



+ Maintenance  
	+ Maintenance Basics  
		+ Introduction  
			+ 1. Aircraft 
			+ 2. Aircraft Generation 
			+ 3. Reporting 
			+ 4. Reports 

		+ Permissions 
		+ Module Notes 
		+ Controls 
		+ Workspace 

	+ Aircraft  
		+ Setup tab  
			+ Introduction 
			+ Workspace 
			+ Settings 
			+ Lists 

		+ Aircraft tab  
			+ Introduction 
			+ Workspace  
				+ Add an MDS 
				+ Add a Tail Number 
				+ Move a Tail Number to Another Squadron 


		+ Status tab  
			+ Introduction 
			+ Workspace 
			+ Status 
			+ Status History 
			+ Discrepancy List 


	+ Aircraft Generation  
		+ Aircraft Generation - Setup  
			+ Introduction 
			+ Permission Roles 
			+ Setup 

		+ Aircraft Generation  
			+ Introduction 
			+ Permission Roles 
			+ Usage 


	+ Handle Similar MDSs in PEX 
	+ Maintenance Reports  
		+ Daily MX Loads  
			+ Introduction 
			+ Permission Roles 
			+ Before using the report 
			+ Run the report 

		+ Weekly Frag Request  
			+ Introduction 
			+ Permission Roles 
			+ Before using the report 
			+ Run the report 
			+ Munitions grouping 
			+ Quantity \(Qty\) and Spare \(Sp\) calculations 

		+ AF 2407, Weekly/Daily Flying Schedule Coordination  
			+ Introduction 
			+ Permission Roles 
			+ Setup 
			+ Generate the form 
			+ Data sources 
			+ Signatures 



+ Setup  
	+ External Interfaces  
		+ Scheduling Interface Introduction  
			+ Overview 
			+ UC2, EMOC and TBMCS-Force Level 
			+ GTIMS 
			+ CSE 
			+ Scheduling data interfaces outside of the External Interfaces module 

		+ Status  
			+ Overview 
			+ Verify and monitor connections 
			+ Workflow 

		+ UC2/EMOC  
			+ Establish and Verify UC2 and EMOC Connection 
			+ Workflow 

		+ Force Level  
			+ Establish and Verify TBMCS-FL Connection 
			+ Workflow 
			+ PEX data passed to TBMCS-FL 

		+ Graduate Training Integration Management System \(GTIMS\)  
			+ Permissions 
			+ Establish and Verify GTIMS Connection 

		+ Central Scheduling Enterprise \(CSE\)  
			+ Overview 
			+ Permissions 
			+ Establish and Verify CSE Connection 
			+ Setup 
			+ Workflow 

		+ Scheduling Operations  
			+ TTPs 


	+ Labels 
	+ Locations  
		+ Concept 
		+ Existing Locations 
		+ Setup before I use the module 
		+ Add a location 
		+ Latitude and Longitude 
		+ Set Zulu Offset 
		+ Show in Dropdowns 
		+ Frequencies 
		+ Delete a location 

	+ Personnel  
		+ Personnel Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Controls 
			+ Workspace 

		+ Personnel Details by tab  
			+ Personnel 
			+ Details 
			+ Duties 
			+ Contact 
			+ Quals 
			+ Status 
			+ Supervision 
			+ Roster 
			+ Setup 

		+ Setup - Configure Personnel for your unit  
			+ Configure the display 
			+ Page Settings 
			+ Manage the Personnel list 
			+ Customize Dropdown Lists 
			+ Populate with your squadron's personnel 

		+ Add, Move, Import and Export Personnel  
			+ Transfer Personnel data 
			+ Personnel information import, export and move general information 
			+ \(I\) Add a person manually 
			+ \(II\) Import people or a person with an ARMS file 
			+ \(III\) Import individual personnel files from another PEX database 
			+ \(IV\) Export personnel data as a personnel file 
			+ \(V\) Move personnel data from one squadron to another squadron \(Change Squadron\) 

		+ Personnel TTPs  
			+ MDS and Crew Position 
			+ How users can view and update their own information 
			+ Remove a person leaving your unit 
			+ Guest Flyers 
			+ Build Unit Task Codes \(UTC\) in PEX 
			+ Handle Inbound Deployed Personnel in your PEX Database 


	+ Reports  
		+ Reports Overview  
			+ Introduction 
			+ Workspace 

		+ Manage and Use Reports  
			+ Import a Report 
			+ Delete a Report 
			+ View Uploaded Forms and Reports 
			+ Open and Populate Forms and Reports 


	+ Resources  
		+ Resources Basics  
			+ Introduction 
			+ Controls 
			+ Module Notes 
			+ Workspace 

		+ Manage Your Resources  
			+ Associate Resources to Types 
			+ Add a Group 
			+ Add Resources to a Group 
			+ Delete Resources from a Group 
			+ Delete a Group  
				+ Quick method 
				+ Recommended method 



	+ Squadrons  
		+ Squadrons Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Module Notes 
			+ Workspace 

		+ Setup - Associate organizations to your squadron 
		+ Add a Squadron 
		+ Squadrons Availability Periods 

	+ Squadrons – HQ Registration 
	+ TaskView - Import an Airspace Control Order \(ACO\)  
		+ Introduction 
		+ Import an ACO 
		+ Managing Imported Locations 

	+ Users and Permissions  
		+ Users and Permissions Basics  
			+ Introduction 
			+ Permissions 
			+ Rules 
			+ Workspace 
			+ Workflow 

		+ Manage User Accounts  
			+ Create Permission templates 
			+ Add a User account 
			+ Find users not logging in 
			+ Delete an account 
			+ Lock out a user from PEX 

		+ Manage Permission Roles  
			+ View all Users in a Role 
			+ Change a user’s permissions 
			+ Save a User’s permissions as a template for others 
			+ Create a Template from Scratch 
			+ Apply a Template to existing User 

		+ CAC and Windows Associations  
			+ Associate a user to their CAC 
			+ Associate a user to their Windows account 
			+ Joint Use Accounts 

		+ Permission Matrix 

	+ Validation  
		+ Configure Validation 
		+ Add, edit and delete Table entries 
		+ When you first add a squadron to PEX 
		+ Share Listings across squadrons 
		+ How the Sortie Type table differs 
		+ How the Personnel Commitment Types table differs 

	+ Getting Started for PEX Administrators 

+ Miscellaneous  
	+ Visibility Model 
	+ How to Configure SIPR to NIPR Connections 
	+ Filters  
		+ Filter Wizards 
		+ Funnel Filter Wizard 
		+ Magic Wand Filter Wizard 

	+ LAN Out Procedures  
		+ LAN Returns to Operation Procedures \(Single squadron, pick one\) 

	+ Use PEX While Entire Unit Deployed  
		+ Options  
			+ Option 1. Deploy and Use Home Station PEX 
			+ Option 2. Deploy with Your Database on Your Own Hardware 
			+ Option 3. Deploy with Your Database, Install on Host Hardware 
			+ Option 4. Add Your Unit to Existing PEX Database 

		+ Detailed Instructions  
			+ Option 1. Deploy and Use Home Station PEX 
			+ Option 2. Deploy with Your Database on Your Own Hardware 
			+ Option 3. Deploy with Your Database, Install on Host Hardware 
			+ Option 4. Add Your Unit to Existing PEX Database 


	+ Use PEX Deployed, Integrated Squadrons 
	+ Use PEX on NIPR and SIPR \(Deployed\) 
	+ Use Your Logo Instead of US DoD 
	+ Abbreviations and Acronyms 
	+ Users with Multiple CACs 
	+ Security Identifier  
		+ Change your Security Identifier



