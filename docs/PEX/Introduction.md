# Patriot Excalibur Operations Management Software
>AFLCMC/HBBC (PEX)  
>1030 Titan Court  
>Fort Walton Beach, FL 32547  
>helpdesk@pexmain.com  
>Commercial (850) 337-2727  
>https://home.pexmain.com

## What is PEX?

PEX, developed by USAF AFMC AFLCMC/HBBD, is a software suite of applications that coordinates the Scheduling, Training, Stan Eval, and Aircraft Status activities of unit-level operational military aerospace units, such as aeromedical, air control, air operations centers, flying, ICBM, intelligence, joint terminal air control, pararescue, and security forces units. PEX is used to facilitate data sharing across the functional areas in a squadron, and is used worldwide by over 1000 squadron level units, including all AF MAJCOMs, Australia, and Poland.

---

## Log In

To use PEX, you must first log in. To log in, you must either be at a computer which has the **WinPEX** client installed \(double-click the desktop launch icon\) or use a web browser and navigate to **ePEX** web application. Both WinPEX and ePEX take you to the same PEX database. Functionally, ePEX is the same as PEX, except for the flight scheduling aspects. All offices, except flight scheduling, should use ePEX and instead use the WinPEX-only Mission Board.

!!! note "Note"
    Both WinPEX and ePEX take you to the same database.

To login to ePEX, navigate to the login page via a web address \(URL\) that’s provided to you via an email, link, in some sort of squadron/group/wing web page, or some other means of distributing a URL. At the login page, accept the consent banner, verify the name listed in the `Connect To:` button, and click the login button. If you’re able to login to more than one database, clicking the `connect to:` dropdown will provide a list of those databases. Select the appropriate name and click `login.` The last database that you’ve successfully logged into will be the defaulted name for your subsequent logins.

If no connections are listed in ePEX, contact your local PexAdmin and let them know that you have no connections available. They in turn wil configure the ePEX server for the necessary connections.

**Logging into WinPEX as a machine administrator:** If you’re a machine administrator, you have the ability to import the connection file for all user profiles of a machine. Click the WinPEX icon, dismiss the CAUTION about the missing connection file, accept the consent message, and at the login dialog click `import connections file.` Select Save as all users radio button. Navigate to the configuration file and save it accepting the default file name and location.

After this the connect to button will populate for all existing user profiles on that machine.

!!! caution "caution"
    Do not change the default file name or save location. This will prevent you from logging in.

**Logging into WinPEX as a non-privileged user:** You’ll need to import a configuration file the first time you login after migration. This file should be sent to you by your PEX Administrator. Click the WinPEX icon, dismiss the CAUTION about the missing connection file, accept the consent message, and at the login dialog click `import connections file`. Select Save as current user radio button. Navigate to the configuration file and save it accepting the default file name and location.

!!! caution "Caution"
    Do not change the default file name or save location. This will prevent you from logging in.

!!! note "Note"
    If you don’t have machine administrator permissions, selecting `all users` radio button will fail to a message letting you know you don’t have the necessary rights to instal the file for other users.

Once the file saves, you should now see the database name listed in the `connect to:` dropdown. Select it and click login to start using WinPEX. . If you’re able to login to more than one database, clicking the `connect to:` dropdown will provide a list of those databases. Select the appropriate name and click `login.` The last database that you’ve successful logged into wil be the defaulted name for your subsequent logins.

!!! note "Note"
    If no database name is visible in the dropdown, this means a PEX account has not been set up for you, or there’s something wrong with the PEX service host. Contact your local PEX administrator for assistance.

!!! note "Note"
    If you have multiple login accounts in a database, they’ll show up after you hit the login button just like they’ve done before the new login procedure.

If you have existing connections file and you’re sent a new one, click the import connections file and navigate to the new file. Once the file is selected you’l be asked if you want to overwrite or merge the existing file. Selecting `overwrite` will erase existing connections and the file wil be overwritten with the connections from the new file. Selecting `merge` wil retain existing connections and adds the content of the new file.

!!! caution "Caution"
    Exiting WinPEX could be as simple as closing the program with the red X close icon in the upper right hand corner of the screen. You are cautioned to not use this technique but rather to close the individual modules \(applications\) running within the client and then use the file menu item `Logout`. This is to ensure there are no applications running in the background which would remain connected to the database and server.

---

## New in 5.16.1

**21-August-2019**

**Ops**

**Go / No-Go**

* Select the number of persons displayed per page.

**Training, Continuation**

**Web Service ARMS**

* Connect PEX to ARMS via web services. This allows direct transfer of data between PEX and ARMS without using ARMS-generated CSV files, or exporting training or AFTO 781 data via ODAC. This topic, **PEX-ARMS Interface**, encompasses the entire Continuation Training > ARMS tab and should be reviewed in its entirety.

**Training, Mission**

**Most Common Grades on a Course**

* On a course, copy up to five common grades to another course.
* Courses with customized common grades are indicated as such in Overview > Courses.
* Course gradesheets with customized common grades present those grades first and allow any grade on tasks. 

**Scheduler Reports**

**ICBM Reports**

* The Missile Operations Personnel Schedule and Missile Operations Locations Schedule reports and report functionality are updated.

### WinPEX Menu

**File**

* Show Tabs When selected, displays tabs in bottom portion of Container to indicate open modules. Select again to hide tabs.
* Show Navigation Bar Used after the Navigation Bar is hidden to bring it back up. To hide the Navigation Bar, use the ”X” \(close\) icon in the upper-right corner of the Navigation Bar.
* Print Setup Brings up standard MS Windows Print Setup dialog.
* Login brings up the PEX Login dialog and allows you to sign in at the container level so you don’t have to sign in every time a different PEX module \(e.g., Mission Board\) is opened.
* Logout signs off the current PEX user without closing PEX. To subsequently open a PEX application from the container requires another Login. Once logged in to any PEX application, as long as you keep one PEX application running no further PEX Logins are required.
* Pane Options - No longer used.
* Exit PEX closes Patriot Excalibur.

**Edit**  
See the module-specific Menu help topic for a list of functions.

**View**

* Status Bar is no longer used. The Status Bar remains on to allow the WinPEX menu to resemble the ePEX menu.

* Refresh regenerates the screen displayed to present the most current information. This option is useful when the screen does not display a previous successful entry on a different screen.

**Tools**

**Window**

* Cascade lays windows on top of each other
* Tile lays windows side-by-side

**Help**

* Help Topics is no longer functional in WinPEX, use the Navigation Menu: Support, Help.
* About PEX brings up a dialog listing software version.
  
### New PEX Modules

All PEX modules will be rewritten in more advanced computer languages as they become available. The traditional menu commands in newer PEX modules have been replaced or supplemented by right-click "context" menus. PEX context menus perform a function in the grid where the mouse pointer is located when right clicked. A PEX grid is an area on the display with column headers, columns, and rows. The context menus include standard commands found in each of the new modules plus commands unique to the module in use. The standard commands are:

* _Add_ - Adds a record to the current grid.
* _Delete_ - Deletes the highlighted record of the current grid.
* _Grid Settings_ - Allows you to hide or unhide columns, change the font size, or number of records to display per page for the current grid.
* _Save Layout_ - Saves the changes you have made to the screen layout.
* _Restore to Original_ - Returns the screen layout to the default layout.
* _Export to Excel_ - Exports the grid to Excel \(if installed\).
* _Print Grid_ - Prints the grid \(if a printer is installed\).
* _Filter Grid_ - Filters the data based on a Column and user-entered text.

---

## PEX Environment

PEX operates in an M$ Windows environment.

**Dark Gray Column Headings**. Column headings that are a darker shade of gray than the others in a grid denote required entries before a particular line of data \(record\) can be saved to the database.

**Right-clicking**. PEX makes extensive use of the right-click feature of the mouse, normally to add and delete data or to bring up menu items.

**Refresh Icon**. With multiple windows \(e.g., Mission Board, Resources Rainbow\) open simultaneously, a change on one will not update the other\(s\) unless the other\(s\) are ”refreshed.” The Refresh Icon is available on all windows for this purpose.

**Saving Data**. To save data to the PEX database, it is not necessary to use a ”File, Save” type command as in MS Word or Excel. Once the required fields \(indicated by dark gray column headings\) in a line of data \(record\) are entered, all that is necessary to save the data is to click off the line of data to another line.

**Sorting Columns**. Most columns within PEX can be sorted in ascending or descending order by clicking on the column heading. Only one column can be chosen to sort at a time. The sorted column will rearrange the order of the remaining columns in the grid. You cannot add a new record once the columns have been sorted until you exit and reenter the application.

**ToolTip Notations**. On numerous controls throughout PEX, if the cursor is rested on a control for a couple of seconds a ToolTip notation will appear with additional data associated with that control.

**Light Gray Shading**. If a data field is shaded light-gray, that indicates the field is non-editable.

**Line Highlighting for Selected Items**. To change the color used for highlighting selected items on your computer: right-click on your Desktop, select Properties, Appearance Tab, Item drop-down, Selected Items, and Color dropdown. Select a new color for the Item and Font. Click OK.

---

## How to use PEX Help

PEX modules are designed for specific functions and each has its own look and feel. Corresponding help files are written based on a particular module and vary in format. The following descriptions apply as required.

Module help topics provide:

**Introduction**

Provides a brief overview of the module; the intent, what it is used for, and how it is used in a unit. 

**Permissions**  
What roles can access \(read\) and what roles can edit \(update\) the module. For example, "any user, including Basic User, can access and view the module" or "role X can update this and that."

**Rules**  
Business rules hard-wired into PEX. For example, "an evaluator cannot grade his own worksheet." 

**Module Notes**  
General notes, covering the entire module, considered essential to emphasize those not immediately obvious to the user. 

**Controls**  
Path to the described topic.

**Workspace**  
Control locations and the control's basic function.

**Workflow**  
Visually describes, in flowchart form, how to progress through the module with numbered call outs. Call outs are briefly described below the image. 

**Setup**  
How to configure the module for your unit.

**Processes**  
Descriptive individual use cases and processes that can be accomplished in the module. These may be a single topic or multiple topics, depending on the complexity of the module. 

**Key words explained**

!!! tip "Tip"
     Tips are tweaks and common practices not described elsewhere. "Gotchas" that don't fall into other categories, typically learned from experience in the lab, field or help desk.

!!! note "note"
     Indicates operating procedures, techniques, etc. Considered essential to emphasize.

!!! caution "Caution"
     Indicates operating procedures, techniques, etc., which could result in an operating deficiency if not carefully followed. Something that can be reversed.

!!! danger "Warning"
    Indicates operating procedures, techniques, etc. which could result in an irreversible condition or permanent loss of data if not carefully followed. Something that cannot be reversed.

!!! bug "Bug"
     A known bug or software issue.

**Header and Title Formats**

# Heading 1

Title of the module or top-level topic.

## Heading 2

A tab name, major control, or link.

### Heading 3

A primary page or header within a topic.

**Heading 4**

A breakdown of a major sub-topic within a module.

---
