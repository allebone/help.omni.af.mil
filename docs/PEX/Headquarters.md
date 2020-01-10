# Headquarters

## Headquarters Overview

**Introduction**  
The Headquarters \(HQ\) module is installed separately from regular PEX. See the PEX Install Guide for instructions. The HQ module should be instaled for use by MAJCOM HQs. It should not be installed at wing or squadron level. The HQ module is used by a HQ training office or functional manager to create a standardized set of Continuation Training tasks for subordinate units. It is also used to roll up Continuation Training and Scheduling data from subordinate units.

**Controls**  
Access these procedures by navigating to Headquarters. This wil not be present if not installed at your location. 

**Build Continuation Training tasks for units**  
Once the Headquarters module is installed, navigate to Headquarters > Training > Setup, and build Continuation Training tasks just like a local unit would. See the [Continuation Training Setup](Training.md#Continuation-Training) help topic for detailed instructions.

**Send Continuation Training tasks to units**  
When you are done building the Continuation Training tasks and are ready to provide them to subordinate units:

1. Check the desired Tasks
2. Right-click in the Training Tasks grid
3. Select Export Selected Tasks and Save.
4. PEX will generate a .dat file, with a Date Time stamp. An example filename is _HQEvents-20160609014825.dat_
5. Send this file to your subordinate units and have them follow the [Configure Continuation Training]() help topic instructions.

Now that your units have a standardized Continuation Training task list, you will be able to see how they are all doing in Continuation Training.

**Register units with the HQ system**  
Your units need to register with your HQ system.

1. Send the units your HQ ePEX URL address and have them follow the Squadrons – HQ Registration help topic instructions. If you do not know the URL address, contact Comm. Go to Headquarters > Registered Units to see the registration status of your units.
2. When a squadron has registered, a new row will appear and the Status field will show Waiting.
3. To approve the squadron registration, highlight the row, click in the Waiting field, and select from the dropdown - Approved.
4. Click off the row to save.

The squadron is now registered and can start pushing Continuation Training or Scheduling data to the HQ. The only editable field on this page is Status. All other data comes from the unit level.

## Build Continuation Training Tasks

**Introduction**  
This module is used to create a set of standard training tasks that can be exported into a file and sent to subordinate units.

!!! note "Note"
    Once a subordinate unit imports these tasks, they cannot be edited. That is by design, to ensure standardization.

**Build HQ Continuation Training Unit Tasks**

1. Login as PexAdmin. Only PexAdmin can build the tasks.
2. In ePEX \(only\), go to Headquarters > Continuation Tng Tasks > Setup tab.
3. Build the tasks just like building them outside of the HQ module. Instructions are found in the [Configure Continuation]() Training help topic.

**Export the tasks to a file**  
When your tasks are built, check the boxes for the tasks you want to export \(select the box in the header to select all tasks\). Right-click and select Export Selected Tasks. The resulting file can be distributed to subordinate units via email or download from a website.

**Import TACTICS data**  
TACTICS is software used by the Joint Terminal Air Control \(JTAC\) community to track training.

TACTICS data can be imported into PEX. To do so, a HQ Continuation Training Unit Task file needs to be built to mirror the training tasks in TACTICS. Using the TACTICS export file as a reference, the PEX Unit Task ID would be element \#6, e.g., “C00439”. The Task ID must match exactly. The PEX Unit Task \(name\) would be element \#7, e.g., “1. Mission Organization of NAF/Group/Unit”. The name does not have to match exactly and could be shortened, e.g., “1. Msn Org NAF/Group/Unit”. For more see [TACTICS - Track JTAC Training]().  

## Rollup Continuation Training Tasks

**Introduction**  
The Headquarters > Continuation Training Rollup pages are used by a HQ training functional manager for oversight of subordinate unit Continuation Training. PEX refers to HQ as MAJCOM and subordinate units as Squadrons. The module allows the MAJCOM Training FM to view the most current training progress for all squadrons which are registered, approved, and sending Continuation Training data to MAJCOM.

!!! note "Note"
    Access to the HQ module is controlled. Contact the PEX Help Desk to get a copy of the instruction, “How to Enable the Headquarters Module”.

**Navigation**  
From the PEX menu, select Headquarters > Continuation Tng Roll up. The page has two tabs: Overview and Tasks. In the Overview tab, you will create views that display the training data in which you are interested.

**Use the rollup**

* Create a view on the Continuation Training Rollup Overview tab

    1. Click the Add View Button.
    2. Enter a Name.
    3. Click Save.

The new view appears on the left. The column grid may be hidden by clicking the `<` symbol far upper left. The full page is ready to Add Status to this new View. As multiple Views are added, they may be edited or deleted by highlighting the View and selecting Edit View or Delete View.

* Add a status to a view

    1. Select the view.
    2. Click the Add Status button.
    3. The Add Status Wizard opens.
    4. Select the desired items using the four-step, self-guiding selection tool. Asterisked \(\*\) items are required entries and must be selected in order to Save and display a Continuation Training Status Rollup.

        * All \*Squadron\(s\) that are registered and approved with the MAJCOM, and to which the PEX user has permissions to see, appear in the first grid column. Select one squadron, or multi-select squadrons for the Status rollup, according to user requirements. - \*Task Type is single-select only; Currency, Proficiency and One Time. Selecting Currency or Proficiency will also return any Currency/Proficiency Task Types in Step 2 of the Wizard that match the selected criteria in Step 1. - Select one or more Task Source\(s\) - Select one or more Task Category\(s\) \(Next >\).
        * Select one or more \*Task\(s\) \(Next >\).
        * Select applicable MDS\(s\) and Crew Position\(s\), and Mission Ready Status\(es\) \(Next >\).
        * \*Threshold\(s\) may be applied for Currency and One Time Task Types. Click `What's this` for Thresholds Explained. Review Your Selections allows the user to see what was previously selected, change any selections if required, and is helpful in applying a distinguishing Name to the Status Rollup
        * Finally, \*Name the Status and the Save button becomes active and selectable. Click `Save`.

The Continuation Training Rollup Status now displays within the View. To interpret the data returned click the multi-color box icon, upper right, to open the Legend which will breakdown what the different colors represent.

**Edit a status in a view**

1. Click to highlight the Status row.
2. Click the Edit Status button.
3. The Edit Status wizard is opened.
4. Edit the desired items using the four-step, self-guiding selection tool. \*Asterisked items are required entries and must be selected in order to Save and display a Continuation Training Status Rollup. The selection options are the same as adding a status.

**Delete a status in a view**

1. Click to highlight the Status row.
2. Click the Delete Status button and confirm the deletion.

**View status details**

1. Click on the name of the status \(the name is a hyperlink\). 
2. The Status Details open displaying a breakout of the Continuation Training Rollup.

**Get the latest data**

1. Click the clock icon to the upper right; Squadron\(s\) Last Updated info is displayed. This tells the user how current the Continuation Training data is.
2. Click the refresh icon for a manual refresh.

**Use the Tasks page**
This page allows you another option for filtering, selecting and displaying Squadron Continuation Training data.

1. Initiate the Task Criteria selection dialog by hovering the mouse in the left grid column;`Click to launch selection dialog` tooltip appears.
2. Left mouse click and the Task Criteria selection dialog box opens. As with the Add Status Wizard on the Overview page, this is a self-guiding selection tool.
3. Selection a Squadron\(s\), which again are single or multi-selectable.
4. Click Load and a single Continuation Training Rollup snapshot is provided and labeled with the Task Type selected.
5. Further rollups are created by hovering the mouse in the left grid column and re-initiating the "Click to launch selection dialog" tooltip and Task Criteria dialog box. Each Tasks Rollup is created successively and not saved.

The Last Updated, Legend, and Refresh buttons on the upper right are the same as on the Overview page.
