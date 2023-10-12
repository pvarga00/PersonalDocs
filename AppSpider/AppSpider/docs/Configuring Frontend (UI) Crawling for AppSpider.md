
1. Follow this <u><span style="color: rgb(0,0,255);"><a href="https://git.rockfin.com/pages/QAPOW/cqrunbook/quality-gates/security-tests/appspiderSetup/"><span style="color: rgb(0,0,255);"><strong>LINK</strong></span></a></span></u> for documentation on how to set up your application's AppSpider security scanning configuration
2. If your application has authentication and/or authorization (see below sub-bullet)

    1. If yes, use the following sample selenium script to automate the authentication into the application. Update all the "TODO" tags in the script with your appropriate information:

        1. <ac:link><ri:attachment ri:filename="example-script.java"></ri:attachment></ac:link>
3. Open a Chrome web browser
4. Install the following extension: 'Penetration Testing Kit' by Rapid7

    1. Go to the [Chrome extensions "Store"](https://chrome.google.com/webstore/category/extensions?hl=en-US)
    2. Find the ['Penetration Testing Kit'](https://chrome.google.com/webstore/detail/penetration-testing-kit/ojkchikaholjmcnefhjlbohackpeeknd?hl=en-US) by Rapid7 and "Add to Chrome"
5. Within Chrome, launch the 'Penetration Testing Kit'
<ac:image ac:thumbnail="true" ac:height="117"><ri:attachment ri:filename="image2019-11-26_11-5-24.png"></ri:attachment></ac:image>
6. If you click the icon you should a screen like below:
    <ac:image ac:height="250"><ri:attachment ri:filename="image2019-11-19_20-40-14.png"></ri:attachment></ac:image>
7. Navigate to your website to be tested
8. Login into your application, if you need to authenticate your application
9. Within the 'Penetration Testing Kit' extension, navigate to the "Traffic Recorder" tab
10. Click "Record Sequence"
    <ac:image ac:height="250"><ri:attachment ri:filename="image2019-11-19_20-47-0.png"></ri:attachment></ac:image>
11. Once you click the "Record Sequence" button, it should open a new window where the recording session will continue. You will see a message similar to: **"Penetration Testing Kit" is debugging this browser**
12. Click all of the links of your application, that you would like to scan
13. Navigate back to original window, (where you initiated the recoding session)
14. Review the recorded session capture
15. Once things look as expected, click "Export"
    <ac:image ac:height="250"><ri:attachment ri:filename="image2019-11-19_20-50-13.png"></ri:attachment></ac:image>
16. Click the "Download" button, to save the capture
17. Navigate to [AppSpider Enterprise](https://shorty/appspider), to continue the configuration
18. Navigate to "Scanning"
19. Select "Configs"
<ac:image ac:height="167"><ri:attachment ri:filename="image2019-11-26_11-14-37.png"></ri:attachment></ac:image>
20. Search for your configuration
21. Select your application (checkbox) and click "Edit One"
<ac:image ac:height="250"><ri:attachment ri:filename="image2019-11-26_11-16-30.png"></ri:attachment></ac:image>
22. Go to "Crawling"
<ac:image ac:height="250"><ri:attachment ri:filename="image2019-11-26_11-17-4.png"></ri:attachment></ac:image>
23. Click the plus sign next to the "Proxy log"
<ac:image ac:height="250"><ri:attachment ri:filename="image2019-11-26_11-17-44.png"></ri:attachment></ac:image>
24. Upload the capture saved previously
<ac:image ac:height="141"><ri:attachment ri:filename="image2019-11-26_11-18-49.png"></ri:attachment></ac:image>
25. Select **"Restrict scan to recorded traffic"**
    **<ac:image ac:height="207"><ri:attachment ri:filename="image2019-11-26_11-19-26.png"></ri:attachment></ac:image>**
26. If you have a Selenium script, from the previous step (authentication)

    1. Go to Authentication tab
    2. Select Selenium
    3. Upload the script from above step under Selenium authentication
27. Save the configuration
28. Run your newly configured scan!



