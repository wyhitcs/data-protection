# Usage Control


##Review

###Data Protection Mechanisms

* Access Control
  * Discretionary Access Control (DAC)
  * Mandatory Access Control (MAC)
  * Role-Based Access Control (RBAC)
* Trust Management
  * access control paradigm for decentralized systems
* Digital Right Management (DRM)

###Access Control

* Identity-based authorization
* Rights pre-defined and granted to subjects
* Repeated access until explicitly revoked
* Access decision at request time
* Enforcement at server side

<div align="center">
<img src="/Users/wangyu/Desktop/accesscontrol.png" width="350" height="150">
</div>

###Trust Management

* Credentials-based authorization
  * Credential: certified attribute of the subject
* Rights pre-defined and granted to subjects
* Repeated access until explicitly revoked
* Access decision at request time
* Enforcement at server side

###Digital Right Management (DRM)

* Control use of digital media
* Focus on intellectual property rights 
* Based on payment functions



* Limit copying, printing, and sharing 
* Prevent unauthorized use of proprietary documents (crypto) 
* Provide evidence of data misuse (digital watermarks) 
* Enforcement at

  * Server side
  * Client side

###Sample policies

* A user can use a service as long he has sufficient credit (servicecost is 10$/hour)

* An MP3 file can be listened at most 3 times

* There can be at most 10 accesses to an object at the same time

* In emergency, any doctor can access patient medical data


###Problems
* Access Control
  * Close system environment
  * No control on already disclosed object
  * No adaptability wrt context
  * No consumable rights
* Trust Management
  * Open system environment
  * No control on already disclosed object
  * No adaptability wrt context
  * No consumable rights
* Digital Right Management (DRM)
  * Lack of access control
  * No adaptability wrt context

##Outline

* Usage Control
* UCON<sub>ABC</sub>
