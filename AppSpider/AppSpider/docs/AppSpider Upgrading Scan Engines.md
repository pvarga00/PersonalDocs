
Occasionally an update will release for AppSpider Pro which is what Enterprise uses as our scan engines.

## Step-By-Step Process for Upgrading Scan Engines

- Log onto each server that has a scan engine (Remote into <u>utilitybox</u> &gt; scan engine server) (Example: <u><strong>QL1AppSpider1</strong></u>)
- Launch "AppSpider Pro" (\*thick client) Note: Run it as an Administrator! (right-click on the icon!)


<ac:image><ri:attachment ri:filename="image2018-1-8 12:24:42.png"></ri:attachment></ac:image>

- Help &gt; "Check for updates"
<ac:image ac:height="200"><ri:attachment ri:filename="AppSpiderHelp.gif"></ri:attachment></ac:image>
- Click the link at the bottom of the app - if there any updates available
<ac:image ac:height="250"><ri:attachment ri:filename="AppSpiderScanEng.gif"></ri:attachment></ac:image>
- The bottom of the window will notify you if there is an update. Click on the message to download the update
    <ac:image><ri:attachment ri:filename="image2018-1-8 12:25:15.png"></ri:attachment></ac:image>
- Download the file to somewhere you have access (Ex: C:\Users\ws-appspider\Downloads)
- Save and run the installer
- Ensure AppSpider Pro is closed before running
- Right-click on the file &gt; Properties &gt; Click the "Unblock" button **AND/OR** launch PowerShell as an "Administrator" and run this command: "unblock-file -path .\AppSpiderSetup.exe" (From the download dir, for example: "C:\Users\ws-appspider\Downloads")
<ac:image ac:height="245"><ri:attachment ri:filename="AppSpiderUnblock.gif"></ri:attachment></ac:image>
- Run the installer - and take all the defaults 
<ac:image ac:height="400"><ri:attachment ri:filename="AppSpDefaults.gif"></ri:attachment></ac:image>


- NOTE: You may need to terminate ANY/ALL running instances)
    - Examples of things to terminate:


    - - SCANENGSVC.EXE
        - SCANENGINE.EXE
- Ensure that you check the box to "Force Upgrade of existing installation".


<ac:image><ri:attachment ri:filename="image2018-1-8 12:26:35.png"></ri:attachment></ac:image>

- The installer will take a minute or so to complete. Click "Next" when available and finish the install
- Relaunch the "AppSpider 7" application. FYI: We re-open AppSpider Pro to ensure it runs / works as expected
- Help &gt; "Check for updates" &gt; You should now be on the latest version!
- Success!
- Go in to AppSpider Enterprise and go to System &gt; Engines. Check the box next to the scan engine you upgraded and click on "Check Status"
<ac:image ac:height="400"><ri:attachment ri:filename="image2020-3-20_14-53-45.png"></ri:attachment></ac:image>
- The status should show "Online" and "Available".


<ac:image ac:height="400"><ri:attachment ri:filename="image2020-3-20_14-54-20.png"></ri:attachment></ac:image>




