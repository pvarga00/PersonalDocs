
<ac:structured-macro ac:name="toc" ac:schema-version="1" ac:macro-id="28c386b2-a06e-4a8e-ab9e-2ef1cda911e7"></ac:structured-macro>

# **Components and Contacts**

- LOD: <ac:link><ri:user ri:userkey="8a890360620700f901636d730bd700c2"></ri:user></ac:link>
- HIM/CM: <ac:link><ri:user ri:userkey="ff8080814973405c014985a6d46a0017"></ri:user></ac:link>
- EE: <ac:link><ri:user ri:userkey="8a8903605d45dfb2015de5866896004c"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a890360559efb1d01562af7402b0038"></ri:user></ac:link> <ac:link><ri:user ri:userkey="ff8080814a4b9bb3014ac64c2326005b"></ri:user></ac:link>
- InfoSec: <ac:link><ri:user ri:userkey="8a89036056d6e09d0157087407890011"></ri:user></ac:link>
- Architecture: <ac:link><ri:user ri:userkey="ff808081489ad5100148cd2f52b2002c"></ri:user></ac:link> <ac:link><ri:user ri:userkey="8a89036066fbfe6c01671408d2860003"></ri:user></ac:link>
- Checklist Engine: <ac:link><ri:user ri:userkey="8a8903604c9fa921014ca3ffd5c103c1"></ri:user></ac:link>


# **At Rest** 

When data is sitting on a Queue, Database and/or file.

- Field level - If the data represents a PII and PIFI then we need to encrypt those before persisting the data.
- Database level -Database level encryption is required on the database. EFS (Encrypted File System) solution is required for all persisted storage of data
- Disk level - Disk level encryption encrypts the disk where the data is stored. Just disk level is not enough


# **In Transit/Flight** 

When data is being transferred from a service to another service. TLS 1.2 is a requirement. See <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="NFR - Networking Security"></ri:page></ac:link>

- Field level - If the transport layer is encrypted the field level encryption is optional but is a good recommendation from InfoSec. But considering Liftoff components we made a decision to use encryption for PIFI fields even in transit.
- Transport layer - Service to Service communication should be always over HTTPS.


# **Key management services**

1. Mix cloud and on-prem - QKS recommended

    1. We will have a Lift Off-level QKS to be used across the system
2. Cloud only – KMS is recommended for services which are on AWS
3. On-Prem only – QKS is recommended for services which are on Prem


## **Lift Off QKS Keys**

- LiftOff QKS key – Test: [https://secretserver/SecretView.aspx?secretid=38940](https://secretserver/SecretView.aspx?secretid=38940)
- LiftOff QKS key – Beta: [https://secretserver/SecretView.aspx?secretid=38952](https://secretserver/SecretView.aspx?secretid=38952)


# **Logging**

- Logging of PII/PIFI fields in lower, non-prod environments is acceptable for debugging purposes. 
    - Ensure there is no risk of client data being used or exposed.
- Avoid logging PII/PIFI in production. If necessary in production, follow encryption standards.


# **PII**

Personally Identifiable Information

Individual PII fields do not need to be encrypted beyond the encryption used in the communication protocol

# **PIFI**

Personally Identifiable Financial Information

These fields must be encrypted in-flight and at rest beyond any EFS implementation. Encryption must happen before the data gets persisted or exposed.

For example, the Social Security Number MUST be encrypted in the HIM before it is published to the event queue. The ENCRYPTED version of the social security number would be persisted in the database and only decrypted when necessary.

## **Fields**

(Note: QKS is used to encrypt field level values so that they can be decrypted by internal QL services)


| PIFI Fields | PII Fields |
| --- | --- |
| <ul><li>Social Security Number</li><li>Account Identifier</li></ul> | <ul><li>First Name</li><li>Last Name</li><li>GCID for client</li><li>Email</li><li>Phone</li><li>Address</li><li>Loan number &nbsp;</li></ul> |




Notes:

1. <s>InfoSec is working on creating a master dictionary of what fields are constituted as PII, PIFI, PIE.</s>
2. InfoSec recommend separate keys for each PIFI data element i.e. separate key for SSN and separate key for Account Identifier.
3. InfoSec has recommended against any sort of PIFI truncation or masking. They did an analysis and determined that this was not adequate.


# **References**

Information Security Playbook [https://shorty/ThePlaybook](https://shorty/ThePlaybook)

Data Handling Standards – [https://shorty/PIFI](https://shorty/PIFI)

# **Meeting Notes**

## May 16, 2019

- Attendees
- Notes: For our TLS need Andrew suggested three different ways
    - Using API gateway with Ping
        - Adds extra hop and latency. Call will leave VPC since it going through API gateway
    - Open up port 443 to have a secure communication between services
        - Preferable since all the services are in the same VPC and can use internal urls without any special configurations
    - Services enforcing https
        - Not preferable


So we wanted to go with option 2. It requires a new terraform module to be created and Andrew is working on it and he will complete that this week. Each team is responsible to added this tfvar to their services.

If the service which is in different account is requesting data from liftoff services then it should use the api gateway with ping.



## May 15, 2019

- Attendees <ac:link><ri:user ri:userkey="8a890360620700f901636d730bd700c2"></ri:user></ac:link><ac:link><ri:user ri:userkey="8a8903604cb05139014cfb7c570e0146"></ri:user></ac:link><ac:link><ri:user ri:userkey="ff8080814973405c014985a6d46a0017"></ri:user></ac:link><ac:link><ri:user ri:userkey="ff8080814a4b9bb3014ac64c2326005b"></ri:user></ac:link><ac:link><ri:user ri:userkey="ff808081489ad5100148cd2f52b2002c"></ri:user></ac:link><ac:link><ri:user ri:userkey="8a89036066fbfe6c01671408d2860003"></ri:user></ac:link><ac:link><ri:user ri:userkey="8a890360681c62a00168234264140009"></ri:user></ac:link><ac:link><ri:user ri:userkey="8a890360559efb1d01562af7402b0038"></ri:user></ac:link>


Notes:

**<u>Encryption End to End</u>**
**<u>HIM</u>**

- Him is responsible for encryption of PIFI fields


**<u>LOD</u>**

- LOD should store whatever it gets, and it should be encrypting if there it gets plain text by any chance.
- The Lod get end point should have a flag to let LOD know whether to include PIFI fields in the response.
- Lod will send “**XXXXX**” if we get the flag as false and if there is data in that field, if it doesn’t have any value then send whatever the default value is. If the flag is true, then send the encrypted value.


**<u>Enrichment Engine</u>**

- Enrichment Engine should encrypt fields that are PIFI before sending event to LOD


**We will be using Lift Off key and QKS is the server which we want to leverage for all our encryption and decryption needs.**



**<u>Checklist Engine</u>**

- Not discussed in this meeting but want to broadcast here that CE will log the data that is encrypted without decrypting it.




## May 9, 2019

- Attendees: <ac:link><ri:user ri:userkey="8a890360620700f901636d730bd700c2"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814973405c014985a6d46a0017"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814973405c014985a2c9300016"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a890360559efb1d01562af7402b0038"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a890360681c62a00168234264140009"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814a27753d014a353fd6ed001f"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff8080814a4b9bb3014ac64c2326005b"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="ff808081489ad5100148cd2f52b2002c"></ri:user></ac:link>, <ac:link><ri:user ri:userkey="8a89036056d6e09d0157087407890011"></ri:user></ac:link>
- Work this sprint
    - LOD team worked on data at rest, using QKS
    - EE team worked on auditing logging to ensure any PIFI/PII is Debug level. Debug logging level will be turned off in Prod, so no PIFI/PII is logged
- We agreed on using QKS, since this is can be used in cloud and on-prem
    - KMS is acceptable if the particular traffic is only in AWS
- Data should be decrypted only when needed
    - Example flow 
        - EE Core will call LOD Composer API and receive lod with encrypted data
        - EE Core will call Evaluation Service (InRule) with lod still encrypted
        - Evaluation Service only evaluates if a field is null/empty, so there is no need to decrypt the data
        - EE Core will send EnrichmentDispatchEvent to EE Action with lod data still encrypted
        - EE Action may finally decrypt field level data only if need to call entity service(s)
- We will use a Lift Off-level QKS key (<ac:link><ri:user ri:userkey="8a890360620700f901636d730bd700c2"></ri:user></ac:link> to generate and store in secretserver)



