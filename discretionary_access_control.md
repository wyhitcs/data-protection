# Discretionary Access Control



##Outline
- Access Control
- Discretionary Access Control
- Safety Problem
- DAC weaknesses

##Access Control

###Computer Security Objectives
- Confidentiality
  - Information disclosed only to principals authorized to know it
  - Privacy:
    - right to be let alone (Warren and Bradeis, 1890)
    - right of the individual to decide when, what, why and who manage his personal information (Westin, 1970) 
    - freedom from unreasonable constraints on the construction of one’s own identity (Agre, 1999)
- Integrity
  - Information modified only by authorized principals and in the authorized ways
- Availability
  - Information accessible when it is needed (No denial of service)
###Access Control
- Goal: Protect confidentiality and integrity of information
- Control what a subject can do to prevent damage to the system
- Regulate the **operations** that can be executed by a **subject** on **data and resources**
- Typically provided as part of operating systems and of database management systems
  ![Access Control](C0A1990DB2C97F0BB28DA255824641B9.png)
- The basic idea of access control is that there is an _active_ subject requiring access to a _passive_ object to perform some specific access operation
- A _reference monitor_ grants or denies access

###Subjects
- Active entity performing operations in the system
- Subjects can be classified into:
  - users: single individuals connecting to the system
  - groups: sets of users
  - roles: a function or a position within a organization
  - processes: executing programs on behalf of users
- Relations may exist among the various types of subject

###Objects
- Any system resource (file, printer, etc.)
- _Protection objects_: objects controlled by access control system
- Note: not all resources managed by a system need to be protected
- **Advanced Objects: subjects**

###Access Rights
- Operations that a subject can execute on protection objects
- Each type of operation corresponds(相符合, 相一致;相当, 相类似;通信) to an _access_ right
  - access control must be able to control the specific type of operation
- The most simple example of access rights is:
  - read: look at the contents of an object
  - write: change the contents of an object
- Other types of rights depending on the resources to be protected
  - execute, select, insert, update, delete, etc.
- Advanced Rights: ownership, delegate(代表, 代表团成员;vt. 任命或委派…为代表;托付), remove

###Subjects, Objects, Access Rights in Unix
Subjects: users, groups
Objects: files, directories
Access rights: read, write, execute

- For files
  - read: reading from a file
  -  write: writing to a file
  -   execute: executing a (program) file
- For directories
  - read: list the files within the directory
  - write: create, rename, or delete files within the directory
  - execute: enter the directory

###Access Control vs. Authentication
Completely different things
 
Authentication: Establishing who you are(whether a user possesses a certain pseudonym/attribute or not)

Access Control: Establishing if a user has the right of doing a certain operation

Authentication is necessary for access control

###Policies, Models, Mechanisms

**Policy**: define (high-level) guidelines and rules describing the accesses to be authorized by the system
 
**Model**: formally define the access control specification and enforcement

**Mechanism**: implement the policies via low level (software and hardware) functions


###Separation between policies and mechanisms

Discuss access requirements **independently** from their implementation

**Compare** different access control policies as well as different mechanisms that enforce the same policy

Design mechanisms able to **enforce multiple policies**

###Security policies
- Access control policies: define who can access a resource
  - Discretionary(DAC)
  - Mandatory(MAC)
  - Role-based(RBAC)
  - Attribute-based(ABAC)
- Administrative policies: define who can specify access control policies
  - Usually coupled with DAC, RBAC and ABAC

##Discretionary Access Control (DAC)
- Intuitions:
  - The owner of a resource decides who can access it
  - Access rights can be delegated to other users
- Intended Environment:
  - Operating systems in the late 60s
  - Users are members of the same community: objective is to protect data from mistakes of others(cd/; rm-fr *)
  - Currently the most used in corporate environments
    >The basis for DAC is that an individual user (or program on its behalf) is allowed to specify explicitly the types of access other users (or programs on their behalf) may have to information under the user’s control ------NCSC (National Computer Security Center)
- Entities:
  - Subjects: who have privileges and can do operations on objects
  - Objects: files, resources, programs
  - Access Rights: what a subject can do on a object
- Main features
  - Ownership: Users have all the rights about the objects they create
    - when users create objects, they own them
  - Delegations: Users can give certain rights to other users
    - users can grant rights they have, to others
    - users that have control can remove rights

###DAC Models
- Take-grant model
- **Lampson(1974)**
- Graham-Denning(1972)
- **Harrison-Ruzzo-Ullman(1976)**
- Griffiths-Wade(1976)
- Originator control(1989)

###Lampson: Access Matrix
- Set of subjects S
- Set of objects O
  - subjects can be considered as objects, i.e., S ⊆ O
- Access Matrix A(S × O)
  - Entries contain sets of rights
    - access rights: read, write, call, etc.
    - administration rights: own, control
    - delegation rights: flags"*" and "+"

####Sample Access Matrix 见22
- “own” can add any rights
- “control” is the right to remove rights from a subject (in Lampson’s work, in other models ownership includes control)
- “*” flag can delegate rights to other subjects

####Q&A 见23-24

####Access Matrix: Implementation
- Matrix is generally large and sparse
  - Storing the entire matrix is waste of memory space
- Alternative approaches
  - Authorization table: store table of non-null triples(s,o,a)-->used in DBMS
  - Access control lists(ACLs): Stored by column
  - Capability lists: Stored by row

####Authorization table
![###Authorization table](BA93262851EF6CEA620C3A82825B6BC2.png)

####Access control lists vs. Capability lists
![Access control lists vs. Capability lists](53E04535F20C42DBBAE2EC9F376F4526.png)
Access control lists 
- Objects are the starting point (per-object basis)
- Require authentication of subjects
- Superior for access control and revocation on per-object basis
  Capability lists
- Subjects are the starting point (per-subject basis)
- Require control of propagation of capabilities
- Superior for access control and revocation on per-subject basis
  The per-object basis usually more convenient
  Most systems based on ACLs

###Harrison-Ruzzo-Ullman (HRU) Model----------------
Define authorization system
- State(S,O,A)
  - S set of subjects
  - O set of objects
    - subject can be considered as objects( i.e.,S ⊆ O)
- Access Matrix A(S × O))
  - rows correspond to subjects
  - columns correspond to objects
  - A[s,o] indicates the privilege of s on o
- **State transitions** described by commands
  - commands defined as sequences of primitive operations
  - **enter** _r_ into A[s,o], **delete** _r_ from A[s, o], **create subject** s<sup>'</sup> ,
    **destroy subject** s<sup>'</sup> , **create object** o<sup>'</sup> , **destroy object** o<sup>'</sup>

###Primitive operations
![Primitive operations1](847AF5E6E879C86E215C4E6986FCFEC7.png)
![Primitive operations2](7E70E2B5F93928A7FA9D9FAF431BAD7A.png)

###Commands
Changes to the system state modeled by commands of the form
![commands](E15316BADEC9EBFA3092E53DF56B6178.png)
with r<sub>1</sub>,...,r<sub>m</sub> rights and op<sub>1</sub>,...,op<sub>n</sub> primitive operations
Examples:
![command examples](C87FD6FC8CBF9434DA7F3F05EEBD3850.png)

###Transfer of privileges
Delegation of authority by attaching flags to privileges(e.g.,* copy flag, + transfer-only flag)
- copy flag(*): subject can transfer privilege to others
  ![flag](56B57524F092898516163CD89498C15E.png)
- transfer-only flag(+): subject can transfer privilege to others (and the flag on it), but he loses the privilege
  ![+flag](2094561D9AE4E0F8EEFF2D56FCB856DF.png)

###State transitions-------------------------

###Exercise 见35

##Safety Problem

###Fundamental Questions
- How can we determine whether a system is secure? 
  - Need to define what we mean by a system being “secure”
- Is there a generic algorithm that allows us to determine whether a computer system is secure?

###Safety and Liveness-------------

###Examples: ------------

###When is a systme secure?----------------

###Exercise 见46-47

###HRU: Safety Problem
Safety problem: Given an initial state (S,O,A) and a right r , is there any sequence of commands leaking r?

###HRU and Safety: "Desired" leaks-------------------

###Exercise 见50-59

###Safety problem: Decidability-------------------------

###Safety problem: Some bad news-------------

###Safety problem: Good news?-----------

##DAC weaknesses-----------------

















