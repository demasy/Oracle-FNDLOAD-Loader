# Request Groups

<br>

| Entity      | Sub-entities, if any |  #   | Download Parameters   |
| :----       | :--------            | :--: | :----   |
| REQUEST_GROUP  |          REQUEST_GROUP_ UNIT           | 1    |REQUEST_GROUP_UNIT    |
|   |                    | 2    |REQUEST_GROUP_NAME    |

### Example

###### Download 

```
apps/<$APPS_PWD> O Y DOWNLOAD $FND_TOP/patch/115/import/afcpreqg.lct reqg_XXDL_REPORT_GROUP.ldt REQUEST_GROUP REQUEST_GROUP_NAME="XXDL_REPORT_GROUP" APPLICATION_SHORT_NAME="XXDL"
```

###### Upload

```
FNDLOAD apps/<$APPS_PWD> O Y UPLOAD $FND_TOP/patch/115/import/afcpreqg.lct reqg_XXDL_REPORT_GROUP.ldt
```

<br>
