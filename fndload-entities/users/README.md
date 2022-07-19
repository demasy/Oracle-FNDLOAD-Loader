# User



<br>

## Find Entity: SQL Statement

```
SELECT FU.USER_NAME USER_NAME
  FROM FND_USER FU
 WHERE 1 = 1 AND FU.USER_NAME = 'DEMASY'
```

## FNDLOAD Command

Example:

> FND_USER: **DEMASY**

###### Download
```
FNDLOAD apps/<$APPS_PWD> 0 Y DOWNLOAD $FND_TOP/patch/115/import/afscursp.lct u_DEMASY.ldt FND_USER USER_NAME='DEMASY'
```

###### Upload
```
FNDLOAD apps/<$APPS_PWD> 0 Y UPLOAD $FND_TOP/patch/115/import/afscursp.lct u_DEMASY.ldt
```
