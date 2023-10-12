# Service Virtualization Realized! (A Humble Article About Mountebank)

Image result for mountebank

## The Hook
Greetings Reader!

Welcome! and allow me me to pique your interest in a thought experiment: Wouldn't it be wonderful to be able to ensure that your application will work as expected, no matter if the underlying dependencies or systems that are needed for it run, are simply not available?

Your application's "user experience" is the single most important thing for your application's continued success, and your client's experience with your application is made up of several key factors: availability, dependability, and functionality...

How can you be sure that your application will "fail gracefully", or even CONTINUE to work, when you can't rely on consistent behavior from the downstream systems that your application relies on?

Wouldn't it also be grand to be able to continue working on your application, even though a key dependent system that you need to integrate with, is still evolving / under development / not even deployed yet?

Let me introduce you the delightful tool of Mountebank! With Mountebank, you can solve all of these problems, and MORE!

Come closer, really lean-in, read on!, and let me expound on the glorious virtues of Mountebank!



## Introduction to Mountebank
So what is Mountebank? Mountebank is a tool that solves for "Service Virtualization".

Service Virtualization is a way to emulate or fake the behavior of specific components in most API-driven applications, cloud-based applications, and service-oriented architectures (SOA), by providing "mocks" or canned responses to API requests.

Service Virtualization is used to provide software development teams access to (and control over) dependent system components that are needed to exercise an application under test (AUT), but are unavailable or difficult-to-access for development and testing purposes (think: click-charged API calls, or "PROD only" dependency systems).

With the behavior of the dependent components "virtualized," testing and development can proceed without accessing the actual "live" components/systems - by leveraging the mocked (imposter) responses instead. This is especially useful in testing certain scenarios about how a system will react (fail gracefully) - when a dependent system is no longer accessible or providing slow response times (which can be mocked) – allowing the "real/actual" system to behave normally.

Mountebank is the first open source tool to provide cross-platform, multi-protocol test doubles over the wire. Simply point your application to Mountebank instead of the real dependency, and test like you would with traditional stubs and mocks.

Mountebank is the most capable open source service virtualization tool in existence, and will cure what ails you, guaranteed!

Mountebank can be used to mock dependent API endpoints from other services. Mountebank can be used to create more available/maintainable API tests, or it can be used to mock performance scenarios such as retry polices and delayed responses.

    >>> MAGIC!!!!! >>>    Image result for magic


## Background/History : The Problem Mountebank Helps Solve (The Why and Practical Benefits of MB)
Historically, we've relied on ALL of our systems being ready, deployed, and actively available for our testing.

This means that we needed to deploy all of our systems, together, inter-dependently (tightly-coupled).

With Mountebank we can decouple the need for any downstream systems/data/scenarios availability, and allow us understand how our systems will behave under testing.

For example: Let's say we are the application owners of Yelp, which has a direct dependency on Google Maps for finding locations of businesses. Now let's say Google Maps experiences an outage or slowdown, or would Yelp fail completely, or could we test to ensure that our application (Yelp), would still be able to fail gracefully, or process requests for information in a diminished capacity, or even better yet, maybe failover to another geo-location provider (Waze, OsmAnd, etc.)?

Our clients would expect that OUR application, Yelp -- just plain works... regardless of whatever Google Maps does (to our application).

Mountebank allows us to answer these questions, without actually BEING in the "bad situation" first - but testing for it nonetheless!



- "Service Virtualization offers our application development teams the ability to test with certainty, faster, and with less dependencies!" - Peter Varga (me)



## Implementation Deets (Let's Get Geeky)
Lexicon/Terminology used by MounteBank and this Guide:
Note: The official terminology by Mountebank can be found in the documentation here

Imposter: mock representing your entire api/application
Stub: a complete block of code capturing your request and response information
Predicate: request information to be matched against (Part of a stub)
Response: response that should be send back (Part of a stub)


Mountebank provides the ability for API tests that typically make requests to an application, to instead call an "imposter" (think of it like this: "A test double" is like a "stunt double" in acting, who stands in for the real actor when things get dangerous).

An imposter can be thought of as a server representing a "test double".

An imposter is identified by a port and a protocol. Mountebank is non-modal and can create as many imposters as your tests require. An imposter is a pre-configured response to any request, with additional, optional post-processing information (ex: we can add additional latency to the response)

In the image, we see that our "Tests" make API requests to a "System Under Test" (SUT). The "SUT" would typically send an API response back to the test, which can then be verified as a correct response, or not. Things that can be tested in a response are: return codes (status of the request/response), headers, type, body, response times, etc.

Mountebank can then be used to intercept or proxy the requests the SUT's dependencies - and instead of expecting the SUT's dependency ("Real Service") to provide a response, Mountebank provides the response it has for the "imposter" instead. This is where the "magic' happens, as we can provide many types of "mocked responses" for a "SUT" to utilize.







Gump: Mountebank allows you to create "fake" downstream dependencies' API responses - so that you can test your API in isolation (without having to call the "real" dependency API).

Gump: Mountebank provides you the ability to create mocks for your dependent services, and shape the API responses that you're looking for.

Using mocks gives you the ability to:

Simulate still-in-development service(s) based off API contracts
Mock existing services for reasons of simplicity, repeatability, reliability, and "weird-scenarios" (500s, long latency, etc.)
It is recommended that you check the official Mountebank website for more detailed information: Mountebank's Website



A Learning Path:
A general workflow for understanding how Mountebank works: 

As a learner/user, you are simulating the "System Under Test," by making a request to Mountebank with a pre-determined API signature (coded in JS) emulating the path of the API you are mocking (want to fake out)
Mountebank serves up this response signature, and on all in-coming traffic checks each "imposter" to see if there is a predicate that is a match to the request signature
If there is a match, Mountebank will return the canned response specified, which then is returned to the user
Note: If there is no matching response to the calling API, then Mountebank can offer up a "default response", for example: "No mocked endpoint found"





Now there are many different options for configuring Mountebank - and we detail below starting with the easiest concepts to learn first, and we'll start building on some sample examples, and continue enhancing your knowledge:

Easiest Setup: Record and Replay
Moderate Setup: Predicate Matching, Modularized Setup
Expert Setup: (Predicate/Response) Injection, Behaviors


A proposed order of learning these concepts:

Record and Replay
Predicate Matching
Modularized Mocks
Injection
Behaviors




Record & Replay
Background:
Record and Replay is the most simplest setup for Mountebank. You can record the network calls to your API and save the recording. You can put the recording on replay mode, and test your calls against the recording. Recording leverages the proxy feature of Mountebank to record the calls.



Example:

Here is a sample flow (derived from Mountebank documentation) demonstrating how data flows during the recording feature. This is a sample example of proxyonce mode.

In this example your application (System under test) is dependent on application (real service)
You insert Mountebank in between the two applications
Now when your test triggers your application to make a call to real service, Mountebank will intercept and record the call and the response
It will save the recorded response, and on the next run Mountebank is aware of the call, and will the serve the recorded response right back (the recorded Mountebank imposter) without needing to go to the original service
Proxy Modes:
ProxyOnce: will capture the data once and ignore every additional call until recording stops.
ProxyAlways: will capture the data every single call and record it until recording stops.
ProxyTransparent: will not capture any data, just transfers your call to real service.
Additional details on recording can be found here

Setup Requirements:
Mountebank Server (Docker or Local Instance)
Postman
Setup Instructions:
Startup-Mountebank-Server
Start a local Mountebank server by entering the following command in your terminal:

$ mb

You should see something similar output in the terminal info:
[mb:2525] mountebank v2.1.0 now taking orders - point your browser to http://localhost:2525/ for help

Awesome now you have your Mountebank server up and ready!

Setup-MounteBank-Recording
Open Postman
Create a new POST request
Enter the following in request URL field: http://127.0.0.1:2525/imposters
Add the following header to your request: 
Content-Type: application/json
Add the following to your Post body:

Sample Code
{
    "port": 6568,
    "protocol": "https",
    "name": "MyRecording",
    "stubs": [
        {
            "responses": [
                {
                    "proxy": {
                        "to": "https://rickandmortyapi.com/api/",
                        "mode": "proxyOnce",
                        "predicateGenerators": [
                            {
                                "matches": {
                                    "method": true,
                                    "path": true,
                                    "query": true
                                }
                            }
                        ]
                    }
                }
            ]
        }
    ]
}
Submit the Post request
You should get a response 201 from the request
Mountebank is now ready to record any traffic going to rick: https://rickandmortyapi.com/api/
Record-Traffic
Create a new Postman GET Request
Send request to: https://localhost:6568/api/character/5
You should get a response 200 from the request
Record any additional responses you would like to capture
Save-Recording
Open a new terminal window
Enter the following command to save the recording: 
mb save --savefile recording.json
Mountebank will save the recording in the current working directory of terminal
Replay-Recording
Now you can use the recording to test your calls without relying on the actual service
Shutdown the mb server
Open the recording file and update a response field:
Example: \"name\":\"Jerry Smith\" update to: \"name\":\"Mock Response\"
Save the file
Start Mountebank server with following command:
mb --configfile recording.json
Send GET request again to: https://localhost:6568/api/character/5
You should see the name field update this time around


Predicate Matching
Background:
Predicate matching allows you to get a desired response even when you pass random data. Mountebank will read the data in your predicate, and reply using an appropriate response.

Predicate Matching Types: More Info
equals	requires the request field to equal predicate value
deepEquals	requires all the request fields to equal predicate value
contains	requires the request field to contain predicate value
startsWith	requires the request field to start with predicate value
endsWith	requires the request field to end with predicate value
Matches	requires the request field to match the regular expression provided as the predicate value
exists	requires the request field to exists as a nonempty value or not
not	inverts the subpredicate
or	requires any of predicate value to be matched
and	requires all of predicate value to be matched
Predicate Matching Fields:
You can match against any of your request field. For example, you can use the above matching types against headers, body, query string parameters or path.

Note: We will build on the example recording from the record/replay behavior.
Understanding the recording

Layout

The recording can be split in 2 major sections:
information about the API
information about routes, with responses for the API
Instructions:
Open the recording.json file from the record/replay tutorial
Let’s go through the recording:
You have the basic information about the API here:
Protocol: Mountebank supports multiple types of protocols -> https, http, tcp and smtp. Mountebank also allows you to create a custom protocol if you need one. Custom Protocol Docs
Port: the port at which you can access the mocks
Name: Name for your mocks
key/cert: Mountebank provides a set of Key and Certificate for https protocols. As soon as you start recording Mountebank will add its version of keys and certs
Stubs - you will have the information regarding your paths here
We will cover "contains" and "matches" in this tutorial. You can try out the rest by following the official documentation. More Info
Contains:
Let’s start with the first stub. It makes a call to get information about character 5. (Line 21)
Let’s change the deepEquals at line 20 and change it to contains
Save the file
Start Mountebank with the recording:
mb --configfile recording.json (Local Setup)
Start postman and make a get request to this route: 
/api/character/5 (Example: https://localhost:6568/api/character/5)
You should see the name in the response is mocked name
If you modify the route to: 
/api/character/5/test/contains
You should still get the same response back
Matches:
Shutdown Mountebank by pressing: 
ctrl + c
Go back to the recording.json and update line 58 to: 
"matches"
Update line 59:
character/6 
to: character/[a-z]
Save it and restart Mountebank again
If you make a request to character/6 you should get the response back from actual service
Update the request to character/a and you should get the response back with name: 
Mock Cluster Princess
Summary:
As you can see the predicate matching can be a powerful setup. If you were testing your API and you did not care what was passed in, but wanted to get the same, consistent, desired response back, you can use different types of predicate matching.





Modularized Setup
Background:
So far, so good -- but it is time to break down the "big (recorded) file" into a more maintainable and easier to understand setup

So, let’s get started!

Instructions:
Note: We will build on the example recording from the predicate matching module
Directory Setup:

Sample Code
src
├── exampleAPI              -> this folder will hold information about the routes for the API
│   ├── responses           -> this folder will hold information about the responses for the requests
│   │   ├── char5.json
│   │   ├── char6.json
│   │   └── char7.json
│   ├── stubs               -> this folder will hold information about the stubs for the API
│   │   ├── character.ejs
│   │   └── default.ejs
│   └── stubs.ejs           -> this file will hold information about the stubs for the API
└── imposters.ejs           -> this file will hold information about our imposters
Imposters.ejs

Let’s start by making a copy of recording.json over to the src folder
Copy the file and paste in the imposter.ejs
Clear all the contents for the stubs key in the json
It should look something like stubs: []
Add the following code to the stubs <% include exampleAPI/stubs.ejs %>
The stubs should look something like this now:

Sample Code
"stubs": [
    <% include exampleAPI/stubs.ejs %>
]
We have programmed Mountebank to include stubs from the exampleAPI folder during load time
Save the file
Stubs

We will start with creating few stubs for our imposter
For our recording we hit 2 routes: /api/character/ and the proxy to service
Let’s create 2 stubs for each of the routes:
Let’s call the first file character.ejs and save it in the exampleAPI/stubs folder
Let’s call the second file default.ejs and save it in the exampleAPI/stubsfolder
Open the character.ejs and let’s copy some data over from the recording.json
If using the same recording.json file lets copy all the stubs for api/character - line 12 - 125
Let’s clean up few things on the stubs:
Clear out the response body so it looks something like "body": " "
As the header won’t impact cause any impact on the response, you can delete most of the headers except content-type
You can delete the deepEquals query code block, since we won’t use it for the stubs
Once everything is cleaned up you should just have empty stub something similar to:

Sample Code
{
  "predicates": [
    {
      "deepEquals": {
        "method": "GET"
      }
    },
    {
      "contains": {
        "path": "/api/character/5"
      }
    }
  ],
  "responses": [
    {
      "is": {
        "statusCode": 200,
        "headers": {
          "Content-Type": "application/json; charset=utf-8"
        },
        "body": " ",
        "_mode": "text"
      }
    }
  ]
},
Cleanup all the predicates in the stubs and save the file
Copy over the stub for proxy to the default.ejs file and save it
Responses

Now that we have the stubs ready let’s move to the responses setup
If using the same recording.json file lets copy the body of the response and save it to responses/char5.json
Note - You can copy the response directly from the postman into the responses/char5.json
Let’s go back to Stubs and finish up the rest of setup.
Stubs Part 2

We have one quick update to make here. We just need to update the empty body tag.
Add the following code to map the response to the stubs file. <%- stringify(filename, './exampleAPI/responses/char5.json') %>
Your code should look something like this
  "body": "<%- stringify(filename, './exampleAPI/responses/char5.json') %>",
Stubs.ejs

Now that we have configured imposters.ejs and the stubs, lets edit the stubs.ejs file inside the exampleAPI folder to map everything together
If you followed the instructions above and if you have 2 stubs, you need to map those out in the stubs.ejs file
Your code should look something like
<% include stubs/character.ejs%>
<% include stubs/default.ejs%>
Note: the order of the stubs matter. If in the above example if you place the default stub above the character stub. The default will reach out the real service and you will never hit the mocks. So be sure of your ordering.
Running MB

open terminal and enter the following command to start Mountebank: mb --configfile imposters.ejs
open postman and make a GET request at https://localhost:6568/api/character/5
You should get the mock response back from Mountebank
Summary:
We broke down the big files into multiple chunks for easy maintenance. Here is a quick summary of data flow:

 responses --(send to)--> stubs --(send to)--> imposters


Injection (An Overview)
Background:
While Mountebank has a lot of power built into it, you can extend it even more by leveraging the injection feature. Using javascript injection allows to perform external logic that can be used as either a predicate or a response.

Although Mountebank provides advanced functionality to make your stubs smarter when you need them to be, your best bet is to not need them to be so smart. The dumber your virtual services can be, the more maintainable your test architecture will be.

Predicate Injection: Predicate injection allows you to pass a JavaScript function to decide whether the stub should match or not. Unlike other predicates, predicate injections bind to the entire request object, which allows you to base the result on multiple fields.

Response Injection: Response injection allows you to dynamically construct the response based on the request and previous requests. Mountebank will use the default value documented on the protocol page for any response fields you leave empty.

Mountebank passes the request object to both predicate and response injection functions, so you could put conditional logic based on the request in either location. Compared to response injection, predicate injection is relatively easy to use. If you need to send a static response back based on a dynamic condition, programming your own predicate and using an is response stays true to the intention of predicates in Mountebank.



Predicate Injection
Predicate Injection - Predicate injection allows you to pass a JavaScript function to decide whether the stub should match or not. Unlike other predicates, predicate injections bind to the entire request object, which allows you to base the result on multiple fields.

Instructions:
Note: We will build on the example from the modularized setup module.
Directory Setup: We are going to make few changes for the directory setup:

Sample Code
.
├── exampleAPI
│   ├── predicates  ->  this folder will hold the predicates we will inject into our stubs.
│   │   └── predicate.js
│   ├── responses
│   │   ├── char5.json
│   │   ├── char6.json
│   │   └── char7.json
│   ├── stubs
│   │   ├── character.ejs
│   │   └── default.ejs
│   └── stubs.ejs
└── imposters.ejs
Stubs Cleanup

Before we can start with the predicate, we need to cleanup few things. Let's start with updating character.ejs
You can combine matching predicates under the same condition for readability and maintenance purposes
Let's start with the predicate for character/5
Change the matching condition from deepEquals to equals
Combine path and method in the same matching condition
So, your code should look something like below:
"equals": {
  "method": "GET",
  "path": "/api/character/5"
}
Based on your conditions you can use matching conditions from Predicate Matching Module to combine the request contents
You can see additional cleanup in the attached examples
Let clean few things around response for character/5
We can remove majority of things from the response for readability
Remove _mode and cleanup header to match "Content-Type": "application/json"
Just keep required content you want in your response
You can see additional cleanup in the attached examples
Let's make one final change to the stubs/default.ejs
Update the response to following:
{
  "responses": [{ "is": { "statusCode": 400 } }]
}
New Stub Creation:

We are going to create a new stub to test out predicate injection
Create a new stub in the stubs/character.ejs file
Add the following code after the character/7 stub:

Sample Code
{
  "predicates": [{"inject": "<%- stringify(filename, './exampleAPI/predicates/predicate.js') %>"}],
  "responses": [{ "is": { "statusCode": 200 } }]
},

We are asking Mountebank to inject the JavaScript function in the predicate
Response is configured to send back a 200 response if the predicate matches
Predicate Injection File

Create a new file predicates/predicate.js
Add the following code to it:

Sample Code
(config) => {
  function IsJsonString(str) {
    try {
      JSON.parse(str);
    } catch (e) {
      return false;
    }
    return true;
  }
 
  if (config.request.method === 'POST') {
    if (config.request.headers['Content-Type'] === 'application/json') {
      return IsJsonString(config.request.body);
    }
  } else {
    return {
      statusCode: 400,
      headers: {
        "content-type": "application/json",
      },
      body: {
        "error": "Unsupported request"
      }
    };
  }
}


Let's break down the above snippet:
We are creating an anonymous function passing in the config parameter provided by Mountebank with every request and response. (config) =>
We have another function that does simple check whether the post body is a json string

Sample Code
function IsJsonString(str) {
  try {
    JSON.parse(str);
  } catch (e) {
    return false;
  }
  return true;
}
Finally, we have a condition to check if it is a POST request with application/json header
Test the Setup:

open terminal and enter the following command to start Mountebank mb --configfile imposters.ejs
Make a Post request to https://localhost:6568/api/character/
Add a simple post body to the request:

Sample Code
{
  "test": "Hello World"
}
Add the header Content-Type with value of application/json
When you send the request, you should see a status 200 returned
When you disable the header and send the request you should see a status 400 returned
Summary:

Predicate injection allows you match multiple request criteria before getting a response back


Response Injection
Instructions:
Response Injection - Response injection allows you to dynamically construct the response based on the request and previous requests. Mountebank will use the default value documented on the protocol page for any response fields you leave empty.

Note: We will build on the example from the modularized setup module
Directory Setup:

Sample Code
.
├── exampleAPI
│   ├── responses
│   │   ├── char5.json
│   │   ├── char6.json
│   │   ├── char7.json
│   │   └── response.js
│   ├── stubs
│   │   ├── character.ejs
│   │   └── default.ejs
│   └── stubs.ejs
└── imposters.ejs
Stubs Cleanup

Before we can start, we need to cleanup few things. Let's start with updating character.ejs
You can combine matching predicates under the same condition for readability and maintenance purposes
Let's start with the predicate for character/5
Change the matching condition from deepEquals to equals
Remove the path match condition from the predicate
So, your predicate should look something like below:

Sample Code
"predicates": [
  {
    "equals": {
      "method": "GET"
    }
  }
],
You can see additional cleanup in the attached examples
Let's clean few things around response for character/5
We can completely clear out the response and replace it with the response file we are going to inject
The response should look something like below with injection:


Sample Code
"responses": [{"inject": "<%- stringify(filename, './exampleAPI/responses/response.js') %>"}]
You can see additional cleanup in the attached examples
Response Injection File

Create a new file responses/response.js
Add the following code to it:

Sample Code
(config) => {
  if (config.request.method === 'GET') {
    if (config.request.path.includes('/api/character/5')) {
      let response = JSON.parse("<%- stringify(filename, '/exampleAPI/responses/char5.json') %>");
      response.fetchDate = new Date();
      return {
        headers: {
          "content-type": "application/json",
        },
        body: response
      }
    }
    if (config.request.path.includes('/api/character/7')) {
      let response = JSON.parse("<%- stringify(filename, '/exampleAPI/responses/char7.json') %>");
      response.status = 'Mountebank Injection'
      return {
        headers: {
          "content-type": "application/json",
        },
        body: response
      }
    }
  } else {
    return {
      statusCode: 400,
      headers: {
        "content-type": "application/json",
      },
      body: {
        "error": "Unsupported Request"
      }
    };
  }
}
Let's break down the above snippet:
We are creating an anonymous function passing in the config parameter provided by Mountebank with every request and response. (config) =>
We have an if condition to check for a GET request and the path on the request
Next we parse in the default response and add additional dynamic content to that response. In the case of character/5 we are adding current date time on every request
Test the Setup:

open terminal and enter the following command to start Mountebank mb --configfile imposters.ejs
Make a GET request to https://localhost:6568/api/character/5
Add the header Content-Type with value of application/json
When you send the request, you should see a status 200 returned with a response containing the date field we added to the response
Summary:

Response injection allows you to configure your responses to your liking.


Extending Our Mountebank Experience (Infrastructural Deets)
We have implemented a strategy to make it super easy for our development teams to merely check-in code for their mocks, and have Mountebank automatically deploy with their recently included changes, and be available for testing against in a matter of minutes.

Whenever a dev creates a new mocked endpoint, and commits a code change (into master) - a CircleCI pipeline workflow gets kicked off, and we automatically build and deploy Mountebank, with the new imposters/mocks included!

When the CircleCI workflow is completed, and Mountebank has been successfully deployed (with the new changes), you can now find the newly added endpoint(s) added.

Within the same Mountebank code repository, we also leverage Terraform scripts to automatically regenerate the infrastructure for Mountebank each time we deploy.



Sample Code
Our GIT Repo looks a little something like this:
- .circleci (all the Mountebank application deployment workflows/jobs)
- Infrastructure (all of the Mountebank Terraform Infrastructure scripts are here)
- Imposters (each of the application's mocks are here)
    - Application A
        - stubs, responses, defaults, etc. (*all* the .js/.ejs files!)
    - Application B
    - Application C
    - Etc.
- Dockerfile (everything needed to construct the Mountebank docker image)
Our Mountebank Dockerfile is pretty straightforward:

Sample Code
FROM alpine:3.8
 
EXPOSE 80
EXPOSE 2525
EXPOSE 4545
 
ARG LOG_LEVEL=info
 
###
#Mountebank Stuffs
###
ADD ./imposters /imposters
 
ENV NODE_VERSION=12.13.0
 
RUN apk add --update nodejs nodejs-npm
 
ENV MOUNTEBANK_VERSION=2.0.0
 
RUN npm set unsafe-perm true \
 && npm install -g mountebank@${MOUNTEBANK_VERSION} --production \
 && npm cache clean --force 2>/dev/null \
 && rm -rf /tmp/npm*
 
CMD ["mb", "--configfile=imposters/imposters.ejs", "--allowInjection", "--loglevel=debug"]


In order to deploy Mountebank, we essentially:

Create a Dockerized image of Mountebank (see above)
We utilize our internally built deploy tool: HAL to push the Mountebank docker image into AWS ECR
Launch and run the Mountebank docker image within an ECS Cluster
Load balance everything
And we protect everything behind a WAF (web-application-firewall)


Gliffy Macro Error

Cannot find a diagram with these parameters:

Name: MB-Infra


We offer this Mountebank stack for each of our SAFe Release Trains, with each application having a directory folder structure (as mentioned above), as we found that a single Mountebank instance can serve up mocks for a LOT of applications, and the performance is still pretty good

Note: Even though there have been no performance degradations encountered found thus far, if ever we do encounter any slowness due to the amount of load on Mountebank, we can always just spin up another, new Mountebank instance, and logically port over a few applications (more specifically, their mocks), into a new Mountebank deployed instance (and code repo)



Gliffy Macro Error

Cannot find a diagram with these parameters:

Name: MB


The process for our development teams to get started, is pretty simple:

Dev teams navigate to their Mountebank code repo
They go to the shared "imposters" folder,  (this is a collection of imposters for the entire Release Train)
They create a new folder named for their application that they want to generate mocked API endpoints for (imposters for the entire application)
Teams simply create a new stubs.ejs file, where they define all of the mocked API endpoints for their application
They then add the newly created stubs.ejs file to the parent, collection file: imposters.ejs
They check-in the new changes - and MAGIC! (Mountebank gets automagically deployed)
The development team then deploys their application, pointing their APIs to Mountebank mocks (instead of the "real/dependency APIs")
Note: This is typically done within an "app-config" file, and the process will be exactly the same as deploying your app to any TEST, BETA, STAGING, or PROD environment, you'll want to deploy your app to a "Mountebank-ized" environment (think: it's just a URL/string change for environment switching)
Teams can now test their application, without any "external/downstream dependencies"!

Summary
Mountebank helps with the "hard-to-test systems" that rely heavily on downstream dependencies, which are not easily testable under "normal circumstances"

Such constraints occur in complex, inter-dependent environments when a component connected to the application under test is:

Not yet completed/available (Gump: The dependent system is still evolving / under development / not deployed)
Controlled by a third-party or partner
Available for testing only in limited capacity, at inconvenient times, or with diminished available test cases
Difficult to provision or configure within test environment(s)
Needed for simultaneous access by different teams, with varied test data setup and other requirements (Think: slow response times, always available responses, etc.)
Restricted or costly to use for load and performance testing (Think: "Click charging")


Now that you've determined what type of mocks you want to implement, and you have enough background knowledge to be dangerous, go forth and implement some mocks, and profit!





Acknowledgements:
First and foremost: A very special thanks to Kyle Robertson , Derek Francis , and Bhavdeep Patel for their "unwitting" input and ideas! (I humbly stand on the shoulders of giants)

Secondly, thank you (sarcastically?), to Maciek Konkolowicz , who wrangled me into writing this article

Lastly, although all of the sources of this article are too numerous to reference them all, below you will find a few of them



Disclaimer: Any misunderstandings and/or misrepresentation of any information, is solely my own, and I take full responsibility

(... oh and I also take full credit for anything good that you may have benefitted from, in having read this article)

Additional Learning/Resources
Official Mountebank Site
Mountebank Code Examples
Mountebank Deployment Examples


Edit
User icon: PVarga
Communication Is Hard: But Having Empathy Can Help! [PART 2: Active Listening]
Peter Varga posted on Sep 20, 2016
In the first part of this article, Communication Is Hard: But Having Empathy Can Help! [PART 1], we investigated why communication is often difficult, and how having empathy can help. Next we'll explore some techniques that can help you to communicate more effectively.

 

Active Listening (also known as, Reflective Listening)
Because of the inherent complexity in communicating with others, it is critical to ask for and provide feedback during the conversation, which helps to ensure both parties are understanding a situation correctly.

A good practice to employ is called Reflective Listening, which is the process of repeating back what you think was said, in different words, to clarify understanding, and level set with the other person that you're both on the same page.

GUMP: Periodically, provide clear, concise summarizing statements to ensure understanding. 

You are now ACTIVELY listening... (...And not just thinking about what to say next....)

What is Reflecting?
Reflecting is the process of paraphrasing and restating both the feelings and words of the speaker.  The purposes of reflecting are:

To allow the speaker to 'hear' their own thoughts, and to focus on what they say and feel.
To show the speaker that you are trying to perceive the world as they see it, and that you are doing your best to understand their message.
To encourage them to continue talking, sharing their experience.
Reflecting does not involve you asking questions, introducing a new topic, or leading the conversation in another direction. Speakers are helped through reflecting, as it not only allows them to feel understood, but it also gives them the opportunity to focus their ideas.  This in turn helps them to direct their thoughts and further encourages them to continue speaking.

Mirroring
Mirroring is a simple form of reflecting, and involves repeating almost exactly what the speaker says. 

Mirroring should be short and simple.  It is usually enough to just repeat key words or the last few words spoken.  This shows you are trying to understand the speaker's terms of reference and acts as a prompt for him or her to continue. Be aware not to over mirror, as this can become irritating and therefore a distraction from the message.

Paraphrasing
Paraphrasing involves using other words to reflect what the speaker has said.  Paraphrasing shows not only that you are listening, but that you are attempting to understand what the speaker is saying. 

It is often the case that people 'hear what they expect to hear' due to assumptions, stereotyping or prejudices. When paraphrasing, it is of utmost importance that you do not introduce your own ideas or question the speaker's thoughts, feelings or actions.  Your responses should be non-directive and non-judgmental.

It is very difficult to resist the temptation to ask questions and when this technique is first used, since reflecting can seem very stilted and unnatural. You will need to practice this skill in order to feel comfortable and be natural.

Guidelines for Reflecting
Be natural - it will feel weird for both participants if you're not relaxed
Listen for the basic message - consider the content, feeling, and meaning expressed by the speaker
Restate what you have been told in simple terms
When restating, look for verbal and non-verbal cues that confirm or deny the accuracy of your paraphrasing  (Note that some speakers may pretend you have got it right because they feel unable to assert themselves and disagree with you)
Do not question the speaker unnecessarily
Do not add to the speaker's meaning
Do not take the speaker's topic in a new direction
Always be non-directive and non-judgmental
Be patient, kind, and review what was said - build on agreements
Focus on the topic at hand, (ignore the "other noise" for now), and take all the topics, one-by-one, in isolation


Distinguish what is actually happening from your idea about what is happening:

Notice how your emotions vary with those ideas
Ask yourself: What if this person is just like me?
What would cause them to do what they just did?
Before you can understand/know another, you must first learn to understand/know yourself
Empathic Congruence: Aligning Agreements, Understanding, and Building Empathy
Understanding Empathy - Ask Yourself These Questions:

What if I quit trying to be "Good Enough"? 
What would happen if I tried instead to be AMAZING? 
What is IMPORTANT to me? And what am I doing about protecting and improving those things?
Lastly, ask: What do I need to do to get there? ... Then DO it!
 

Going Forward, Things To Be Aware Of & General Tips:

Explain "Why": Set the stage/expectations EARLY. This is REALLY important! 
Address your specific points first, clearly, and Keep Your Message Simple. The fewer words that gets your point across, the better.
What information is needed : First 30 seconds of conversation : Gump it down
Leave out the extra stuff
Plan out what you are going to say
Take a pause often, and ask for clarification from others (creating a feedback loop)
Ensure the message sent is the message received
Head nods / verbal confirmation (parroting back)
Call out “silence” - polling for feedback (real-time) to refine communication
Engage in, and practice active listening 
Do not take a lot of notes. You'll be missing key nuances being communicated, non-verbally. Quickly jot down notes to remember something, and then re-engage in the conversation immediately
Do not jump in and talk over someone – wait for them to finish first
Only capture decisions and action items (and maybe reasons why) - Everything else is "noise"
Always be aware of your presence. People are watching what you do, and how you do it. Make sure you are displaying what you want people to see
Pause . Think . Act : Having a glass of water handy, and taking a sip before responding is a good trick to use when you need a moment
Offer unconditional positive regard... If you are sincere about it, if you give it, and expect it – you will receive it in return
Express Appreciation: Be genuine and actually tell the person about why you appreciate their actions. Trade expectations for appreciation, and the world changes instantly
Brene Brown said this about vulnerability : "It's the first I look for in others & the last thing I am willing to show others"
Have Self-Empathy: First understand the needs that motivate you - and then seek to understand motivations that drive others' behaviors
Have Confident Humility: Never feel like you don't belong. You belong here. EVERYONE feels the same way. Now go out there, and enhance the experience (for both yourself and others!)
Be Committed To Your Growth: Make mistakes, learn form them, and "always be getting better"
 

Personal Notes in Closing
While you cannot typically change another's behavior or reaction to a situation; you can influence your situation by first understanding another's point of view, helping them to see your point of view, and then working together to resolve a conflict. These actions will go a long way in building a lasting, collaborative relationship.

One of the best tools at your disposal is the ability to revisit a conversation repeatedly. When you revisit a complex conversation, your intentions are clearer: you know more about the questions the other has asked previously, you are more prepared on how you want to tell your story, you’ve assessed your mistakes, apologized for any transgressions, clarified beliefs, built a shared/common vocabulary, and focused on what’s truly important.

If you've already laid the groundwork for the next conversation, the likelihood of that next conversation being even more constructive is very high. And, the best part, you can re-visit the conversation as many times as it takes! 

 

Read these tips. Make them your own. Make them actionable. Do the work, and actively focus on being an effective communicator. 

...practice. Practice. PRACTICE!

 

"GUMPED":

Learn IT ... Implement IT ... Practice IT ... Teach IT ... Grow IT...

...and "IT" is "EVERYTHING".

 

I hope that these words, ideas, and tips will help you in your journey in becoming an even better, more effective communicator.

 

Acknowledgements
Disclaimer: I have blatantly stolen a lot of information/ideas from a variety of sources — although too numerous to reference them all, below you may find some of them. Any misunderstandings and/or misrepresentation of any information, is solely my own and I take full responsibility. (*AND* I also totally take full credit for anything good that you may have benefitted from, from having read this article!)

Additional Learning/Resources
- QL TechU: Communication Stars (TechU class)
- QL TechU: Communication Stars [REMOTE EDITION] (TechU class)
- QL TechU: Emotional Intelligence (TechU class)

