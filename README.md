# Oracle FNDLOAD Loader

The Generic Loader (**FNDLOAD**) is a powerful Oracle E-Business Suite (EBS) concurrent program designed for transferring configuration data between **databases** and **human-readable text files** with the **.ldt** extension. This utility facilitates the automated migration of Application Object Library (AOL) objects, significantly reducing the need for manual reconfiguration across Development (DEV), Test (UAT), and Production (PROD) environments.

The **FNDLOAD** utility utilizes a **configuration file (.lct)** that defines the structure and access methods for **extracting** and **uploading** data. This process ensures seamless and error-free migrations of various components, including menus, responsibilities, profile options, concurrent programs, workflows, and more.

<br>

## Understanding FNDLOAD File Types
FNDLOAD utilizes two primary types of files to transfer configurations between Oracle EBS environments:

### Configuration File (.lct)
- The **.lct** file, also known as the Loader Control File, specifies the data and structure to be extracted.
- It serves as a blueprint for migrating specific entities, such as Concurrent Programs, Menus, Responsibilities, and more.
- Each entity is associated with its **.lct** file, which Oracle provides in the **$FND_TOP/patch/115/import/**.

#### Examples

<br>

| Entity Name                           | Configuration File   |
| :--------                             | :----   |
| Concurrent Programs                  | $FND_TOP/patch/115/import/**afcpprog.lct**|
| Request Groups                       | $FND_TOP/patch/115/import/**afcpreqg.lct**|
| Profile Options                      | $FND_TOP/patch/115/import/**afscprof.lct**|
| Menus                                | $FND_TOP/patch/115/import/**afsload.lct**|
| Profile Options                      | $FND_TOP/patch/115/import/**wf.lct**|

##### How does it work?
- **The .lct** file only defines the data structure, lacking actual data.
- **FNDLOAD** utilizes this file during both **DOWNLOAD** and **UPLOAD** operations.

<br>

> Oracle advises against modifying .lct files, which can lead to data corruption. Always use the official .lct files provided by Oracle.

<br>

### Data File (.ldt)
- The **.ldt** file (Loader Data File) contains extracted configuration data structured in a specific format.
- This file is generated when configurations are downloaded from an Oracle EBS instance.
- It can be transferred and uploaded to another instance using the FNDLOAD utility.

<br>

 #### Examples

<br>

| Entity Name                           | Example Data File (.ldt)   |
| :--------                             | :----   |
| Concurrent Programs                   | program.ldt |
| Menus                                 | menu.ldt |
| Profile Options                       | profile.ldt |
| Workflow                              | workflow.ldt|

<br>

## How FNDLOAD Works?
FNDLOAD functions in two primary modes:

### Download Mode:
This mode extracts data from an Oracle EBS database and saves it in a structured text file with a .ldt extension.

### Upload Mode:
FNDLOAD reads a previously extracted .ldt file and loads the configuration into a target Oracle EBS database in this mode.

<br>
 
This process guarantees automated migrations of menus, responsibilities, profile options, concurrent programs, workflows, and more, ensuring consistency and error-free results.

<br>
<p align="center">
 <img src="https://github.com/demasy/Oracle-FNDLOAD-Loader/blob/main/src/resources/images/how-fndload-works-diagram.png">
</p>

<br>

FNDLOAD DOWNLOAD generates a .ldt file from Oracle E-Business Suite (EBS).

``` shell
FNDLOAD apps/password O Y DOWNLOAD $FND_TOP/patch/115/import/afcpprog.lct prog_XXDL_PROGRAM_NAME_us.ldt PROGRAM APPLICATION_SHORT_NAME="XXDL" CONCURRENT_PROGRAM_NAME="XXDL_PROGRAM_NAME"
```
<br>

Transfer the .ldt file to the target environment.

``` shell
scp prog_XXDL_PROGRAM_NAME_us.ldt applmgr@target_server:/u01/demasy/src/migrations/fndload/program/
```

<br>

The command FNDLOAD UPLOAD imports data into the target instance.

``` shell
FNDLOAD apps/password 0 Y UPLOAD $FND_TOP/patch/115/import/prog_XXDL_PROGRAM_NAME_us.lct program.ldt
```

<br>

## FNDLOAD Executable Syntax 

The Generic Loader is a concurrent program called FNDLOAD. This concurrent executable accepts the following parameters:

> **FNDLOAD {apps/password} {0 Y} {mode} {configfile} {datafile} {entity} [optional {param} {param}]**

<br>

| Code      | Variable                   | Description                   |
| :-:       | :-----------                  | :--------------------------   |
| 1         | {apps/password}       | The APPS schema and password       |
| 2         | {0 Y}                      | Concurrent program flags       |
| 3         | {mode}                     | UPLOAD or DOWNLOAD <br> - **DOWNLOAD** causes the loader to fetch rows and write them to the datafile. <br> - **UPLOAD** causes the datafile to be uploaded to the database. |
| 4         | {configfile}               | The configuration file to use (usually with a suffix of .lct, but not enforced or supplied by the loader).       |
| 5         | {datafile}                 | The data file to write (usually with a suffix of .ldt, but not enforced or supplied by the loader). If the data file already exists, it will be overwritten.       |
| 6         | {entity}                   | The entity(ies) to upload or download. When uploading, you should always upload all entities, so specify a "-" to upload all entities.       |
| 7         | [optional {param} {param}] | Zero or more additional parameters are used to provide bind values in the access SQL (both UPLOAD and DOWNLOAD). Each parameter is in the form NAME=VALUE. NAME should not conflict with an attribute name for the entities being loaded.       |

<br>

### Example

###### Download
```
FNDLOAD apps/password 0 Y DOWNLOAD $FND_TOP/patch/115/import/<configfile>.lct <datafile>.ldt [entity] [parameters]
```

###### Upload
```
FNDLOAD apps/password 0 Y UPLOAD $FND_TOP/patch/115/import/<configfile>.lct <datafile>.ldt
```


<br>

## **FNDLOAD Supported Entities**

### Concurrent Processing Entities
These entities are responsible for managing the execution of concurrent requests and their dependencies.
 - Concurrent Programs
 - Executables
 - Request Groups
 - Request Sets
 - Request Set Links
 
### Application Object Library (AOL) Setup Entities
These entities refer to core application-level configurations used for validation, system settings, and flexfields.
  * Lookups
    * Lookup Types
    * Lookup Values
  * Profile Options
    * Profile Definitions
    * Profile Option Values
  * Messages Dictionary
  * Attachments Setup
  * Flexfields Setup
    * Key Flexfield Structures
    * Descriptive Flexfields
    * Value Sets
   
### Security & Access Control Entities
These entities are responsible for defining user roles, controlling menu access, and managing function-level security in the Oracle E-Business Suite (EBS).
  * Users
  * Responsibilities
  * Menus
  * Menu Entries
  * Functions
  * Forms
  * Entry
 
### Workflow & Approval Management Entities
These entities are used for business approvals and workflow.
  * Workflow (WFLOAD)
  * Approvals Management Engine (AME)
    * Transaction Types
    * Attributes & Attribute Definitions
      * Attributes
      * Attribute Definitions
      * Attribute Usages
    * Conditions
    * Approver Groups
      * Approver Groups Definitions
      * Approval Group Configuration
    * Rules & Rule Definitions
      * Rule Definitions
      * Rule Usages
      
### Reporting & BI Publisher (XDO) Entities
These entities are associated with reporting and template management in Oracle BI Publisher.
  * Data Definitions
  * XML Templates
  * RTF Templates

### SOA, Integrations & Web ADI Entities
These entities facilitate integrations with external systems and allow data imports from desktop applications.
  * SOA Gateway
  * Web ADI (Application Desktop Integrator)
 
### Alerts & Monitoring Entities
These entities are utilized for automated alerts and notifications within the system.
  * Alerts

### Forms Customization & Personalization Entities
These entities are focused on enhancing the user interface of Oracle Forms to improve the overall user experience.
  * Forms Personalizations

<br>

## **Configuration File**

<br>
 
| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 1.1    | <a href="#">Concurrent Programs</a>                  | $FND_TOP/patch/115/import/**afcpprog**.lct|
| 1.2    | <a href="#">Request Groups</a>                  | $FND_TOP/patch/115/import/**afcpreqg**.lct|
| 1.3    | <a href="#">Lookup: Lookup Types</a>                  | $FND_TOP/patch/115/import/**aflvmlu**.lct|
| 1.4    | <a href="#">Lookup: Lookup Values</a>                  | $FND_TOP/patch/115/import/**aflvmlu**.lct|
| 1.5    | <a href="#">Profile Option: Definition</a>                  | $FND_TOP/patch/115/import/**afscprof**.lct|
| 1.6    | <a href="#">Profile Option: Values</a>                  | $FND_TOP/patch/115/import/**afscprof**.lct|
| 1.7    | <a href="#">Flexfield: Key flexfields</a>                  | $FND_TOP/patch/115/import/**afffload**.lct|
| 1.8    | <a href="#">Flexfield: Descriptive flexfields</a>                  | $FND_TOP/patch/115/import/**afffload**.lct |
| 1.9    | <a href="#">Flexfield: Value sets</a>                  | $FND_TOP/patch/115/import/**afffload**.lct|
| 1.10   | <a href="#">Attachments</a>                  | $FND_TOP/patch/115/import/**afattach**.lct|
| 1.11   | <a href="#">Messages</a>                  | $FND_TOP/patch/115/import/**afmdmsg**.lct|
| 1.12   | <a href="#">Security: Menu</a>                  | $FND_TOP/patch/115/import/**afsload**.lct|
| 1.13   | <a href="#">Security: Function</a>                  | $FND_TOP/patch/115/import/**afsload**.lct|
| 1.14   | <a href="#">Security: Form</a>                  | $FND_TOP/patch/115/import/**afsload**.lct|
| 1.15   | <a href="#">Security: Entry</a>                  | $FND_TOP/patch/115/import/**afsload**.lct|

<br>

### Alerts

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 2.1    | <a href="#">Alert</a>                 | $ALR_TOP/patch/115/import/**alr**.lct|

<br>


### Approvals Management Engine (AME)

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 3.1    | <a href="#">Transaction Types</a>                 | $AME_TOP/patch/115/import/**amesrulk**.lct|
| 3.2    | <a href="#">Attribute</a>                 | $AME_TOP/patch/115/import/**amesattr**.lct|
| 3.2    | <a href="#">Attribute: Definitions</a>                 | $AME_TOP/patch/115/import/**amesatdf**.lct|
| 3.3    | <a href="#">Attribute: Usages</a>                 | $AME_TOP/patch/115/import/**amesatus**.lct|
| 3.4    | <a href="#">Conditions</a>                 | $AME_TOP/patch/115/import/**amescond**.lct|
| 3.5    | <a href="#">Approver Group</a>                 | $AME_TOP/patch/115/import/**amesagrp**.lct|
| 3.5    | <a href="#">Approver Group: Definitions</a>                 | $AME_TOP/patch/115/import/**amesagdf**.lct|
| 3.6    | <a href="#">Approver Group: Configuration</a>                 | $AME_TOP/patch/115/import/**amesagco**.lct|
| 3.7    | <a href="#">Rule: Definitions</a>                 | $AME_TOP/patch/115/import/**amesrulk**.lct|
| 3.8    | <a href="#">Rule: Usages</a>                 | $AME_TOP/patch/115/import/**amesruus**.lct|

<br>

### Business Intelligence (BI) Publisher (XDO)

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 4.1    | <a href="#">Data Definitions</a>                 | $XDO_TOP/patch/115/import/**xdotmpl**.lct|
| 4.2    | <a href="#">XML Template</a>                 | $XDO_TOP/patch/115/import/**xdotmpl**.lct|

<br>

### Web Applications Desktop Integrator (Web ADI)

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 4.1    | <a href="#">Integrators</a>                 | $BNE_TOP/patch/115/import/**bneintegrator**.lct|

<br>

### Generic

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 5.1    | <a href="#">Responsibility</a>        | $FND_TOP/patch/115/import/**afscursp**.lct|
| 5.2    | <a href="#">Users</a>                 | $FND_TOP/patch/115/import/**afscuur**.lct|
| 5.3    | <a href="#">Request Set</a>           | $FND_TOP/patch/115/import/**afcprset**.lct|
| 5.4    | <a href="#">Request Set Link</a>      | $FND_TOP/patch/115/import/**afcpreqs**.lct|
| 5.5    | <a href="#">SOA Gateway</a>           | $FND_TOP/patch/115/import/**soa**.lct|

<br>



### WFLOAD

| Code   | Entity Name                           | 
| :-     | :--------                             | 
| 6.1    | <a href="#">Workflow</a>              |


<br>


## Contributors

| Author | GitHub & LinkedIn account |
| :-  | :---- |
| Ahmed El-Demasy (Original Author) | <a href="https://github.com/demasy">Github</a> & <a href="https://www.linkedin.com/in/demasy">LinkedIn</a> |
<br>

 ### Contributing to the Oracle FNDLOAD scripts
We welcome you to join and contribute to the Oracle FNDLOAD Scripts. If you are interested in helping, please don’t hesitate to contact on e-mail: founder@demasy.io

<br>

###### Suggestions & Issues
> If you find any issue or have a great idea in mind please create an issue on <a href="https://github.com/demasy/Oracle-FNDLOAD-Loader/issues">GitHub</a>.
