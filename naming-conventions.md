# Naming Conventions

##### FNDLOAD File Name
> {prefix_}{Enitiy Name}[{_suffix}]

This is my recommendation for a naming convention for the data file name.

 | SEQ       | Type                   | Name                           | Prefix | Suffix | Example |
 | :-:       | :----------            | :----                          | :---   | :---   | :----   |
 | 1         | Responsibility         | XXDL_RESPONSIBILITY_NAME       | resp_  |   -     | resp_XXDL_RESPONSIBILITY_NAME.ldt |
 | 2         | Menu                   | XXDL_MENU_NAME                 | mu_    |   -     | mu_XXDL_MENU_NAME.ldt |
 | 3         | Function               | XXDL_FUNCTION_NAME             | func_  |   -     | func_XXDL_FUNCTION_NAME.ldt |  
 |           | **Concurrent Program**                                  | -      |  -      |  -      | -|
 | 4         | Program                | XXDL_CONCURRENT_PROGRAM        | prog_  |   -     | prog_XXDL_CONCURRENT_PROGRAM.ldt |
 | 5         | Request Groups         | XXDL_REQUEST_GROUP             | rg_    |   -     | rg_XXDL_REQUEST_GROUP.ldt |
 | 6         | Request Set & Link     | XXDL_REQUEST_SET               | rs_    |   -     | rs_XXDL_REQUEST_SET.ldt | 
 | 7         | Lookups                | XXDL_LOOKUP_TYPE               | lu_    |   -     | lu_XXDL_LOOKUP_TYPE.ldt |
 | 8         | Messages               | XXDL_MESSAGE_NAME              | msg_   |   -     | msg_XXDL_MESSAGE_NAME.ldt |
 |           | **Flexfields Setup**   | -                              | -      |   -     | - |
 | 9         | Value Set              | XXDL_VALUE_SET_NAME            | vs_    |   -     | vs_XXDL_VALUE_SET_NAME.ldt |
 | 10        | Descriptive flexfields | XXDL_DFF_FLEXFIELD_NAME        | df_    |   -     | df_XXDL_DFF_FLEXFIELD_NAME.ldt |
 | 11        | Key flexfields         | XXDL_KFF_FLEXFIELD_NAME        | kf_    |   -     | kf_XXDL_KFF_FLEXFIELD_NAME.ldt |
 | 12        | Profile                | XXDL_PROFILE_NAME              | pf_    |   -     | pf_XXDL_PROFILE_NAME.ldt |
 | 13        | Profile Value          | XXDL_PROFILE_VALUE             | pv_    |   -     | pv_XXDL_PROFILE_VALUE.ldt | 
 | 14        | Alert                  | XXDL_ALERT_NAME                | alr_   |   -     | alr_XXDL_ALERT_NAME.ldt |
 | 15        | Definition & Associated Template | XXDL_DATA_DEFINITION    | ddt_   |   -     | ddt_XXDL_DATA_DEFINITION.ldt | 
 | 16        | Data Template - Data Source XML File | XXDL_DATA_TEMPLATE| dtds_  |   -     | dtds_XXDL_DATA_TEMPLATE.ldt |  
 | 17        | Workflow               | XXDLWF                         | wf_    |   -     | wf_XXDLWF.wft |
 | 18        | Users                  | XXDL_DEMASY_LABS               | u_     |   -     | user_DEMASY_LABS.ldt | 
 
