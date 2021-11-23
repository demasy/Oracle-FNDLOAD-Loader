# Oracle FNDLOAD Scripts

The Generic Loader (FNDLOAD) is a concurrent program that can move Oracle E-Business Suite data between database and text file representations. The loader reads a configuration file to determine what data to access. For information on specific configuration files consult the Open Interfaces Guide for your product group. The following sections describe the operation of the Generic Loader.

<br>

## FNDLOAD Syntax 

The Generic Loader is a concurrent program named FNDLOAD. The concurrent executable takes the following parameters:

> **FNDLOAD apps/{APPS_PASSWORD} 0 Y  {mode} {configfile} {datafile} {entity} [optional {param} {param}]**

<br>

###### Additional Resources
> <a href="https://docs.oracle.com/cd/E18727_01/doc.121/e12893/T174296T206863.htm">Oracle® E-Business Suite System Administrator's Guide - Configuration</a>

<br>

###### Suggestions & Issues
> If you find any issue or have a great idea in mind please create an issue on <a href="https://github.com/demasy/Oracle-FNDLOAD-Scripts/issues">GitHub</a>.
