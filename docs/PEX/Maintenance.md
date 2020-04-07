
# Maintenance

## Maintenance Basics

Introduction

The Maintenance module is the source of your units' aircraft data and functions as a link between operations and maintenance. It contains four modules.

1. Aircraft

The Aircraft module contains three tabs:

A.  The Aircraft tab lists your aircraft by Mission Design Series \(MDS\) and tail number, and assigns tail numbers to "owning" squadrons.

B.  The Status tab contains a status board to manage and display aircraft tail number statuses and discrepancies. You can use Aircraft to track other vehicles, such as trucks.

C.  The Setup tab configures the Maintenance module for your unit.

2. Aircraft Generation

The Aircraft Generation module allows you to track the completion of al tasks that must be performed to generate aircraft for an operation.

3. Reporting

4. Reports

Reports provides maintenance a daily list of which load items \(munitions, ammo, chaff, flares, etc.\) installed on aircraft. It also provides an AF Form 2407 to track schedule changes.

Permissions

Ops Ops

Flight

Ground

MX

Flying



Administrator Desk

SOF



Staff

Scheduling Scheduling Scheduling Hours

Aircraft

No

Read No

No

Generation Update

No Access No Access Read Only



Access Only Access

Access

Aircraft tab

Read Read Read

Read

Update

Only

Read Only Read Only Update



Only Only

Only

Status tab

Read Read Read

Read



Update

Only

Read Only Read Only Update



Only Only

Only

Setup tab

No

No

No

No



Update

Access

No Access No Access Update

Access Access

Access



367

Maintenance

Module Notes

* MDS is the type of aircraft, e.g., B-52H. Tail Number is the serial number of a particular airplane, e.g., 99-0001. This module can also be used to track other equipment \(vehicles, computers, etc.\), besides aircraft, by simply changing some labels.
* MDSs are PEX database wide. They are not by squadron. Your squadron can pick which MDSs to see in the Squadrons module.
* The tail number list is MDS and squadron specific. Highlight an MDS, then use the squadron drop-down located between the aircraft and tail number grids. The tail number grid will populate with the tail numbers assigned to that squadron and MDS.
Controls
Aircraft and Setup. Access these procedures by navigating to Maintenance > Aircraft and the relevant tab.
Status. Access these procedures by navigating to Maintenance > Aircraft > Status. The Status board opens in a new window.
Workspace

## Aircraft
Setup tab
Introduction
The Setup tab contains two sub-areas; the Settings and Lists used by your unit.
Workspace!(images/000103.png)
1. Settings. Select your unit's settings.
2. Lists. Manage which list items are used by your unit. Once created, list items are stored in the database Master List and associated to your unit.
3. Squadron selector.
4. View/Edit the Master List from the database. Associate a list item to your squadron if it exists, add it if it does not exist.
5. Send Selected Items to other squadrons. This aids in standardization between similar units.
Settings
This allows the Maintenance Status board to automatically show an aircraft's status as Landed at a set number of minutes past its scheduled land time.
Select your squadron. Use the rol er control to set the duration in minutes.
Lists
These items are displayed in other maintenance and scheduling modules. They can be created here or, if already in your database, pulled from the Master List. Once created, they are added to the Master List, and can be sent to other units in your database.
REMIS MDS. PEX populates a list of MDSs from the Reliability and Maintainability Information System \(REMIS\). Check the MDSs you need to view in the Aircraft tab > REMIS MDS dropdown list.
Configuration. Enter a set of aircraft configurations, i.e., all-cargo, distinguished visitor \(DV\), etc. It can also be used for simplified Standard Configuration Load \(SCL\) codes.
Status Code. Enter/select aircraft maintenance status codes such as "FMC" \(Fully Mission Capable\).
Select the appropriate color.
Priority. Enter your unit's mission Priority codes.!(images/000001.png)

Symbol. Enter/select aircraft maintenance status symbols such as "X" \(Major Discrepancy\). You can also enter Rankings for each.
Aircraft Parking Site. Enter your unit's aircraft parking spots. If desired, enter the elevation and Latitude/Longitude.
Organization. Enter units not listed in your PEX Locations module. For example, your unit is in temporary possession of an aircraft owned by another unit. This is displayed in the Aircraft tab > Tail Number grid.
Service. Enter/select Codes used by nonspecific groups of forces, such as AIR FORCES or COMBINED.
Aircraft tab
Introduction
This tab lists aircraft resources for display in other PEX modules and allows interfaces with other programs. Aircraft are listed by Mission Design Series \(MDS\) and associates individual tail numbers to those MDSs. Tail numbers are listed by owning squadron, and can be associated to shared squadrons. MDSs and Tail Numbers can be matched to their REMIS, ARMS, and Emoc identifications.
Workspace


1. Aircraft MDS. Create aircraft MDS designations in your database. Once created in the database, each MDS is available to any squadron by selecting Show MDS in Dropdowns in the Setup >
Squadrons module. Assigning tail numbers \(below\) to a squadron populates functionality in that squadron. Associate the MDS used in PEX to that used in ARMS, REMIS, and Emoc.
2. Squadron dropdown selector. Select the squadron to which you want to assign a tail number.
3. Tail Number. Create tail numbers in your database, in the owning squadron, and share them with other squadrons. In the example above, the 80 FS owns 80-2002, but 80-2002 can also be scheduled by the 35 FS. Associate the tail number used in PEX to that used in ARMS, REMIS, and Emoc. Designate owning and possessing organizations. Check which tail numbers to show in the assigned squadron's tail number dropdown list.
Add an MDS
1. In the MDS grid, right-click, select Add from the menu 370
2. In the MD column enter the aircraft’s Mission and Design, e.g. C-130
3. In the S column and enter the Series e.g. J
4. PEX wil combine these in the read-only MDS column, e.g. C-130J.
CAUTION: Do not attempt to circumvent this process by entering the entire MDS in the MD
box. Doing so will result in problems with the way MDSs are displayed in the various modules, forms, and reports in PEX.
5. Match the PEX MDS to the ARMS MDS. The ARMS designation is used on the AFTO 781.
NOTE. The CAMS MDS column is obsolete. Leave it blank.
6. The remaining columns are optional; however, Speed and Fuel Flow are necessary to use the Distance-Time-Fuel feature of the Mission Board.
Add a Tail Number
Adding a tail number is required for full MDS functionality.
1. Right-click and select Add
2. Type in the tail number and select the squadron that owns it 3. Select the squadrons that share it. This will allow other squadrons to schedule the tail number.
4. Enter the ARMS ID so it shows up correctly on ARMS documents 5. Enter data in the remaining columns as desired
6. Show in Drop-Down. This column allows you to hide tail numbers throughout PEX. This prevents schedulers from accidentally scheduling an aircraft that’s not available due to prolonged down time.
Move a Tail Number to Another Squadron
1. Pick the MDS
2. Select the squadron that owns the tail number
3. In the Tail Number grid, locate the tail number you want to move, and in the Squadron dropdown column, change the squadron to the gaining unit
4. When the screen refreshes, the tail number wil disappear 5. Change the squadron selector, just above the grid, to the gaining squadron, and you wil see the moved tail number.
CAUTION: Do not attempt to circumvent this process by adding a slightly-modified version of the same tail number in a different squadron. For example, don't have tail number 99-0001 in Squadron A and tail number 001 in Squadron B, when both are real y the same thing. If you 371
!(images/000093.png)

do this, later on when you want to see what tail number .. 01 is doing, you'll have to select it in multiple places and won't get an overall view, because PEX thinks they are two different airplanes. If more than one squadron needs to schedule the same tail number, instead of adding it separately to each squadron, share the tail number.


Status tab
Introduction
The Status board opens in a new window and contains displays three grids. The three grids can be moved, sized and closed independently.
Workspace


1. Refresh. The board refreshes automatically every ten minutes. It can also be refreshed manually. The Last Refresh field displays date and time, in local or Zulu, and Julian Date.
2. Mission Capable Rates. Mission Capable \(MC\), Fully Mission Capable \(FMC\), Partially Mission capable \(PMC\) and Not Mission Capable \(NMC\) rates are displayed as a percentage.
3. Page controls.
A. Labels allows for overwriting of existing column labels, or headers. For example, you can overwrite LOX with GOX.
B. Page Settings allows you to show or hide grids and functions. It also contains the Aircraft Status Output Service generation function.
C. Once the status board is configured, use Save Page Layout to save your display, or Restore Page Layout to return it to the original configuration.4. The Filter control is unique to maintenance and allows you to select one or more MDS, Squadron, Status, Actual Cfg and Actual SCL.
5. Status board. Data display can be configured as required. Status and Discrepancies can be updated here or in the grids below.
6. Status History. This grid can be configured and positioned independently of other the grids.
7. Discrepancy List. This grid can be configured and positioned independently of other the grids.
Status
The Status grid displays data on individual aircraft. Some data feeds from other modules. Status and Discrepancy data is added and updated via hyperlink in the Status grid or in the grids described below.
Status History
This grid displays current and historical status/condition data. Right-click to add new status data.
Click Edit to edit existing data.
Discrepancy List
This grid displays current and historical discrepancy data. Right-click to add new discrepancy data.
Click Edit to edit existing data. This wil not change the status data; it must be updated separately.

## Aircraft Generation

Aircraft Generation - Setup
Introduction
This module allows you to track the completion of all tasks that must be performed to generate aircraft for an operation.
Permission Roles
You need the Administrator role to setup the module. To monitor operations, you need the MX
Scheduler role. The Ops Staff role can view the module.
Setup
1. Add tasks. Tasks are a list of events that need to be accomplished in order to generate aircraft. Examples of these would be “Fuel”, “Weapons Load”, “Crew Acceptance”, etc.
A. Click the Add Task button or right click for the functionality. When adding a task enter Name, Default Duration in HH\+MM, and MDS. The task will be added as active and with your squadron selected as the squadron to “Show In”. If you want other squadrons to be able to use the tasks select those squadrons to “Show In”.B. Once the data is entered, you can either select “Save” to save the data and close the dialog or “Save & New” to add another task. You can Edit or Delete existing tasks by highlighting the task and selecting “Edit Task” or “Delete Task” from the toolbar action buttons or “Edit “ or “Delete” from the right-click context menu.
C. If a given squadron no longer uses a task, but other squadrons still need it, you can uncheck that squadron so they no longer see the task. In order to delete a Task, you must not have “visibility” or “active” selected for that Task.
2. Build flows. Flows are a combination of Tasks grouped together to be accomplished in a logical sequence when generating an aircraft. Examples of these would be “Install tanks” then
“fueling” etc.
A. Flows are added by selecting “Add Flow” from the toolbar action buttons or “Add” from the right-click context menu. When adding a flow, enter the Name. The Squadron dropdown filters the MDS list to be displayed. Once the MDS is selected, the available tasks for that MDS are populated in the left-hand grid. The Flow wil be added as active and with your squadron selected as the squadron to “Show In”. If you want other squadrons to be able to use the flow, select those squadrons to “Show In”.
B. To include a Task on a flow, drag-n-drop a Task from the Available Tasks list to the right-hand grid. You can also use the Ctrl key to multi-select and drag multiple tasks at one time.
Once the Tasks are added to the Flow, you can order them as applicable, again using drag-n-drop.
C. Once they are in the order you desire, select the Calculate Start/End Times to complete the process. By doing this, you wil see the start time, end time, and duration for each Task.
D. Once the data is entered, you can either select “Save” to save the data and close the dialog or “Save & New” to add another Flow.
E. You can make changes or delete a flow by highlighting it and selecting “Edit Flow” or
“Delete Flow” from the toolbar action buttons or “Edit “ or “Delete” from the right-click context menu.
F. You can add or remove flows from a squadron by checking/unchecking the appropriate box. In order to delete a Flow, you must not have “visibility” or “active” selected for that Flow.
3. Build a template. A template is a combination of Flows plus a specific number of aircraft.
The Flows within the template may be “Offset” from each other for a cascade start and also may be “Delayed” from the actual start of the Operation. Examples of templates would be “12-Aircraft Red Flag” and “18-PAA Deploy” etc. They can also be used for future exercises or operations.
A. Templates are added by selecting “Add Template” from the toolbar action buttons or
“Add” from the right-click context menu. The Template will be added as active and with your squadron selected as the squadron to “Show In”. If you want other squadrons to be able to use the template, select those squadrons to “Show In”.
B. To include a Flow on a Template, drag-n-drop a Flow from the Available Flows list to the right-hand grid. If you are going to use multiple instances of a Flow on the Template, you can enter that number in the “\# of Lines” and that number wil be added when you drag-n-drop that Flow. You can also use the Ctrl key to multi-select and drag multiple tasks at one time.C. Once the Flows are added to the Template, you can order them as applicable, again using drag-n-drop. Once they are in the order you desire, you can apply an Offset and/or Delay to the flows.
D. To apply an Offset and/or Delay, enter the desired Offset and/or Delay in the right-hand grid and using the Shift or Ctrl keys, select the Flows that you want them applied to. You can hover over the “Apply Offset/Delay” to see what will be applied in bold. If the Offset/Delay is correct select “Apply Offset/Delay” to apply.
E. Once the data is entered, you can either select “Save” to save the data and close the dialog or “Save & New” to add another Flow.
F. You can edit or delete a template by highlighting it and selecting “Edit Template” or
“Delete Template” from the toolbar action buttons or “Edit “or “Delete” from the right-click context menu. In order to delete a template you must not have “visibility” or “active”
selected for that template.
Aircraft Generation
Introduction
This module al ows you to track the completion of al tasks that must be performed to generate aircraft for an operation.
Permission Roles
You need the Administrator role to setup the module. To monitor operations, you need the MX
Scheduler role. The Ops Staff role can view the module.
Usage
1. When an operation starts that needs aircraft generation, go to the Operations tab and select Add Operation from the toolbar. Enter the Name, Start or End Time, and Squadron of the Operation.
2. Select the Template you want to use. If it does not exist, please refer to the Setup help topic that explains how to add a template.
3. The Operation timing will be calculated based on whether you selected Start time or End time. If you enter Start time, times wil start at the time you designated and run for the duration of the Operation. If you selected End time, the calculation wil show you when you need to start your Operation in order to finish when desired.
4. Monitor the Operation by selecting the Operation Details toolbar the More Options \(. .\) button. This wil open the Details page, which can be moved to another monitor and left open.
Additionally, you can set the refresh rate for this page.
5. On the Details page, you can see the complete Operation. Add the tail\# for each line using the dropdown. If there is an aircraft status in PEX it will be displayed in the Status column.
6. To track the Operation, enter the actual start and end times by clicking in the appropriate box and entering the time. If the actual time is on or before scheduled, the box wil highlight green. If the time entered is after the scheduled time, the box wil highlight red. If the Scheduled 375
time of the task passes with no Actual time having been entered, the Actual time field will turn yellow to help highlight the missing data.
7. You can edit the Operation by selecting the Edit Operation button in the upper left-hand corner. This allows you to edit the Name and Time of the Operation. You can choose to shift all times in the Operation at this point. Additionally, you can Add, Edit, or Delete Flows from the Operation using the toolbar More Options \(. .\) button. If you want to save the changed Operation as a new Aircraft Generation Template, select Save as New Generation Template in the lower right-hand corner.

## Handle Similar MDSs in PEX

\(For example, F-16A, F-16B, F-16C, and F-16D\)
1. Maintenance, Aircraft, MDSs. Each MDS should be entered individual y in the MDS grid, e.g., F-16A, F-16B, F-16C, and F-16D. Also, for exporting AFTO 781 data, the ARMS MDS, e.g., F016A, for each should be identified in this grid.
2. Maintenance, Aircraft, Tail Numbers. Each Tail Number should be assigned to its associated MDS, e.g., the F-16A Tail Numbers should be assigned to the F-16A and so forth. Also, for exporting AFTO 781 data, the ARMS ID for the tail number should be identified in this grid.
3. Setup, Personnel, Qualifications. If a person is qualified to fly in more than one MDS, each MDS should be identified in the Quals & Certs tab > MDS/CP Qualification grid. For example, if the person is an instructor pilot that can fly all four models of F-16, that person should be assigned MDS Qualifications of F-16A IP, F-16B IP, F-16C IP, and F-16D IP. The model that is most frequently flown should be marked as the “Primary” MDS/CP qualification.
4. Setup, Personnel, Certifications. Pick one of the similar MDSs and enter all the certifications there, e.g., enter al F-16 certifications under “F-16C”. As a technique, to indicate a person is also certified in other F-16 models, you could create an “F-16C” certification called “F-16A”, another called “F-16B”, and another called “F-16D”.
5. Scheduling, Flying Schedule, Sortie MDS. In the Sorties grid, in the MDS column, the desired MDS for the sortie should be identified. Once a Tail Number for the sortie is established, the true MDS should be updated, if required.
6. Stan Eval, Testing, QDBs and Exams. If the QDB/Exam pertains to multiple MDSs, associate the QDB/Exam to all applicable MDSs simultaneously. For example, if a QDB/Exam applies to all types of F-16, associate it to F-16A, F-16B, F-16C, and F-16D.
7. Stan Eval, Management, Setup, Assoc Eval Types & Reqs. Select the first MDS, e.g., F-16A, and enter the Eval Types and Requisites for it. Do the same for the other MDSs, e.g., F-16B, F-16C, and F-16D. Normally, the Eval Types and Requisites will match for each MDS.
8. Stan Eval, Management, Qualifications. Add a qualification for each MDS the person is authorized to fly. For example, if an Instrument evaluation in the F-16C also qualifies the person for Instrument in the other F-16s, enter an Instrument qualification in all four, i.e., F-16A, F-16B, F-16C, and F-16D. Each qualification should have the same “Last Evaluation” date.
9. Stan Eval, Management, Open Evaluations. When adding an Open Evaluation, make sure to identify which MDS\(s\) also get updated as a result of the primary evaluation. For example, the Instrument evaluation may be conducted in the F-16D and it “Also Updates” the F-16A, F-16B, and F-16C.10. Stan Eval, FCIF Admin. If the read file item pertains to multiple MDSs, associate the read file item to all applicable MDSs simultaneously. For example, if an item applies to all types of F-16, associate it to F-16A, F-16B, F-16C, and F-16D.
11. Ops, Go/No-Go. If the above procedures are fol owed, the Go/No-Go page will display the correct data for Testing, FCIF, and Stan Eval, whether the page is filtered by MDS/CP, Msn/Sortie, or by Shift.
12. AFTO 781. If the above procedures are followed, the AFTO 781 data will export correctly to the ARMS database.

## Maintenance Reports

Daily MX Loads
Introduction
This report provides maintenance a daily list of which load items \(munitions, ammo, chaff, flares, etc.\) to install on the aircraft. The report is found at Maintenance> Reports> Daily MX Loads.
Permission Roles
To view/print this report, you need Flight Scheduler, Maintenance Scheduler, OPS Desk, Supervisor of Flying, or OPS Staff permission role.
Before using the report
1. To get data to show up in the ECM, LANTIRN, NACTS, OTHER, AMMO, CHAFF, or FLARES
columns, you first must have Load Item Types of ECM, LANTIRN, NACTS, Other, Ammo, Chaff, and/or Flares in the Weapons > Munitions > Setup list. Then, specific Load Items must be categorized as one of those as the Load Item Types. Finally, schedule that particular Load Item onto a sortie station using the Flying Schedule> Loads tab.
2. The report works best when Load Items are entered as Code numbers and names. The Load Item Name would be the plain text definition, e.g., Code = 46 and Name = Mk-82 Hi Drag.
3. To minimize confusion, we recommend using distinct load item Codes/Names even across different types of load items. For example, don’ t have load item code "42” which is an AIM-9
missile and another load item code "42” which is a travel pod. However, if you do use the same load item code/name across different types, the bottom legend will list which specific load item goes on which line number.
Run the report
1. Pick whether you want the report ordered with formations together or just strictly by MX
Line \#. Spare aircraft \(any line number which includes the letters "SP”\) are listed at the bottom.
2. Pick whether you want the report to list al stations for the MDS or just the ones that have something on them \(Populated Stations\). Although Populated Stations shortens the report greatly, some people become confused when they don’t see al the stations listed \(the empty ones\), so you have an option.
3. Pick the date range of interest and whether you want times in Local or Zulu.4. Pick whether you want the Load Item Code shown vertically \(for long ones\) or horizontally \(for short ones\).
5. Pick the Squadron\(s\), MDS\(s\), and Munition Project Number\(s\) of interest.
6. Pick the columns of interest. If you select for display the following columns: ECM, LANTIRN, NACTS, or OTHER; the load items of those types wil appear under those columns and not under a station. If you want those types of load items to appear under the station, do not select the ECM, LANTIRN, NACTS, or OTHER columns for display.
7. Click PDF or Excel to generate the report.
NOTE: Depending on your Excel trust center settings, on the Windows File Download dialog you may need to Save the report first instead of Opening it directly.
Weekly Frag Request
Introduction
This report is provided by Ops to munitions personnel to specify how many of each load item are scheduled by day, for five days. The report is found at Maintenance > Reports > Weekly Frag Request.
Permission Roles
To view/print this report the user needs Flight Scheduler, Maintenance Scheduler, OPS Desk, Supervisor of Flying, or OPS Staff role.
Before using the report
CRC: Complete Round Codes \(CRC\) are entered in the Weapons module by editing the individual Load Item. This is a one-time setup step.
Setting: Settings are entered in the Flying Schedule module on each sortie Station. When you enter station Settings, those settings will appear for every Load Item on that Station on the Weekly Frag Request. Settings are normal y fuse settings.
Mount:
* To setup mounts and/or pylons, enter “Mount” \(case sensitive\) as a Load Item Type. Then add your specific mounts and/or pylons as Load Items, making sure to select “Mount” as the Load Item Type. This is a one-time setup step.
* To schedule mounts and/or pylons, add the mount/pylon as a normal load item to a station.
Then, onto the same station, schedule other load items that wil be attached to the mount/pylon. On the Frag Report, each load item will now list the mount/pylon “Description”
\(not Name\) in the Mount column of the report.
Run the report
Pick the start date of the five-day range and whether you want times in Local or Zulu.
Pick the MDSs, Munition Project Numbers, Categories, and Load Item Types of interest.
Select PDF or Excel to generate the report.NOTE: Depending on your Excel trust center settings, you may need to "Save" the report first, as the
“Open" option may be blocked our will generate an Excel error message.
Munitions grouping
The report groups load items by Squadron, Munition Project Number, and MDS.
Quantity \(Qty\) and Spare \(Sp\) calculations
The Qty column shows the number of that particular load item scheduled for that day on primary aircraft. The Sp column shows the number of that particular load item scheduled for that day on spare aircraft \(line numbers which include "Sp."\). The TOTAL column at the end shows the total of that particular load item scheduled for that week on primary aircraft plus the last \(not total\) Spare quantity for the week. In other words, the TOTAL column does not add up al the Sp for the week but uses the last daily value.
AF 2407, Weekly/Daily Flying Schedule Coordination
Introduction
The PEX AF Form 2407 documents mission changes.
Permission Roles
To view/print this form the user needs Flight Scheduler, Maintenance Scheduler, OPS Desk, Supervisor of Flying, or OPS Staff role.
Setup
You must use the Mission Board to Commit \(firm\) missions. From then on, when changes are made to squadron-specified fields on a committed mission, PEX allows you to enter information about why the change was made. This change information wil show up on the 2407.
Generate the form
Navigate to Maintenance > Reports > AF 2407 tab. Select your desired squadron and the schedule changes you want on the form.
Data sources
AF 2407
Field Mission Board Mission Change Field
Date and Time initiated N/A. Data comes from system time when form is created Initiated by
From “Authorized By” field
Equipment Affected
From “Item Affected” field
Schedule Change
From “Description” field
Effective date
From “Date” field

Notification Agencies, Names, and Times can be filled out via a template so this information doesn’t have to be entered every time the form is generated. You access/create template\(s\) from the same dialog where you initially make your selections for which data will go on the form.
Signatures
The form is enabled for digital CAC signatures for the Operations Scheduling Officer and the Maintenance Control Supervisor.!(images/000047.jpg)

Setup
External Interfaces
Scheduling Interface Introduction
Overview
The Setup > External Interfaces module serves as a consolidated location to establish, manage and monitor data-exchange connections between PEX and other scheduling applications, including: 1. Unit Command and Control \(UC2\)
2. Enhanced Maintenance Operations Center \(EMOC\)
3. Theater Battle Management Core Systems-Force Level \(TBMCS-FL\) 4. Graduate Training Integration Management System \(GTIMS\) 5. Central Scheduling Enterprise \(CSE\)
UC2, EMOC and TBMCS-Force Level
Some locations conduct squadron operations using PEX while conducting various wing operations using UC2, EMOC, and TBMCS-FL. Data is shared between systems allowing PEX users access to relevant information. If properly configured and operated, the end result is a reduced reporting burden on the squadrons and enhanced communication to higher headquarters. UC2/EMOC
maintains aircraft and aircraft status data. Updated data are exchanged between PEX and UC2, while EMOC can update both PEX and UC2. PEX does not directly update EMOC, although PEX can update UC2 which then flows EMOC.
NOTES:
* In PEX, connectivity is established between these four systems \(PEX, UC2, EMOC and TBMCS-FL\) in two tabs. Once established however, operations in PEX appear seamless to schedulers.
* Not all data flows to each program.
* Typically, an AOR/AOC will have a single TBMCS-FL database, while an individual location may have one UC2 database and multiple PEX databases.
GTIMS
PEX imports scheduling data from GTIMS and displays the information in the Ops > Waterfall
module.!(images/000021.jpg)

!(images/000107.jpg)