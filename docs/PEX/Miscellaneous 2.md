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

### Abbreviations and Acronyms 

| Abbreviation | Full Name                 |
|--------------|---------------------------|
| Acc          | Accomplished              |
| Act          | Actual                    |
| AFTO         | Air Force Technical Order |
| AR           | Air Refueling             |
| Acft | Aircraft |
| API | Aircrew Position Indicator |
| A/S | Airspace |
| ACO | Airspace Control Order |
| ATO | AirSpace Tasking Order |
| Alt | Altitude |
| Asc | Ascending |
| Assoc | Associate |
| Att | Attempts |
| Avail | Availability |
| Calc | Calculation |
| Cnx | Cancelled |
| Cat | Category |
| Cert | Certification |
| Civ | Civilian |
| Cmdr | Commander |
| Cnfg | Configuration |
| Cont Tng or CT | Continuation Training |
| Cont'd | Continued |
| Cntl | Control |
| CAFSC | Control Air Force Specialty Code |
| Coord | Coordinating |
| CP | Crew Position |
| Curr | Currency |
| Dt | Date |
| Decert | Decertification |
| Dep | Deputy |
| Desc | Descending |
| Dist | Distance |
| Dur | Duration |
| DAFSC | Duty Air Force Specialty Code |
| Eng | Engine |
| Eval | Evaluation |
| Exp | Experience |
| Exp Ind | Experience Indicator |
| Expire | Expiration |
| Flt | Flight |
| Freq | Frequency |
| Hrs | Hours |
| Ind | Indicator |
| INIT | Initial |
| INSTR | Instructor |
| Intel | Intelligence |
| Know Lvl | Knowledge Level |
| Ltr | Letter |
| LoX | Letter of Xs |
| Loc | Location |
| Mx | Maintenance |
| Max | Maximum |
| Min | Minimum |
| Msn | Mission |
| MPS | Mission Planning Sheet |
| Msn Rdy Status | Mission Ready Status |
| Oper | Operator |
| Org | Organization |
| Passport Exp | Passport Expiration Date |
| Per | Period |
| Pt | Point |
| PQI | Position Qualification Indicator |
| Pri | Primary |
| PAFSC | Primary Air Force Specialty Code |
| Pri | Priority |
| Pro | Proficiency |
| Pro Lvl | Proficiency Level |
| Proj Loss | Projected Loss |
| Qual | Qualification |
| Qual Code | Qualification Code |
| Qual Tng | Qualification Training |
| Rdy | Ready |
| Rsn | Reason |
| Rcvr | Receiver |
| Recert | Recertification |
| Rem | Remaining |
| Rmks | Remarks |
| RQ | Requalification |
| Req | Request |
| Req | Require |
| Req | Requisite |
| Rev | Reverse |
| Sched | Scheduled |
| Sec | Secondary |
| Sec | Security |
| SAPM | Self--Assessment Program Manager |
| Seq | Sequence |
| Sig | Signature |
| SIM | Simulator |
| Sp | Spare |
| SEI | Special Experience Identifier |
| Sq | Squadron |
| Stan | Standardization |
| St | Start |
| T/O | Takeoff |
| Tnkr | Tanker |
| Trnr | Trainer |
| Tng | Training |
| UMD | Unit Manning Document |
| UTC | Unit Task Code |
| Vol | Volume |
| Warn | Warning |
| WX | Weather |
| WX Cat | Weather Category |

### Users with Multiple CACs 

You may encounter users with multiple ways to logon to the network domain, usual y through one of two Common Access Cards \(CAC\). This typically happens in Reserve or Guard units when a person has a crewmember CAC and another contractor CAC. The question arises, which CAC should be associated to their PEX account? 

Our recommendations: 

* This individual should be identified in the Personnel module only once. 

* This individual should be identified in the Users module only once. 

* The Person and User should be associated in the Users module. 

* The User should be associated to only one network account \(CAC\) in the Users module. That CAC should be the one they use the most. When they use the other CAC to logon the network, they would not be able to logon to PEX. 

!!! Caution CAUTION
    Despite our recommendation, if you think the individual really needs to access PEX using both network accounts \(CACs\), then: 

    * This individual should be identified in the Users module twice. 

    * Each User should be associated to only one network account (CAC) in the Users module. 

    * This individual should be identified in the Personnel module only once. 

    * Associate one user account (the military one) with the Personnel record. 

    * Do not associate the other user account \(the contractor one\) with any Personnel record. 

    * Via policy (PEX can’t enforce this), one User/Person combination should be used to manage the individual’s schedule, training, and Stan Eval. The other User account would be used for the individual to accomplish PEX administrative duties, for example. 


### Security Identifier 

The PEX Security Identifier is used to sign off FCIFs, proctor tests, and pilot review AFTO 781s. The Security Identifier is defaulted to the person’s ID number \(typically, the Social Security Number\). The Security Identifier can be changed only by the user and requires six to nine characters, case-sensitive. 

Change your Security Identifier 

1.  From My Page, click My Preferences. 

2.  In the Security Identifier fields, enter 6-9 characters and re-enter the same characters to confirm your change. Using the same number as your CAC PIN, so you don’t have to remember another password, is acceptable. 

3.  Click Save Preferences. 

If you forget your Security Identifier, click the “Reset to Personal ID Number” button. This resets your Security Identifier to the Personal ID Number \(usual y SSN\) saved in the Personnel module. 
