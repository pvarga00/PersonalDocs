
The process steps through how to get the test results from System Tests to show up on the Test Summary Tab, Artifacts Tab and see the results in Insights for a specific component.

***Examples are using Lod-Composer, use data relevant to your component.***

***Caveat***: I did this working with xUnit tests, if you are using a different framework you may encounter some differences in implementation, but I don't think so.

**What are we trying to do?**

- We currently have test results show up in Circle CI from a console type display on that particular job. There are no historical views of this to help identify troublesome or inconsistent tests.
- By following the below we will see summary information on the Test Summary tab in Circle CI, we will also have a copy saved on the Artifacts Tab, and finally Insights will keep tabs on the last 10 failed jobs and rank them by frequency and run time.
- By adding the TRX file to the Artifacts Tab, we will be able to access this for our QL Quality Metrics Dashboard.


**Will I have to make any changes to my test solution?**

- No, everything is done via Circle CI. Note Caveat at the top of this page.


***See the finished Product:***
<ac:structured-macro ac:name="expand" ac:schema-version="1" ac:macro-id="52dd781b-154f-42f0-9ca6-8bd7ff72eadc"><ac:parameter ac:name="title">Before any changes we saw this</ac:parameter><ac:rich-text-body><p><strong>Test Summary Tab</strong></p><p><ac:image ac:height="150"><ri:attachment ri:filename="image2019-6-12_15-53-45.png"><ri:page ri:space-key="~pvarga" ri:content-title="How To integrate System Tests into Circle CI for Test Summary and Insights"></ri:page></ri:attachment></ac:image></p><p><strong>Artifacts Tab</strong></p><p><ac:image ac:height="150"><ri:attachment ri:filename="image2019-6-12_15-54-43.png"><ri:page ri:space-key="~pvarga" ri:content-title="How To integrate System Tests into Circle CI for Test Summary and Insights"></ri:page></ri:attachment></ac:image></p><p><strong>Insights View</strong></p><p><ac:image ac:height="150"><ri:attachment ri:filename="image2019-6-12_15-55-25.png"><ri:page ri:space-key="~pvarga" ri:content-title="How To integrate System Tests into Circle CI for Test Summary and Insights"></ri:page></ri:attachment></ac:image></p></ac:rich-text-body></ac:structured-macro>

<ac:structured-macro ac:name="expand" ac:schema-version="1" ac:macro-id="d2850f9a-a451-47e8-b14d-6612490a7275"><ac:parameter ac:name="title">After the below changes we now see this</ac:parameter><ac:rich-text-body><p><strong>Test Summary Tab</strong></p><ac:structured-macro ac:name="html" ac:schema-version="1" ac:macro-id="2bdd1efb-e71a-4f86-8bef-149b5813e8e7"><ac:plain-text-body><![CDATA[<b>Lod-Composer example Test Summary with Failures <a href="https://circleci.foc.zone/gh/LiftOff/lod-composer-api/817" target="_blank">Click Here</a>]]></ac:plain-text-body></ac:structured-macro><p><ac:image ac:height="250"><ri:attachment ri:filename="image2019-6-12_15-59-36.png"><ri:page ri:space-key="~pvarga" ri:content-title="How To integrate System Tests into Circle CI for Test Summary and Insights"></ri:page></ri:attachment></ac:image></p><p><br></p><p><strong>Artifact Tab</strong></p><ac:structured-macro ac:name="html" ac:schema-version="1" ac:macro-id="297b4dcc-1bc0-4f3b-8a5a-1eb714333026"><ac:plain-text-body><![CDATA[<b>Lod-Composer example Artifact Tab <a href="https://circleci.foc.zone/gh/LiftOff/lod-composer-api/817#artifacts/containers/0" target="_blank">Click Here</a>]]></ac:plain-text-body></ac:structured-macro><p><br><ac:image ac:height="250"><ri:attachment ri:filename="image2019-6-12_16-0-8.png"><ri:page ri:space-key="~pvarga" ri:content-title="How To integrate System Tests into Circle CI for Test Summary and Insights"></ri:page></ri:attachment></ac:image></p><p><br></p><p><strong>Insights View</strong></p><p class="auto-cursor-target"><br></p><ac:structured-macro ac:name="html" ac:schema-version="1" ac:macro-id="69ae4427-d0b5-48a5-b4c8-bcd0b0c28661"><ac:plain-text-body><![CDATA[<b>Lod-Composer Insights View <a href="https://circleci.foc.zone/build-insights/gh/LiftOff/lod-composer-api/master" target="_blank">Click Here</a>]]></ac:plain-text-body></ac:structured-macro><p class="auto-cursor-target"><br></p><p><ac:image ac:height="250"><ri:attachment ri:filename="image2019-6-12_16-0-42.png"><ri:page ri:space-key="~pvarga" ri:content-title="How To integrate System Tests into Circle CI for Test Summary and Insights"></ri:page></ri:attachment></ac:image></p></ac:rich-text-body></ac:structured-macro>


### Steps to Implement:

1. **The entirety of these changes are in the config.yml file for Circle CI in your component's directory.**
    1. **Find the "system\_tests:" job definition *<u>(See the Before and After section below for the actual code views)</u>***
        1. ***Add a step to Create Test Results Folders***
            1. mkdir /tmp/test-results && mkdir /tmp/test-results/LodComposer && mkdir /tmp/test-results/LodComposer/TRX
            2. Extensions are not enabled so you can't do this in one mkdir command
            3. Use your components name instead of Composer
        2. ***Add a step to Install the Trx2Junit tool***
            1. <ac:structured-macro ac:name="html" ac:schema-version="1" ac:macro-id="239a5a74-c363-4aff-8831-dbd7a990e008"><ac:plain-text-body><![CDATA[Circle CI <a href="https://discuss.circleci.com/t/nunit-test-summary/28272" target="_blank">requires the xml result to be in JUnit or Cucumber format. So we only need this package for this xml conversion.]]></ac:plain-text-body></ac:structured-macro>
            2. **command**: dotnet tool install -g trx2junit && echo 'export PATH="$[PATH:/root/.dotnet/tools](http://PATH/root/.dotnet/tools)"' &gt;&gt; $BASH\_ENV

                1. This installs the tool, then exports the Path so it can be used in subsequent steps
        3. ***Update the System Integration Tests step***
            1. Add the logger switch and param
                1. **command**: cd TestSuite && dotnet test LiftOff.Tests.LOD.LODComposer --logger:"trx;LogFileName=/tmp/test-results/LodComposer/TRX/LodComposerOut.trx"
                    1. Use data relevant to your component
                    2. <ac:structured-macro ac:name="html" ac:schema-version="1" ac:macro-id="d03842dc-0869-4f58-94f3-093880a5675d"><ac:plain-text-body><![CDATA[This creates a .trx result file that we will push to the Artifacts Tab so that it can be picked up by the <a href="https://shorty/qlqualitymetrics" target="_blank">QL Quality Metrics Dashboard]]></ac:plain-text-body></ac:structured-macro>
        4. ***Add a step to Convert the TRX file to Junit***
            1. trx2junit /tmp/test-results/LodComposer/TRX/LodComposerOut.trx --output /tmp/test-results/LodComposer/
            2. Add the when property so this runs regardless of failures in the tests
                1. **when**: always
                2. Without this there were intermittent runs when this step didn't execute
            3. This call the tool and provides it with the location of your TRX file. The tool converts it to junit xml and places it in the output location
        5. ***Add a step to publish the test results***
            1. ***store\_test\_results***
            2. Path to the ***xml***test results folder you created (/tmp/test-results/LodComposer)
            3. Use sub folders as makes sense to organize your component files
                1. Example: /tmp/test-results/&lt;Component&gt;
                2. I've used an extra TRX folder just to keep things in their place.
                3. /tmp already exists and the first step above creates the others. Update these if desired.
        6. ***Add a step to publish the test results to the Artifact Tab***
            1. ***store\_artifacts***
            2. Path to where you have your ***TRX***test results (/tmp/test-results/LodComposer/TRX)
        7. ***By creating Steps for each of these you will see them separated in the Timing Tab as well as to help troubleshoot if you are having problems.***
            1. ***Don't forget to reference the Before and After below that shows all the details including naming the steps, etc.***
    2. **Save this and push it up.** Once the workflow runs you should see the finished resulting stats in Circle CI going forward.


<ac:image ac:thumbnail="true" ac:height="250"><ri:attachment ri:filename="image2019-6-14_8-19-1.png"><ri:page ri:space-key="~pvarga" ri:content-title="How To integrate System Tests into Circle CI for Test Summary and Insights"></ri:page></ri:attachment></ac:image>

### Circle CI config.yml Before and After:
<ac:structured-macro ac:name="expand" ac:schema-version="1" ac:macro-id="1675c7ac-8a5d-4269-a713-d87cfe079ce0"><ac:parameter ac:name="title">config.yml Before Changes</ac:parameter><ac:rich-text-body><p class="auto-cursor-target"><br></p><ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="c02c3dde-a595-4539-bd46-ec481e6bd4af"><ac:parameter ac:name="language">yml</ac:parameter><ac:parameter ac:name="theme">Confluence</ac:parameter><ac:parameter ac:name="firstline">96</ac:parameter><ac:parameter ac:name="linenumbers">true</ac:parameter><ac:plain-text-body><![CDATA[system_tests: &system_tests
  <<: *netcore
  steps:
    - *enterprise_setup
    - run: git clone https://git.rockfin.com/LiftOff/LiftOffTests TestSuite
    - run:
        name: System Integration Tests
        command: cd TestSuite && dotnet test LiftOff.Tests.LOD.LODComposer]]></ac:plain-text-body></ac:structured-macro><p class="auto-cursor-target"><br></p></ac:rich-text-body></ac:structured-macro>

<ac:structured-macro ac:name="expand" ac:schema-version="1" ac:macro-id="ebc6e008-55f4-49d2-af8c-7ace9fa2c213"><ac:parameter ac:name="title">config.yml After Changes</ac:parameter><ac:rich-text-body><p class="auto-cursor-target"><br></p><ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="82ded8d1-ac64-4bdd-9fd8-07629b017081"><ac:parameter ac:name="language">yml</ac:parameter><ac:parameter ac:name="theme">Confluence</ac:parameter><ac:parameter ac:name="firstline">96</ac:parameter><ac:parameter ac:name="linenumbers">true</ac:parameter><ac:plain-text-body><![CDATA[system_tests: &system_tests
  <<: *netcore
  steps:
    - *enterprise_setup
    - run: git clone https://git.rockfin.com/LiftOff/LiftOffTests TestSuite
    - run:
        name: Create Test Results Directory
        command: mkdir /tmp/test-results && mkdir /tmp/test-results/LodComposer && mkdir /tmp/test-results/LodComposer/TRX    
    - run:
        name: Install trx2junit
        command: dotnet tool install -g trx2junit && echo 'export PATH="$PATH:/root/.dotnet/tools"' >> $BASH_ENV
    - run:
        name: System Integration Tests
        command: cd TestSuite && dotnet test LiftOff.Tests.LOD.LODComposer --logger:"trx;LogFileName=/tmp/test-results/LodComposer/TRX/LodComposerOut.trx"
    - run:
        name: Convert TRX results to JUnit
        command: trx2junit /tmp/test-results/LodComposer/TRX/LodComposerOut.trx --output /tmp/test-results/LodComposer/	when: always
    - store_test_results:
        path: /tmp/test-results/LodComposer
    - store_artifacts:
        path: /tmp/test-results/LodComposer/TRX   ]]></ac:plain-text-body></ac:structured-macro><p class="auto-cursor-target"><br></p></ac:rich-text-body></ac:structured-macro>



