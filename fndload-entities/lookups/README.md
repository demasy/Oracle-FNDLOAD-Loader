# Lookups

<br>

| Entity           | Sub-entities, if any |  #   | Download Parameters   |
| :----            | :--------            | :--: | :----   |
| FND_LOOKUP_TYPE  |         FND_LOOKUP_VALUE           | 1    | 	VIEW_APPSNAME LOOKUP_TYPE    |
|                  |                                    | 2    |SECURITY_GROUP    |

<br>

### Example


###### Download 

```
FNDLOAD apps/<$APPS_PWD> O Y DOWNLOAD $FND_TOP/patch/115/import/aflvmlu.lct lu_XXDL_LOOKUP_TYPE.ldt FND_LOOKUP_TYPE APPLICATION_SHORT_NAME="XXDL" LOOKUP_TYPE="XXDL_LOOKUP_TYPE"
```

###### Upload

```
FNDLOAD apps/<$APPS_PWD> O Y UPLOAD $FND_TOP/patch/115/import/aflvmlu.lct lu_XXDL_LOOKUP_TYPE.ldt UPLOAD_MODE=REPLACE CUSTOM_MODE=FORCE
```

<br>
