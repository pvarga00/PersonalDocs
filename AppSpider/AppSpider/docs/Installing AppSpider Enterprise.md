
**Original Content:** [https://appspider.help.rapid7.com/docs/installing-appspider-enterprise](https://appspider.help.rapid7.com/docs/installing-appspider-enterprise)

[Enabling SAML for AppSpider Enterprise](https://appspider.help.rapid7.com/docs/enabling-saml-for-appspider-enterprise)

[Configuring SMTP Settings for AppSpider Enterprise](https://appspider.help.rapid7.com/docs/configuring-an-smtp-settings-for-appspider-enterprise)



To update AppSpider Enterprise, please reach out to Rapid7 Support using the [Customer Portal](https://www.rapid7.com/for-customers/) and request the latest AppSpider Enterprise installer. Once you have the latest installer, you must run it on the AppSpider Enterprise server following the instructions [here](https://appspider.help.rapid7.com/docs/installing-appspider-enterprise) (newer) or below.

You can learn about the latest versions of AppSpider Enterprise on the [release notes](https://help.rapid7.com/appspiderenterprise/release-notes/) page.





AppSpider Enterprise allows you to manage and coordinate multiple AppSpider installations across your organization so that you can scale your application security programs to handle thousands of scans at the same time. The enterprise version of AppSpider allows you to manage scan configurations and schedules from a centralized location, identify and prioritize high risk vulnerabilities, and easily share the results with members of your organization.

Installing AppSpider Enterprise is a multi-step process that requires:

- Configuring Internet Information Services (IIS).
- Installing AppSpider Enterprise.
- Adding an engine by installing AppSpider Pro.
- Configuring a scan engine for AppSpider Enterprise.


## System Requirements

In order to set up and operate AppSpider Enterprise, your system must meet the following [minimum requirements](https://www.rapid7.com/products/appspider/system-requirements.jsp).

## Database Server Requirements

If you intend to use an existing database, you'll need the connection information and the table name for the database you want to use. You'll need to make sure that you have administrator privileges for the database, which allows you to modify columns and tables in the database.

If you don't have a database readily available to use, you'll need to set one up one of the following databases:

- Microsoft SQL Server 2008 Family including Express Edition
- Microsoft SQL Server 2012 Family including Express Edition
- Microsoft SQL Server 2014
- Microsoft SQL Server 2016


## AppSpider Enterprise Licensing

The enterprise version of AppSpider does not require any licensing, but you must have at least one license for AppSpider Pro in order to use it. When you purchased AppSpider Enterprise, you automatically received a license for one AppSpider engine. For you need help with licensing, please contact our [support team](https://www.rapid7.com/support).

## Before You Begin

Before you install AppSpider Enterprise, please make sure that you have set up the following on your Windows system:

- A database server, such as MSSQL Server 2008 or 2012
- A web server, such as Microsoft Internet Information Services (IIS) 6.0


You'll also need to download:

- The AppSpider Enterprise installer: A link to the AppSpider Enterprise installer is sent to you from Rapid7. If you have not received a link to the installer, please contact our [support team](https://www.rapid7.com/support).
- The AppSpider Pro installer: The installer can be downloaded from the following location: [http://download2.rapid7.com/download/AppSpider/AppSpiderSetup.exe](http://download2.rapid7.com/download/AppSpider/AppSpiderSetup.exe).




Note: You'll also want to run PowerShell to unblock the .exe - with this command:  <u>Unblock-File -Path C:\Users\ws-appspider\Desktop\AppSpiderEnterprise_Setup-XXXXXX.exe</u> and then run it as an Administrator

## Installing Internet Information Services (IIS)

Before you can install AppSpider Enterprise, you'll need to set up Internet Information Services, or IIS, which is the Web server role in Windows Server 2012.

There are a few ways that you can install IIS:

- Using the Server Manager
- Using the command line with Deployment Image Servicing and Management (DISM)
- Using the command line with Powershell


The following instructions show you how to install IIS with the Server Manager. For instructions on how to use Powershell, visit [https://technet.microsoft.com/en-us/magazine/jj149025.aspx](https://technet.microsoft.com/en-us/magazine/jj149025.aspx). To learn how to install with DISM, read [this link](https://technet.microsoft.com/en-us/library/hh831475%28v=ws.11%29.aspx/).

If you already have an IIS configured, you can skip the next section on installing AppSpider Enterprise. You'll need to know the server name for IIS and the database.

### Installing IIS on Windows 2012 Server with the Server Manager

The Server Manager provides a single dashboard that you can use to add server roles, role services, and features. The following steps show you how to set up IIS for the first time.

To install IIS using the Server Manager:

1. From the Dashboard, select Add roles and features from the Quick Start menu to launch the Add Roles and Features Wizard.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-server-manager-dashboard.jpg"></ri:url></ac:image>
2. The first screen provides you with some information you need to know before you begin. Read the section and select Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-before-you-begin.jpg"></ri:url></ac:image>
3. The next screen prompts you to choose an installation type. Select Role-based or feature based installation to install all parts of roles or features on a single server and click Next.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-installation-type.jpg"></ri:url></ac:image>
4. The next screen prompts you to choose a server or virtual disk to install the roles and features. Choose the Select a server from the server pool option and click Next.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-server-selection.jpg"></ri:url></ac:image>
5. The next screen prompts you to choose the roles you want to install on the server. From the "Roles" list, select Web Server (IIS).
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-roles.jpg"></ri:url></ac:image>
6. After you choose Web Server (IIS), a pop-up appears and prompts you to add the tools that are required to run it. Click Add Features to close the pop-up and to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-add-features.jpg"></ri:url></ac:image>
7. When you are back on the "Server Roles" tab, click Next to continue.
8. From the "Features" list, make sure that .NET Framework 3.5 and .NET Framework 4.5 are selected.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-net-versions.jpg"></ri:url></ac:image>
9. Expand the ".NET Framework 3.5 Features" node and then select the HTTP Activation option.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-http-activation-3.5.jpg"></ri:url></ac:image>
10. After you select the HTTP Activation option, a pop-up appears and asks you if you want to add the features that are required for it. Click Add Features to close the pop-up and to continue. When you are back on the "Features" tab, click Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-add-features-for-http-activation-3.5.jpg"></ri:url></ac:image>
11. Expand the ".NET Framework 4.5 Features" node, and then expand "WCF Services". After you've expanded the "WCF Services" node, select the HTTP Activation option.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-http-activation-4.5.jpg"></ri:url></ac:image>
12. After you select the HTTP Activation option, a pop-up appears and asks you if you want to add the features that are required for it. Click Add Features to close the pop-up and to continue. When you are back on the "Features" tab, click Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-add-features-for-http-activation-4.5.jpg"></ri:url></ac:image>
13. The next screen provides information on web servers. Read the section and click Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis_server_information.jpg"></ri:url></ac:image>
14. From the "Role services" list, find "Application Development", expand the node, and select the following services:
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-application-development-services.jpg"></ri:url></ac:image>
15. From the same list, find the "Management Tools" node and expand it.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-management-tools-node.jpg"></ri:url></ac:image>
16. Verify IIS Management Console is selected. Then, select IIS 6 Management Compatibility , and click Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-management-tools.jpg"></ri:url></ac:image>
17. On the next screen, review the roles, services, and features you are installing on the server. When you are ready to start the installation process, click Install.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-installation-confirmation.jpg"></ri:url></ac:image>


The "Results" tab displays and shows you the installation progress.

<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/iis-installation-progress.jpg"></ri:url></ac:image>

1. Close the Wizard when the installation completes.


Now that you've set up IIS, you are ready to install AppSpider Enterprise.

### Configuring HTTPS certificates through IIS

In a new installation, the AppSpider Enterprise console and the scan engine run web services run over HTTP by default. For security purposes, you'll need to reconfigure them to run over HTTPS instead.

To learn how to configure your certificates through IIS, please visit [https://www.iis.net/learn/manage/configuring-security/how-to-set-up-ssl-on-iis](https://www.iis.net/learn/manage/configuring-security/how-to-set-up-ssl-on-iis).

### Creating a self-signed certificate in IIS

## Installing AppSpider Enterprise

To set up AppSpider Enterprise you'll need the installer, which you should have received from Rapid7. If you have not received a link to the installer, please contact our [support team](https://www.rapid7.com/support).

To install AppSpider Enterprise:

1. Run the installer.
2. When the Welcome screen appears, click Next to continue.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-welcome.jpg"></ri:url></ac:image>
3. The next screen displays the license agreement. Read the agreement and click I Agree when you are ready to continue.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-license-agreement.jpg"></ri:url></ac:image>
4. The next screen lists the required software that must be installed to run AppSpider Enterprise. Review the software prerequisites and click Next to continue.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-prerequisites.jpg"></ri:url></ac:image>
5. After the Visual C++ redistributable package is installed, the next screen displays the components that you need to install to run AppSpider Enterprise. At a minimum, you must install the database, web application, and scheduler service. After you choose the components you want to install, click Next to continue.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-components.jpg"></ri:url></ac:image>
6. The Destination Folder stores the program files for AppSpider Enterprise. Specify the directory you want to use for the Destination folder and click Next.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-destination-folder.jpg"></ri:url></ac:image>
7. The Data Directory stores the reports and uploaded files for AppSpider. Specify the directory you want to use for the Data Directory and click Next.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-data-directory.jpg"></ri:url></ac:image>
8. You will now configure parameters to be used to execute AppSpider Enterprise. Read more about this [in the Support portal](https://rapid7support.force.com/customers/00P1O00001CuwKG?btdid=5001O00001Ez080/).
9. On the next screen, you'll need to configure your IIS settings. Choose the site, virtual directory, and application pool you want to use. For more information on sites, virtual directories, and application pools, please read [http://www.iis.net/learn/get-started/planning-your-iis-architecture/understanding-sites-applications-and-virtual-directories-on-iis](http://www.iis.net/learn/get-started/planning-your-iis-architecture/understanding-sites-applications-and-virtual-directories-on-iis).
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-iis-configuration.jpg"></ri:url></ac:image>
10. Next, you can optionally configure SMTP and LDAP at this point, or do it after the installation if you do not have these details available. See more details in steps 19 and 20.


1. If you do not plan to use LDAP to log in to AppSpider Enterprise, select the Create AppSpider Enterprise Administrator Account checkbox to create a local system administrator account. See further details in step 15.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-admin-account-option.jpg"></ri:url></ac:image>


If you do plan to connect with LDAP, you do not need to create a system administrator. Configure further details in step 20.

1. On the next screen, you will need to set up your database connection. To generate the connection string, click Generate to display the "Connection Properties" window.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-generate-database-connection-button.jpg"></ri:url></ac:image>
2. In the Server name field, either select a server from the dropdown list or enter the name of your SQL server. If using a non-default SQL Server port (1433), please specify the Server name using the following format server,port.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-connection-properties.jpg"></ri:url></ac:image>
3. Choose the Select or enter a database name option and either enter a new database name or choose an existing database that you want to use. Click OK to save your changes and close the "Connection Properties" window to finish configuring SQL server.
<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-database-connection.jpg"></ri:url></ac:image>


### If Setting Up a Local Admin Account

1. On the original wizard screen, if you are setting up your local Admin account, enter the login you want to use for your administrator account in the AppSpider Enterprise Administrator Login field.
2. Enter the email address you want to use for your administrator account in the AppSpider Enterprise Administrator Email field.
3. Enter a password for the account in the AppSpider Enterprise Administrator Password field.
4. Enter the same password again in the Confirm Password field.
5. Click Next to continue.


Skip to step 21.

### If Setting Up LDAP

1. If applicable, setup the LDAP configuration in the next screen. Read [connecting to an LDAP Directory Server](https://appspider.help.rapid7.com/v1.2/docs/connecting-to-an-ldap-directory-server) for more information.
2. If applicable, setup the SMTP configuration. Read [configuring an SMTP Settings for AppSpider Enterprise](https://appspider.help.rapid7.com/v1.2/docs/configuring-an-smtp-settings-for-appspider-enterprise) for more information.
3. Enter or select a start menu folder to receive AppSpider Enterprise shortcuts, and click the Install button. [Here is the link for the shortcut via the Support Portal](https://rapid7support.force.com/customers/00P1O00001CuyiB?btdid=5001O00001Ez080).
4. The database connection is tested, and if it is successful, the installation process begins. When the installation completes, click Next to go to the last screen.
5. Click Finish to close the Installation Wizard.


You are now done installing AppSpider Enterprise. The next thing you'll need to do is log in to AppSpider Enterprise for the first time.

## Logging into AppSpider Enterprise for the First Time

AppSpider Enterprise can be managed through the web interface. To access the web interface, go to [http://localhost/AppSpiderEnterprise](http://localhost/AppSpiderEnterprise) and login using the credentials for the system administrator account you created when you installed AppSpider Enterprise.

<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-login-page.jpg"></ri:url></ac:image>

When you log in, you will be prompted to select a client. A client represents a collection of users who interact with AppSpider Enterprise. By default, the client is set to "None". If you want to practice with a web application, you can select the "webscantest" option, which is part of an intentionally vulnerable application that we've created for testing purposes so that users can quickly get started with AppSpider Enterprise.

<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-select-client.jpg"></ri:url></ac:image>

After you select the client you want to you, the Dashboard will appear. The next thing you'll need to do is install a scan engine.

## Installing AppSpider Pro

Now that you've finished setting up AppSpider Enterprise and have logged in for the first time, you are ready to install an AppSpider engine. To set up an AppSpider engine, you'll need to install AppSpider Pro.The installer for AppSpider Pro is located at [http://download2.rapid7.com/download/AppSpider/AppSpiderSetup.exe](http://download2.rapid7.com/download/AppSpider/AppSpiderSetup.exe).

The scan engine should be installed on a dedicated system that is part of your scan engine pool.

To install AppSpider Pro:

1. Run the installer.
2. When the Welcome screen appears, click Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-welcome.jpg"></ri:url></ac:image>
3. Read the license agreement and click I Agree to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-license.jpg"></ri:url></ac:image>
4. The next screen allows you to choose the components you want to install. The default selections are recommended, but you should also include the AppSpider Web Service. Here are the components that are available and their descriptions:

    - AppSpider Engine - The core component that runs AppSpider. This is a required component; AppSpider cannot run without it.
    - AppSpider WebService - The service that runs the AppSpider web interface.
    - AppSpider GUI - The component that is used to manage scans, monitoring, and reporting.
    - AppSpider CMD - The component that enables you to use the command line to manage a scan engine.
    - AppSpider Branding Tool - The tool that enables you to create custom branded reports
    - AppSpider REST Service - The REST API that enables you to manage scan engines over FAST CGI.
    - NGINX Web Server - The web server that manages FAST CGI over HTTP/HTTPS
5. After you select the components you want to install, click Next.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-components.jpg"></ri:url></ac:image>
6. The Destination Folder stores the program files for the scan engine. Specify the directory you want to use for the Destination folder and click Next.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-destination.jpg"></ri:url></ac:image>
7. Choose how you want the data storage to impact other users on the system. Make the data folder accessible for all users and specify the path to data folder.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-directory-access.jpg"></ri:url></ac:image>
8. Select the location where you want to store your scan data and click Next. If the directory doesn't currently exist, you'll be prompted to create it.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-directory-folder.jpg"></ri:url></ac:image>
9. The Data Directory stores the data, such as reports and uploaded files, for the engine. Specify the directory you want to use for the Data Directory and click Next.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-data-directory.jpg"></ri:url></ac:image>
10. If active scripting is disabled for Internet Explorer, the next screen alerts you that need to enable JavaScript to improve the effectiveness of AppSpider. Click Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-active-scripting.jpg"></ri:url></ac:image>
11. On the next screen, configure the information for your IIS server.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-iis.jpg"></ri:url></ac:image>
12. Select the Create the new Application Pool option to create new a application pool for the Engine Web Service (SOAP) and click Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-application-pool.jpg"></ri:url></ac:image>
13. The next screen prompts you to configure a user account for the AppSpider Scan Engine. Select Create a new windows user account.
14. On the next screen, enter the username and password for the scan engine account and click Next to continue.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-account-creds.jpg"></ri:url></ac:image>
15. Select the folder you want to use in the Start menu for AppSpider and click Install when you are ready install AppSpider Pro.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/engine-start-menu.jpg"></ri:url></ac:image>
16. The progress screen displays and shows you the status of the installation. When the installation completes, click Next to finish and start AppSpider Pro.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation/progress.jpg"></ri:url></ac:image>
17. On the next screen, you can choose to start AppSpider Pro and review the release notes. Select the actions you want to perform and click Finish.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation/complete.jpg"></ri:url></ac:image>


If you decided to launch AppSpider Pro, a window appears and prompts you to enter your product key.

<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation/license-key.jpg"></ri:url></ac:image>

Now that you've installed your first scan engine, you can repeat this process to additional engines.

## Adding a Scanning Engine

A scan engine is the component that crawls, analyzes, and simulates attacks on your mobile and web applications. With AppSpider Enterprise, you can deploy distributed scan engines across multiple locations within your network and manage them from a centralized location. Data from the scan engines are collected and integrated into the database for analysis and reporting.

If you have distributed scan engines across your network, you'll need to configure them for AppSpider Enterprise to use. In order to add a scan engine, you'll need to go to grab the user name and password specified in the scan engine's Web configuration file. The Web configuration file is located in /path/to/Rapid7/AppSpider6/IIS.NET and will need to be opened and edited with a text editor.

When you open the Web configuration file, find the "UserName" and "Password" keys and have those available when you ready to configure a scan engine in AppSpider Enterprise.

<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-web-config-file.jpg"></ri:url></ac:image>

To add a scanning engine:

1. Log in to AppSpider Enterprise.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-login-page.jpg"></ri:url></ac:image>
2. Select System &gt; Engines.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-system-menu.jpg"></ri:url></ac:image>
3. Click the Add button.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-add-engine-button.jpg"></ri:url></ac:image>
4. When the "Add engine" page appears, enter the following information:

    - Name - A descriptive name that you can assign to help identify the engine.
    - Service URL - The URL for the scan engine. If it is on the local server, the URL is [http://localhost/AppSpiderEntScanEngine/default.asmx](http://localhost/AppSpiderEntScanEngine/default.asmx). If the scan engine is located on a different server, the URL is http://\&lt;scan engine IP\&gt;/AppSpiderEntScanEngine/default.asmx.
    - Username - The user name specified in /path/to/Rapid7/AppSpider6/IIS.NET/Web.config
    - Password - The password specified in /path/to/Rapid7/AppSpider6/IIS.NET/Web.config

    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-add-engine.jpg"></ri:url></ac:image>
5. Save the engine when you are done. If the engine is saved successfully, it is displayed on the Engines page.
    <ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/installation-enterprise/ase-add-engine-successful.jpg"></ri:url></ac:image>


Congratulations! You've finished setting up AppSpider Enterprise and are now ready to start configuring and managing your scans.



Note: To verify if the AppSpider service is running on a server: It should be set to "Started" and "Automatic"
<ac:image ac:height="250"><ri:attachment ri:filename="AppSpSvc.gif"></ri:attachment></ac:image>


