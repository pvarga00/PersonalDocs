


# What you need:

- GIT → [https://git-scm.com/downloads](https://git-scm.com/downloads)


## Step 1 -  Setting Up Correct SSL Permissions

This one's still a bit hairy. Git straight-up won't work if you skip this step. Distilling instructions from [this writeup](https://confluence/display/KBR/Solution+for+users+of+GIT+having+connectivity+issue):

1. Get this CRT file: [https://s3.amazonaws.com/uploads.hipchat.com/95152/1042085/OLlsBH1t1DCsTjO/curl-ca-bundle.crt](https://s3.amazonaws.com/uploads.hipchat.com/95152/1042085/OLlsBH1t1DCsTjO/curl-ca-bundle.crt)
    1. This contains a certificate which authenticates to our Enterprise GitHub server
2. Save this file to *C:/Users/&lt;your username&gt;*as *curl-ca-bundle.crt*
    1. It should default to this.
3. Open Git and run the following command:          
                                         
       <s><strong><em> &nbsp; &nbsp;<span style="color: rgb(153,153,153);">git config --global http.sslCAInfo C:/Users/&lt;your username&gt;/curl-ca-bundle.crt</span></em></strong></s><s><strong><em><br></em></strong></s>
    1. <s>Obviously replacing the chunk in wrapped in &lt; &gt;</s>


***<u>git config --global http.sslBackend schannel&nbsp; </u>****<u>(</u>**Refer**<ac:link><ri:page ri:space-key="KBR" ri:content-title="How To Configure Git To Connect To GitHub Enterprise"></ri:page><ac:plain-text-link-body><![CDATA[GHE Certificate & Fully Qualified Domain Name Upgrade (Prod)]]></ac:plain-text-link-body></ac:link> Github Enterprise update changes)*

## Step 2 -  Fork the Repository

1.) First off you will need to find the repository you wish to contribute to.

<ac:image ac:height="400"><ri:attachment ri:filename="image2018-4-2_17-23-59.png"><ri:page ri:space-key="~pvarga" ri:content-title="Setup Git Environment"></ri:page></ri:attachment></ac:image>



2.) Then you will need to clone your repo to local

a.)  Get the clone url from GIT

<ac:image ac:height="400"><ri:attachment ri:filename="image2018-4-2_17-34-37.png"><ri:page ri:space-key="~pvarga" ri:content-title="Setup Git Environment"></ri:page></ri:attachment></ac:image>

b.) Clone the repo using   the command    **git clone  {{ GIT\_URL\_HERE }}** or through your tool of choice  (ex.  Visual Studio,  Source Tree)





## Step 3 - Set up upstream/master 

1.) Now that you have  you have a**local/master** branch and can call out to **origin/master** for your repo you want to set up an  **upstream/master** that points to the master branch of the original repo

GIT command →  [https://help.github.com/articles/configuring-a-remote-for-a-fork/](https://help.github.com/articles/configuring-a-remote-for-a-fork/)

Visual Studio → [https://docs.microsoft.com/en-us/vsts/git/concepts/forks?view=vsts](https://docs.microsoft.com/en-us/vsts/git/concepts/forks?view=vsts)


