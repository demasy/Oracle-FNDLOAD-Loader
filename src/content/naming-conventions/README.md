# Naming Conventions

##### FNDLOAD File Name
> {prefix_}{enitiy-name}[{_suffix}]{_language-code}

<br>

##### How to get the Language Code?
``` SQL
  SELECT FL.NLS_LANGUAGE LANGUAGE, LOWER (FL.LANGUAGE_CODE) LANGUAGE_CODE
    FROM FND_LANGUAGES FL
   WHERE 1 = 1 AND UPPER (FL.INSTALLED_FLAG) IN ('B', 'I')
ORDER BY FL.INSTALLED_FLAG
```

<br>

 
This is my recommendation for a naming convention for the data file name.

## Concurrent Program Entities
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 | 1   | Concurrent Programs  | XXDL_PROGRAM_CODE      | prog_  |   -     | prog_XXDL_PROGRAM_CODE_us.ldt |
 | 2   | Executables          | XXDL_EXECUTABLE_CODE   | exe_   |   -     | exe_XXDL_EXECUTABLE_CODE_us.ldt |
 | 3   | Request Groups       | XXDL_REQ_GROUP_CODE    | reqg_  |   -     | reqg_XXDL_REQ_GROUP_CODE_us.ldt |
 | 4   | Request Sets         | XXDL_REQ_SET_CODE      | reqs_  |   -     | reqs_XXDL_REQ_SET_CODE_us.ldt |
 | 5   | Request Set Links    | XXDL_REQ_SET_LINK_CODE | reqsl_ |   -     | reqsl_XXDL_REQ_SET_LINK_CODE_us.ldt |

<br>

## Application Object Library (AOL) Entities

### Lookups
 | SEQ | Type           | Name              | Prefix | Suffix | Example |
 | :-: | :----------    | :----             | :---   | :---   | :----   |
 | 1   | Lookups        | XXDL_LOOKUP_TYPE  | lu_    |   -    | lu_XXDL_LOOKUP_TYPE_us.ldt |
 | 2   | Lookup Values  | XXDL_LOOKUP_VALUE | luv_   |   -    | luv_XXDL_LOOKUP_VALUE_us.ldt | 

### Profile Options
 | SEQ | Type                  | Name                | Prefix | Suffix | Example |
 | :-: | :----------           | :----               | :---   | :---   | :----   |
 | 1   | Profile Options       | XXDL_PROFILE_OPTION | prof_  |   -    | prof_XXDL_PROFILE_OPTION_us.ldt |
 | 2   | Profile Option Values | XXDL_OPTION_VALUE   | prof_  |   -    | prof_XXDL_OPTION_VALUE_us.ldt |  
 
### Flexfields
 | SEQ | Type                     | Name                    | Prefix | Suffix | Example |
 | :-: | :----------              | :----                   | :---   | :---   | :----   |
 | 1   | Key Flexfield Structures | XXDL_KEY_FLEXFIELD_CODE | kff_   |   -    | kff_XXDL_KEY_FLEXFIELD_CODE_us.ldt |
 | 2   | Descriptive Flexfields   | XXDL_DESCRIPTIVE_CODE   | dff_   |   -    | dff_XXDL_DESCRIPTIVE_CODE_us.ldt |  
 | 3   | Value Sets               | XXDL_VALUE_SET_CODE     | vs_    |   -    | vs_XXDL_VALUE_SET_CODE_us.ldt | 
 
### Messages Dictionary
 | SEQ | Type                | Name               | Prefix | Suffix | Example |
 | :-: | :----------         | :----              | :---   | :---   | :----   |
 | 1   | Messages Dictionary | XXDL_MESSAGE_CODE  | msg_   |   -    | msg_XXDL_MESSAGE_CODE_us.ldt |
 
### Attachments
 | SEQ | Type                 | Name                   | Prefix   | Suffix | Example |
 | :-: | :----------          | :----                  | :---     | :---   | :----   |
 | 1   | Attachments Setup    | XXDL_ATTACHMENT        | attach_  |   -    | attach_XXDL_ATTACHMENT_us.ldt |
 
<br>

## Security & Access Control Entities
 | SEQ | Type                 | Name                     | Prefix | Suffix | Example |
 | :-: | :----------          | :----                    | :---   | :---   | :----   |
 | 1   | Users                | XXDL_USER_NAME           | usr_   |   -    | usr_XXDL_USER_NAME_us.ldt |
 | 2   | Responsibilities     | XXDL_RESPONSIBILITY_CODE | rsp_   |   -    | rsp_XXDL_RESPONSIBILITY_CODE_us.ldt |
 | 3   | Menus                | XXDL_MENU_CODE           | mu_    |   -    | mu_XXDL_MENU_CODE_us.ldt |
 | 4   | Menu Entries         | XXDL_MENU_ENTRY_CODE     | mue_   |   -    | mue_XXDL_MENU_ENTRY_CODE_us.ldt |
 | 5   | Functions            | XXDL_FUNCTION_CODE       | func_  |   -    | func_XXDL_FUNCTION_CODE_us.ldt |
 | 6   | Forms                | XXDL_FORM_CODE           | forms_ |   -    | forms_XXDL_FORM_CODE_us.ldt |
 | 7   | Entry.               | XXDL_ENTRY_CODE          | entry_ |   -    | entry_XXDL_ENTRY_CODE_us.ldt |
 
<br>

## Workflow & Approval Management Entities

### Workflow
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 | 1   | HRSSA                | WFLOAD                 | wf_    |   -    | wf_HRSSA_us.ldt |
 
### Approvals Management Engine (AME)

 #### Transaction Types
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 
 #### Attributes
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 
 #### Conditions
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 
 #### Approver Groups
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 
 #### Rules
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 
 
<br>

## Reporting & BI Publisher (XDO) Entities
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |

<br>

## SOA, Integrations & Web ADI Entities

### Integrated SOA Gateway (ISG)
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 
### Application Desktop Integrator (Web ADI)
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |

<br>

## Alerts Entity
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |
 
<br>

## Forms Personalization Entities
 | SEQ | Type                 | Name                   | Prefix | Suffix | Example |
 | :-: | :----------          | :----                  | :---   | :---   | :----   |

<br>

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
 
