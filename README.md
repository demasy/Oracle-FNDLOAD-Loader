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
- **The .lct** file only defines the data structure, lacking actual data.
- **FNDLOAD** utilizes this file during both **DOWNLOAD** and **UPLOAD** operations.


#### Examples

<br>

| Entity Name                           | Configuration File   |
| :--------                             | :----   |
| Concurrent Programs                  | $FND_TOP/patch/115/import/**afcpprog.lct**|
| Request Groups                       | $FND_TOP/patch/115/import/**afcpreqg.lct**|
| Profile Options                      | $FND_TOP/patch/115/import/**afscprof.lct**|
| Menus                                | $FND_TOP/patch/115/import/**afsload.lct**|
| Workflow                             | $FND_TOP/patch/115/import/**wf.lct**|


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
FNDLOAD apps/password 0 Y UPLOAD $FND_TOP/patch/115/import/afcpprog.lct prog_XXDL_PROGRAM_NAME_us.ldt
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

### Concurrent Program Entities
These entities are responsible for managing the execution of concurrent requests and their dependencies.
 - <a href="https://github.com/demasy/Oracle-FNDLOAD-Loader/tree/main/src/content/fndload-entities/concurrents/concurrent-program">Concurrent Programs</a>
 - <a href="https://github.com/demasy/Oracle-FNDLOAD-Loader/tree/main/src/content/fndload-entities/concurrents/executable">Executables</a> 
 - <a href="https://github.com/demasy/Oracle-FNDLOAD-Loader/tree/main/src/content/fndload-entities/concurrents/request-groups">Request Groups</a>  
 - <a href="https://github.com/demasy/Oracle-FNDLOAD-Loader/tree/main/src/content/fndload-entities/concurrents/request-set">Request Sets</a> 
 - <a href="https://github.com/demasy/Oracle-FNDLOAD-Loader/tree/main/src/content/fndload-entities/concurrents/request-set-links">Request Set Links</a>
 
### Application Object Library (AOL) Entities
These entities refer to core application-level configurations used for validation, system settings, and flexfields.
  * Lookups
    * <a href="#">Lookup Types</a>
    * <a href="#">Lookup Values</a>
  * Profile Options
    * <a href="#">Profile Definitions</a>
    * <a href="#">Profile Option Values</a>
  * <a href="#">Messages Dictionary</a>
  * <a href="#">Attachments Setup</a>
  * Flexfields Setup
    * <a href="#">Key Flexfield Structures</a>
    * <a href="#">Descriptive Flexfields</a>
    * <a href="#">Value Sets</a>
   
### Security & Access Control Entities
These entities are responsible for defining user roles, controlling menu access, and managing function-level security in the Oracle E-Business Suite (EBS).
  * <a href="#">Users</a>
  * <a href="#">Responsibilities</a>
  * <a href="#">Menus</a>
  * <a href="#">Menu Entries</a>
  * <a href="#">Functions</a>
  * <a href="#">Forms</a>
  * <a href="#">Entry</a>
 
### Workflow & Approval Management Entities
These entities are used for business approvals and workflow.
  * <a href="#">Workflow (WFLOAD)</a>
  * Approvals Management Engine (AME)
    * <a href="#">Transaction Types</a>
    * Attributes & Attribute Definitions
      * <a href="#">Attributes</a>
      * <a href="#">Attribute Definitions</a>
      * <a href="#">Attribute Usages</a>
    * <a href="#">Conditions</a>
    * Approver Groups
      * <a href="#">Approver Groups Definitions</a>
      * <a href="#">Approval Group Configuration</a>
    * Rules & Rule Definitions
      * <a href="#">Rule Definitions</a>
      * <a href="#">Rule Usages</a>
      
### Reporting & BI Publisher (XDO) Entities
These entities are associated with reporting and template management in Oracle BI Publisher.
  * <a href="#">Data Definitions</a>
  * <a href="#">XML Templates</a>
  * <a href="#">RTF Templates</a>

### SOA, Integrations & Web ADI Entities
These entities facilitate integrations with external systems and allow data imports from desktop applications.
  * <a href="#">SOA Gateway</a>
  * <a href="#">Web ADI (Application Desktop Integrator)</a>
 
### Alerts Entity
These entities are utilized for alerts.
  * <a href="#">Alerts</a>

### Forms Personalization Entities
These entities are focused on enhancing the user interface of Oracle Forms to improve the overall user experience.
  * <a href="#">Forms Personalizations</a>

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
