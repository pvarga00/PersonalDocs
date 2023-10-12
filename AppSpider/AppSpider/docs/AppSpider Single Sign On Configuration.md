
Rapid7 Docs: [https://appspider.help.rapid7.com/docs/enabling-saml-for-appspider-enterprise](https://appspider.help.rapid7.com/docs/enabling-saml-for-appspider-enterprise)



# Enabling SAML for AppSpider Enterprise

Security Assertion Markup Language (SAML) is an XML-based standard for single sign-on (SSO) authentication that enables you to access applications you have rights to use. AppSpider Enterprise offers integration with SAML 2.0, which allows you to use an identity provider (IdP) to handle the sign-in process and provide the credentials your users need to authenticate to AppSpider Enterprise.

To enable SAML for AppSpider Enterprise, there are two things you'll need to do:

- Create a SAML certificate with your IdP and install the certificate on the server running AppSpider Enterprise.
- Modify the `samlProviders.config` file to include the information for your IdP and to enable SAML for AppSpider Enterprise.


## Creating a SAML certificate with your IdP

SAML certificates enable you to increase security between your IdP and your SAML applications. To learn how to create SAML certificates, please visit your IdP's documentation. You'll need to create one for AppSpider Enterprise.

After you create the SAML certificate, you'll need to download the certificate, and store it on your AppSpider Enterprise server. You'll need details from the SAML certificate, such as the location of where the certificate is installed, to configure SAML for AppSpider Enterprise.

## Modifying the SAML configuration file

1. Open `C:\Program Files(x86)\Rapid7\AppSpider Enterprise x.x\IIS.NET\samlProviders.config` with a text editor. Replace "x.x" in the file path with the version of AppSpider Enterprise you are running.


### Note

You may need to have administrator privileges to edit the file.

1. Find the element `<samlProviders enabled="false">` and change its value to `true` to provision users to use SAML.
2. Find the line that starts with `<provider>`. You *must* provide the information for the following options:
    - signOnUrl - The URL of the IdP handling your sign-in requests, such as [http://IDP\\_servername/saml2/sso/1234](http://idp/_servername/saml2/sso/1234).
    - issuer - The unique entity identifier for your IdP, such as [http://saml.yourcompany.com](http://saml.yourcompany.com/).
    - title - The company name you'll use to log in to AppSpider Enterprise. This is the information you will enter when you log in to AppSpider Enterprise via SAML.
3. Find the line that starts with `<certificate>`. You *must* provide the information for the following options:
    - findBy - How to search for the certificate. Ex: "FindBySubjectName", "FindByThumbprint", "FindBySubjectDistinguishedName"
    - findValue - The value to search for based on how "findBy" is defined.
    - storeLocation - The location of the certificate on your local machine. Ex: "LocalMachine", "CurrentUser"
    - storeName - The certificate's storage name. By default, this value is "My," which means that the certificate is located in Local Machine &gt; Personal storage. Another example is "TrustedPeople".
4. Find the line that starts with `<provideConfiguration>`. You *must* provide the information for the following options for new AppSpider Enterprise users:
    - autoAttachToClient - The enterprise client that you want to assign to SAML users. A client is a collection of users who interact with AppSpider Enterprise and sets bounds on the people can use the application.
    - autoAttachSysAdmins - The IdP username you want to assign as a system administrator. You can only specify one user name for this option.
    - autoAttachGroups - The name of the enterprise group that can log in to AppSpider Enterprise to manage access to the application.
5. If you want to send login data to your IdP, you can add the following line to the configuration file: `<samlRequestParams ID="" AssertionConsumerServiceURL="" Issuer="" />`, where:

    - ID - An identifier for AppSpider Enterprise.
    - AssertionConsumerServiceURL - The SAML login for AppSpider Enterprise, such as https://&lt;servername&gt;/AppSpiderEnterprise/Account/SamlLogin`.
    - Issuer - The server name.
    - NameIdFormat="undefined" - This configures the &lt;samlp:NameIDPolicy (Specifies constraints on the name identifier to be used to represent the requested subject). If omitted email is used. ( Version: 3.8.189 and above)
6. Save the file.


## Using SAML to log in to AppSpider Enterprise

After you have enabled and configured SAML for AppSpider Enterprise, you can navigate to the AppSpider Enterprise login page and use the SAML button to log in to the application.

<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/saml/saml-login.jpg"></ri:url></ac:image>

You'll be prompted for your company name, which is the title you defined in the SAML configuration file.

<ac:image><ri:url ri:value="https://help.rapid7.com/appspider/content/resources/images/saml/company-name.jpg"></ri:url></ac:image>

If SAML is set up properly, you'll be logged in to AppSpider Enterprise.




<ac:structured-macro ac:name="expand" ac:schema-version="1" ac:macro-id="0af8a8af-8044-429d-ba28-9c77b0f181ad"><ac:parameter ac:name="title">Old Setup</ac:parameter><ac:rich-text-body><p><u><strong>Our Setup:&nbsp;</strong><em>C:\Program Files(x86)\Rapid7\AppSpider Enterprise 3.8\IIS.NET\samlProviders.config</em></u></p><p class="p1"><span class="s1">&lt;samlProviders enabled=&quot;true&quot;&gt;</span></p><p class="p1"><span class="s1">&nbsp; &lt;providers&gt;</span></p><p class="p1"><span class="s1">&nbsp; &nbsp; &lt;provider signOnUrl=&quot;<a href="https://sso.ss.foc.zone/" title="https://sso.ss.foc.zone/">https://sso.ss.foc.zone</a><a href="https://sso.rockfin.com/idp/SSO.saml2">/idp/sso.saml2</a>&quot; issuer=&quot;<a title="https://sso.ss.foc.zone/" href="https://sso.ss.foc.zone/">https://sso.ss.foc.zone</a>&quot; title=&quot;QL&quot;&gt;</span></p><p class="p1"><span class="s1">&nbsp; &nbsp; &nbsp; &lt;certificate findValue=&quot;AppsSpideR7&quot; storeLocation=&quot;CurrentUser&quot; storeName=&quot;My&quot; findBy=&quot;FindBySubjectName&quot; /&gt;</span></p><p class="p1"><span class="s1">&nbsp; &nbsp; &nbsp; &lt;providerConfiguration autoAttachToClient=&quot;Quicken Loans&quot; autoAttachSysAdmins=&quot;&quot; autoAttachGroups=&quot;QL Reporter&quot; /&gt;</span></p><p class="p1"><span class="s1">&nbsp; &nbsp; &nbsp; &lt;samlRequestParams&nbsp; ID=&quot;<a href="http://appspider.rapid7.com">appspider.rapid7.com</a>&quot;&nbsp; AssertionConsumerServiceURL=&quot;<a href="https://appspider.rockfin.com/AppSpiderEnterprise/Account/SamlLogin">https://appspider.rockfin.com/AppSpiderEnterprise/Account/SamlLogin</a>&quot; Issuer=&quot;<a href="http://appspider.rapid7.com">appspider.rapid7.com</a>&quot; NameIdFormat=&quot;unspecified&quot;/&gt;</span></p><p class="p1"><span class="s1">&nbsp; &nbsp; &lt;/provider&gt;</span></p><p class="p1"><span class="s1">&nbsp; &lt;/providers&gt;</span></p><p class="p1"><span class="s1">&lt;/samlProviders&gt;</span></p></ac:rich-text-body></ac:structured-macro>



<ac:structured-macro ac:name="expand" ac:schema-version="1" ac:macro-id="85e12984-4897-4359-9435-ee3fe9902a82"><ac:parameter ac:name="title">New Auth0 - Current Setup</ac:parameter><ac:rich-text-body><p>&lt;samlProviders enabled=&quot;true&quot;&gt;<br> &lt;providers&gt;<br> &lt;provider signOnUrl=&quot;<a href="https://sso.ss.foc.zone/idp/SSO.saml2">https://sso.ss.foc.zone/idp/SSO.saml2</a>&quot; issuer=&quot;<a href="https://sso.ss.foc.zone">https://sso.ss.foc.zone</a>&quot; title=&quot;QL&quot;&gt;<br> &lt;certificate findValue=&quot;AppsSpideR7&quot; storeLocation=&quot;CurrentUser&quot; storeName=&quot;My&quot; findBy=&quot;FindBySubjectName&quot; /&gt;<br> &lt;providerConfiguration autoAttachToClient=&quot;Rocket Mortgage (formerly QL)&quot; autoAttachSysAdmins=&quot;&quot; autoAttachGroups=&quot;QL Reporter&quot; /&gt;<br> &lt;samlRequestParams ID=&quot;<a href="http://appspider.rapid7.com">appspider.rapid7.com</a>&quot; AssertionConsumerServiceURL=&quot;<a href="https://appspider.rockfin.com/AppSpiderEnterprise/Account/SamlLogin">https://appspider.rockfin.com/AppSpiderEnterprise/Account/SamlLogin</a>&quot; Issuer=&quot;<a href="http://appspider.rapid7.com">appspider.rapid7.com</a>&quot; NameIdFormat=&quot;unspecified&quot;/&gt;<br> &lt;/provider&gt;<br> &lt;/providers&gt;<br>&lt;/samlProviders&gt;</p></ac:rich-text-body></ac:structured-macro>




Note: The command "mmc" will launch a console UI that allows you to view/import certificates:

Then you want to go to File &gt; Add/Remove Snap-In &gt; Certificates

<ac:image ac:thumbnail="true" ac:height="250"><ri:attachment ri:filename="image2020-11-3_15-50-12.png"></ri:attachment></ac:image>

<ac:image ac:height="250"><ri:attachment ri:filename="image2020-11-3_15-51-31.png"></ri:attachment></ac:image>

<ac:image ac:height="250"><ri:attachment ri:filename="image2020-11-3_15-52-17.png"></ri:attachment></ac:image>





<u><strong>Powershell Helper Commands:</strong></u>

$store = New-Object System.Security.Cryptography.X509Certificates.X509Store("My", "LocalMachine”)

$store.Open("ReadOnly")

$store.Certificates.Find("FindBySubjectName", "AppSpider", "false")



The Powershell response will be empty if no certs are found - or something like this if the cert <u><strong>IS</strong> </u>found:

PS C:\WINDOWS\system32&gt; $store.Open("ReadOnly")
PS C:\WINDOWS\system32&gt; $store.Certificates.Find("FindBySubjectName", "AppsSpideR7", "false")

Thumbprint Subject
---------- -------
607993D184DD5CCAECB2A71AD33C80228670CF5E CN=AppsSpideR7, O=QL, C=US


