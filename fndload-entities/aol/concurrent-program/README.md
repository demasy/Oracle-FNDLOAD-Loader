# Concurrent Program

### Program

| Entity      | Sub-entities, if any |  #   | Download Parameters   |
| :----       | :--------            | :--: | :----   |
| PROGRAM     | INCOMPATIBILITY      | 1    |CONCURRENT_PROGRAM_NAME    |
|             |                      | 2    | APPLICATION_SHORT_NAME    |

### Executable

| Entity      | Sub-entities, if any |  #   | Download Parameters   |
| :----       | :--------            | :--: | :----   |
| EXECUTABLE  |          -           | 1    |EXECUTABLE_NAME    |


<br>

### Example: Program

###### Download 

```
FNDLOAD apps/<$APPS_PWD> O Y DOWNLOAD $FND_TOP/patch/115/import/afcpprog.lct prog_XXDL_CONCURRENT_PROGRAM.ldt PROGRAM APPLICATION_SHORT_NAME="XXDL" CONCURRENT_PROGRAM_NAME="XXDL_CONCURRENT_PROGRAM"
```

###### Upload

```
FNDLOAD apps/<$APPS_PWD> 0 Y UPLOAD $FND_TOP/patch/115/import/afcpprog.lct prog_XXDL_CONCURRENT_PROGRAM.ldt - WARNING=YES UPLOAD_MODE=REPLACE CUSTOM_MODE=FORCE
```

<br>
  
### Example: Executable

###### Download 

```
FNDLOAD apps/<$apps_password> 0 Y DOWNLOAD $FND_TOP/patch/115/import/afcpprog.lct exe_XXDL_EXECUTABLE_NAME_us.ldt EXECUTABLE EXECUTABLE_NAME="XXDL_EXECUTABLE_NAME" APPLICATION_SHORT_NAME="XXDL"
```

###### Upload

```
FNDLOAD apps/<$apps_password> 0 Y UPLOAD $FND_TOP/patch/115/import/afcpprog.lct exe_XXDL_EXECUTABLE_NAME_us.ldt
```

<br>
