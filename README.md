# Oracle FNDLOAD Scripts

The Generic Loader (FNDLOAD) is a concurrent program that can move Oracle E-Business Suite data between database and text file representations. The loader reads a configuration file to determine what data to access. For information on specific configuration files consult the Open Interfaces Guide for your product group. The following sections describe the operation of the Generic Loader.

<br>

## FNDLOAD Syntax 

The Generic Loader is a concurrent program named FNDLOAD. The concurrent executable takes the following parameters:

> **FNDLOAD apps/{APPS_PASSWORD} 0 Y  {mode} {configfile} {datafile} {entity} [optional {param} {param}]**

<br>

| Code      | Variable                   | Description                   |
| :-:       | :--------                  | :--------------------------   |
| 1         | apps/{APPS_PASSWORD}       | The APPS schema and password       |
| 2         | < 0 Y >                    | Concurrent program flags       |
| 3         | {mode}                     | **UPLOAD** or **DOWNLOAD** <br> UPLOAD causes the datafile to be uploaded to the database. <br> DOWNLOAD causes the loader to fetch rows and write them to the datafile.|
| 4         | {configfile}               | -       |
| 5         | {datafile}                 | -       |
| 6         | {entity}                   | -       |
| 7         | [optional {param} {param}] | -       |

<br>

## **FNDLOAD Entities**

<br>

| Code      | Entity Name                           | Notes   |
| :-:       | :--------                             | :--------------------------   |
| 1         | **Oracle Application Object Library** | -       |
| 1         | Concurrent program definitions        | -       |
| 2         | Request groups                        | -       |
| 3         | Lookup types and lookup values        | -       |
| 4         | Flexfields setup data                 | -       |
| 5         | Attachments definitions               | -       |
| 6         | Messages                              | -       |
| 7         | Security information                  | -       |

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
