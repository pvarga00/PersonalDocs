
<ac:structured-macro ac:name="gliffy" ac:schema-version="1" ac:macro-id="ecea5b9e-7567-4757-9779-5e83cdceb8cf"><ac:parameter ac:name="name">GIT_Workflow_Diagram Copy</ac:parameter><ac:parameter ac:name="pagePin">1</ac:parameter></ac:structured-macro>





<ac:image><ri:url ri:value="https://s3.amazonaws.com/uploads.hipchat.com/95152/3113420/plylheTi6Tvq9ZI/upload.png"></ri:url></ac:image>







<ac:structured-macro ac:name="gliffy" ac:schema-version="1" ac:macro-id="81f7b392-cfa1-4a35-bc89-b3149be3cbe5"><ac:parameter ac:name="name">GIT_Workflow_Diagram</ac:parameter><ac:parameter ac:name="pagePin">3</ac:parameter></ac:structured-macro>



## **Step 1:  PULL from <u>upstream/master</u> into <u>origin/master</u>**

* * *



### 1.) Switch over to your master branch and pull the latest from upstream/master
<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="ef1ab807-60ce-4841-87c3-26ea2759d308"><ac:parameter ac:name="language">bash</ac:parameter><ac:plain-text-body><![CDATA[$ git checkout master
$ git pull upstream master]]></ac:plain-text-body></ac:structured-macro>


### 2. ) Update your origin/master  
<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="bf40c3b2-6cce-4d91-ba5b-70fb72423a6c"><ac:parameter ac:name="language">bash</ac:parameter><ac:plain-text-body><![CDATA[$ git push origin master]]></ac:plain-text-body></ac:structured-macro>




**Step 2:  REBASE <u>origin/myFeature</u> onto <u>origin/master</u>**

* * *



### 1.) Switch back over to your feature branch
<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="8cca2d50-8ad9-47d6-a46d-aa3e59f43729"><ac:parameter ac:name="language">bash</ac:parameter><ac:plain-text-body><![CDATA[    $ git checkout myFeature]]></ac:plain-text-body></ac:structured-macro>
### **<u><br></u>**2.) Rebase onto origin/master
<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="dcfc81f5-3e7f-4440-a2c4-baea90305bd7"><ac:parameter ac:name="language">bash</ac:parameter><ac:plain-text-body><![CDATA[$ git rebase origin/master]]></ac:plain-text-body></ac:structured-macro>
**<u>The following are the possible results of this command:</u>**

A.)  You have no merge conflicts → **Congratulations! You can move on to the next step**

B.) You have merge conflcts → **STOP! You need to resolve your merge conflicts!** See below

i.) Resolve your merge conflicts

ii.) Stage your changes to resolve the merge conflicts
<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="feebec80-3a72-4da2-bff1-486d1545b7d4"><ac:parameter ac:name="language">bash</ac:parameter><ac:plain-text-body><![CDATA[$ git add .]]></ac:plain-text-body></ac:structured-macro>
iii.) Once all merge conflicts are resolved continue the rebase
<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="1ba5e4db-4600-4ee0-a6c5-614c745098fe"><ac:parameter ac:name="language">bash</ac:parameter><ac:plain-text-body><![CDATA[$ git rebase --continue]]></ac:plain-text-body></ac:structured-macro>
iv.) Move on to Step 3

### 3.)  Push your changes to origin/myFeature
<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="1a6c2577-caea-42da-848e-2b4e36c19325"><ac:parameter ac:name="language">bash</ac:parameter><ac:plain-text-body><![CDATA[$ git push origin myFeature -f]]></ac:plain-text-body></ac:structured-macro>


**Step 3:  PULL REQUEST <u>origin/myFeature</u> on <u>upstream/master</u>**

* * *

**<u><br></u>**

**<u><br></u>**

## **STEP 4 : SQUASH MERGE**

* * *




