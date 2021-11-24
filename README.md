# Oracle FNDLOAD Scripts

The Generic Loader (FNDLOAD) is a concurrent program that can move Oracle E-Business Suite data between database and text file representations. The loader reads a configuration file to determine what data to access. For information on specific configuration files consult the Open Interfaces Guide for your product group. The following sections describe the operation of the Generic Loader.

<br>

## FNDLOAD Syntax 

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

<br>

| Code      | Entity Name                           | Configuration File   |
| :-:       | :--------                             | :----   |
| -         | **Oracle Application Object Library** | -       |
| 1         | Responsibility                        | afscursp.lct       |
| 2         | Users                                 | -       |
| 3         | Concurrent program definitions        | afcpprog.lct       |
| 4         | Request groups                        | afcpreqg.lct       |
| 5         | **Lookups**                           | aflvmlu.lct       |
| 5.1       | Lookup types                          | -       |
| 5.2       | Lookup values                         | -       |
| 6         | **Profile options**                   | afscprof.lct       |
| 6.1       | Profile option definitions            | -       |
| 6.2       | profile option values                 | -       |
| 7         | **Flexfields setup**                  | afffload.lct       |
| 8.1       | Value sets                            | -       |
| 8.2       | Descriptive flexfields                | -       |
| 8.3       | Key flexfields                        | -       |
| 9         | Attachments definitions               | afattach.lct       |
| 10        | Messages                              | afmdmsg.lct       |
| 11        | **Security Information**              | afsload.lct       |
| 11.1      | Menu                                  | -|
| 11.2      | Function                              | -|
| 11.3      | Form                                  | -|
| 11.4      | Entry                                 | -|
| 12        | **General**                           | -|
| 12.1      | Workflow                              | -|



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
