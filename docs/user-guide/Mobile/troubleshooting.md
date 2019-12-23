
# Troubleshooting Sync Problems

## *"My Pubs Won’t Sync!”*
![](img/syncissue.png)

----

## Step 1: Are you connected to BOCKSCAR?

GoodReader Syncing only works when you’re connected to a BOCKSCAR Wi-Fi Access Point. You’ll be unable to syn when connected to any other Wi-Fi (e.g. home, billeting, starbucks, etc).


 1. Tap the **iOS Settings** icon. Image result for ios settings icon
 2. Make sure that Airplane Mode is turned off and that Wi-Fi is turned on.
 3. Connect to the BOCKSCAR Wi-Fi network.
 ![](img/wifi.png)  

----

## Step 2: Is a VPN Enabled?

Some VPNs can stop GoodReader from properly syncing.

 1. Tap the **iOS Settings** icon. Image result for ios settings icon
 2. If the VPN setting exists, ensure that the connection is not enabled.
 3. Open GoodReader and try to sync. If you still get an error, continue below to step 3.

----
 
## Step 3: GoodReader Sync Settings

If GoodReader still won’t sync, you can clear and re-add the synced folder.

 1. Open **GoodReader**.
 ![](img/goodreader.png)

 2. Tap the **Connect** button on the main screen. <br>
 ![](img/connect.png)

 3. Tap to highlight **Sync Records**.

 4. If a Sync Record called 55_OG is listed, tap the **trash can** icon to the right to delete the Sync Record. If there are no saved Sync Servers to delete, just go on to the next step.
 ![](img/trash.png)

 5. Tap to highlight **Saved Servers**. If BOCKSCAR is listed, tap the **gear** icon to the right of it and go to step 7. If it is not listed, tap the plus sign `+` to add a server.
 ![](img/add.png)

 6. Select WebDAV Server.
 ![](img/webdav.png)

 7. Configure the new WebDAV Server as follows:
    * Readable Title: `BOCKSCAR`
    * URL-address: `pubs.bockscar.mil`
    * Turn on/enable `Windows-style name encoding`
    * Turn off `Use cookies`
    * Leave all the other fields/settings unchanged
![](img/webdav2.png)

 8. Tap **Add**.
 9. You should now see **BOCKSCAR** listed as a saved server.
 ![](img/bockscar.png)

----

## Step 4: Sync a Folder

Now that you have the server added, we’ll configure GoodReader to sync with a folder on that server.

1. Tap the Connect button on the main screen. <br>
 ![](img/connect.png)

 2. Tap to highlight Saved Servers.
 ![](img/savedservers.png)

 3. Select BOCKSCAR. A list of folders on the server are displayed.
 ![](img/bockscarfiles.png) 


 4. Tap to highlight the folder you’d like to sync (We want to select the folder, not see its contents. So tap the folder name, not the > to the right of it). 

    !!! Note 
        55 OG Aircrew should select the **55_OG** folder. If you’re unsure, that’s probably what you should select. You can come back anytime and sync additional folders.

 5. Tap **Sync**, at the bottom of the screen. 

 6. If you get a pop-up that says *Folder Already Exists* select **Proceed**.
 
 7. Now we’ll tell GoodReader where to sync the folder to on your device. We want the folder in your top/root directory, called **My Documents**, so do not select any folders. Tap **Download Here & Synchronize**.
![](img/mydoc.png) 

 8. If you see a `Folder Already Exists` pop-up, tap **OK**.
 
 9. Configure the Sync Parameters as follows:
    * Turn on/enable **Download only** sync.
    * Make sure **Delete local files** is on/enabled
    * Turn on/enable **…even if they were edited**.
    * POLICY ON SYNC CONFLICTS: **Action** needs to be *Remote files have priority*.
    * Tap **Sync** (or **Close**)
![](img/syncparam.png) 

10. You’ve set up the folder to sync from the BOCKSCAR server. GoodReader will now begin to sync that folder. You should see:
![](img/syncprogress.png)   

----

## Sync your Folders

From now on, you can update your synced folders in GoodReader to make sure you have the latest publications/T.O.s/files.

1. Connect to a BOCKSCAR Wi-Fi Access Point.
![](img/wifi.png) 

2. Open GoodReader. From the main screen, tap the **Sync** button. 
![](img/sync.png) 

