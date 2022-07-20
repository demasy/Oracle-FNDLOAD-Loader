# Oracle FNDLOAD Scripts

The Generic Loader (FNDLOAD) is a concurrent program that can move Oracle E-Business Suite data between database and text file representations. The loader reads a configuration file to determine what data to access. For information on specific configuration files consult the Open Interfaces Guide for your product group. The following sections describe the operation of the Generic Loader.

<br>

## FNDLOAD Executable Syntax 

The Generic Loader is a concurrent program named FNDLOAD. The concurrent executable takes the following parameters:

> **FNDLOAD {apps/APPS_PASSWORD} {0 Y} {mode} {configfile} {datafile} {entity} [optional {param} {param}]**

<br>

| Code      | Variable                   | Description                   |
| :-:       | :--------                  | :--------------------------   |
| 1         | {apps/APPS_PASSWORD}       | The APPS schema and password       |
| 2         | {0 Y}                      | Concurrent program flags       |
| 3         | {mode}                     | UPLOAD or DOWNLOAD <br> - **UPLOAD** causes the datafile to be uploaded to the database. <br> - **DOWNLOAD** causes the loader to fetch rows and write them to the datafile.|
| 4         | {configfile}               | The configuration file to use (usually with a suffix of .lct, but not enforced or supplied by the loader).       |
| 5         | {datafile}                 | The data file to write (usually with a suffix of .ldt, but not enforced or supplied by the loader). If the data file already exists, it will be overwritten.       |
| 6         | {entity}                   | The entity(ies) to upload or download. When uploading, you should always upload all entities, so specify a "-" to upload all entities.       |
| 7         | [optional {param} {param}] | Zero or more additional parameters are used to provide bind values in the access SQL (both UPLOAD and DOWNLOAD). Each parameter is in the form NAME=VALUE. NAME should not conflict with an attribute name for the entities being loaded.       |

<br>

### Example

###### Download
```
FNDLOAD
```

###### Upload
```
FNDLOAD
```


<br>

## **FNDLOAD Entities**


- Oracle AOL Configuration
  * Concurrent Programs
  * Application Lookups
  * Application Messages
  * Profile Options
  * Flexfields
  * Security Information
    * Menu
    * Function
    * Form
    * Entry
- Alerts
- Attachments
- AME
- XDO
- SOA Gateway
- Workflow

<br>



### Security Configuration

| Code      | Entity Name                           | Configuration File   |
| :-        | :--------                             | :----   |
| 1.1      | <a href="#">Menu</a>                                  | afsload.lct|
| 1.2      | <a href="#">Function</a>                              | afsload.lct|
| 1.3      | <a href="#">Form</a>                                 | afsload.lct|
| 1.4      | <a href="#">Entry</a>                                | afsload.lct|


<br>

### Oracle AOL Configuration

| Code      | Entity Name                           | Configuration File   |
| :-        | :--------                             | :----   |
| 1.1      | <a href="#">Menu</a>                                  | afsload.lct|





### Generic

| Code      | Entity Name                           | Configuration File   |
| :-        | :--------                             | :----   |
| 1.1      | <a href="#">Menu</a>                                  | afsload.lct|


<br>



| Code      | Entity Name                           | Configuration File   |
| :-        | :--------                             | :----   |
| -         | **Oracle Application Object Library** | -       |
| 1         | <a href="https://github.com/demasy/Oracle-FNDLOAD-Scripts/tree/main/fndload-entities/responsibility">Responsibility</a>                        | afscursp.lct       |
| 2         | <a href="https://github.com/demasy/Oracle-FNDLOAD-Scripts/tree/main/fndload-entities/users">Users</a>                                 | afscursp.lct       |
| 3         | <a href="#"> Concurrent program definitions</a>         | afcpprog.lct       |
| 4         | <a href="#">Request groups</a>                         | afcpreqg.lct       |
| 5.1       | <a href="#">Request Set</a>                            | -|
| 5.2       | <a href="#">Request Set Link </a>                     | -|
| 5.3       | <a href="#">Alert</a>                                 | -|
| 6         | <a href="#">Attachments definitions</a>               | afattach.lct       |
| 7         | <a href="#">Messages</a>                              | afmdmsg.lct       |
| 8         | **Lookups**                           | aflvmlu.lct       |
| 8.1       | <a href="#">Lookup types</a>                           | -       |
| 8.2       | <a href="#">Lookup values</a>                         | -       |
| 9         | **Profile options**                   | afscprof.lct       |
| 10.1      | <a href="#">Profile option definitions</a>            | -       |
| 10.2      | <a href="#">profile option values</a>                 | -       |
| 11        | **Flexfields setup**                  | afffload.lct       |
| 11.1      | <a href="#">Value sets</a>                            | -       |
| 11.2      | <a href="#">Descriptive flexfields</a>                | -       |
| 11.3      | <a href="#">Key flexfields</a>                        | -       |
| 12        | **Security Information**              | afsload.lct       |
| 12.1      | <a href="#">Menu</a>                                  | -|
| 12.2      | <a href="#">Function</a>                              | -|
| 12.3      | <a href="#">Form</a>                                 | -|
| 12.4      | <a href="#">Entry</a>                                | -|
| 13        | **XDO Files**                         | -|
| 13.1      | <a href="#">Data Definitions</a>                      | -|
| 13.2      | <a href="#">XML Template</a>                          | -|
| 14        | **AME**                         | -|
| 14.1      | <a href="#">Transaction Types</a>                      | -|
| 14.2      | <a href="#">Attributes</a> | -|
| 14.2.1    | <a href="#">Attribute Definitions</a> | -|
| 14.2.2    | <a href="#">Attribute Usages</a> | -|
| 14.3      | <a href="#">Conditions</a> | -|
| 14.4      | <a href="#">Approver Groups</a> | -|
| 14.4.1      | <a href="#">Definitions</a> | -|
| 14.4.2      | <a href="#">Approval Group Config</a> | -|
| 14.5      | <a href="#">Rules</a> | -|
| 14.5.1      | <a href="#">Rule Definitions</a> | -|
| 14.5.2    | <a href="#">Rule Usages</a> | -|
| 15        | **General**                           | -|
| 15.1      | <a href="#">Workflow</a>                              | -|


<br>

## Naming Conventions

<br>

## Contributors

| Author | GitHub & LinkedIn account |
| :-  | :---- |
| Ahmed El-Demasy (Original Author) | <a href="https://github.com/demasy">Github</a> & <a href="https://www.linkedin.com/in/demasy">LinkedIn</a> |
<br>

 ### Contributing to the Oracle FNDLOAD scripts
We welcome you to join and contribute to the Oracle FNDLOAD Scripts. If you are interested in helping please don’t hesitate to contact on an e-mail: founder@egyptianprogrammers.com

<br>

###### Suggestions & Issues
> If you find any issue or have a great idea in mind please create an issue on <a href="https://github.com/demasy/Oracle-FNDLOAD-Scripts/issues">GitHub</a>.
