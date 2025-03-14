# Configuration Files

<br>

## Concurrent Program Entities
| Code   | Entity Name                      | Entity Code      | Configuration File   | Table Name |
| :-:     | :--------                       | :----            | :----   | :----   |
| 1    | Concurrent Programs                | PROGRAM          | $FND_TOP/patch/115/import/afcpprog.lct | FND_CONCURRENT_PROGRAMS  |
| 2    | Executables                        | EXECUTABLE       | $FND_TOP/patch/115/import/afcpprog.lct | FND_EXECUTABLES  |
| 3    | Request Groups                     | REQUEST_GROUP    | $FND_TOP/patch/115/import/afcpreqg.lct | FND_REQUEST_GROUPS  |
| 4    | Request Sets                       | REQUEST_SET      | $FND_TOP/patch/115/import/afcpreqs.lct | FND_REQUEST_SETS  |
| 5    | Request Set Links                  | REQUEST_SET_LINK | $FND_TOP/patch/115/import/afcpreqs.lct | FND_REQUEST_SET_LINKS  |

<br>

## Application Object Library (AOL) Entities

### Lookups
| Code   | Entity Name      | Entity Code      | Configuration File                    | Table Name |
| :-:    | :--------        | :----            | :----                                 | :----   |
| 1      | Lookups          | LOOKUP_TYPE      | $FND_TOP/patch/115/import/aflvmlu.lct | FND_LOOKUP_TYPES  |
| 2      | Lookup Values    | LOOKUP_VALUE     | $FND_TOP/patch/115/import/aflvmlu.lct | FND_LOOKUP_VALUES  |

<br>

### Profile Options
| Code   | Entity Name              | Entity Code          | Configuration File                     | Table Name |
| :-:    | :--------                | :----                | :----                                  | :----   |
| 1      | Profile Options          | PROFILE_OPTION       | $FND_TOP/patch/115/import/afscprof.lct | FND_PROFILE_OPTIONS  |
| 2      | Profile Option Values    | PROFILE_OPTION_VALUE | $FND_TOP/patch/115/import/afscprof.lct | FND_PROFILE_OPTION_VALUES  |

<br>

### Flexfields
| Code   | Entity Name               | Entity Code            | Configuration File                     | Table Name |
| :-:    | :--------                 | :----                  | :----                                  | :----   |
| 1      | Key Flexfield Structures  | KEY_FLEXFIELD          | $FND_TOP/patch/115/import/afffload.lct | FND_ID_FLEX_STRUCTURES  |
| 2      | Descriptive Flexfields    | DESCRIPTIVE_FLEXFIELD  | $FND_TOP/patch/115/import/afffload.lct | FND_DESCRIPTIVE_FLEXS  |
| 3      | Value Sets                | VALUE_SET              | $FND_TOP/patch/115/import/afffload.lct | FND_FLEX_VALUE_SETS  |

<br>

### Messages Dictionary
| Code   | Entity Name           | Entity Code   | Configuration File                     | Table Name |
| :-:    | :--------             | :----         | :----                                  | :----   |
| 1      | Messages Dictionary   | MESSAGE       | $FND_TOP/patch/115/import/afmsg.lct    | FND_NEW_MESSAGES  |

<br>

### Attachments
| Code   | Entity Name           | Entity Code   | Configuration File                     | Table Name |
| :-:    | :--------             | :----         | :----                                  | :----   |
| 1      | Attachments Setup     | ATTACHMENT    | $FND_TOP/patch/115/import/afftalrt.lct | FND_DOCUMENTS  |

<br>


## Security & Access Control Entities
| Code   | Entity Name     | Entity Code    | Configuration File                     | Table Name |
| :-:     | :--------      | :----          | :----                                  | :----   |
| 1    | Users             | USER           | $FND_TOP/patch/115/import/afscusr.lct  | FND_USER  |
| 2    | Responsibilities  | RESPONSIBILITY | $FND_TOP/patch/115/import/afscursp.lct | FND_RESPONSIBILITY  |
| 3    | Menus             | MENU           | $FND_TOP/patch/115/import/afsload.lct  | FND_MENUS  |
| 4    | Menu Entries      | MENU_ENTRY     | $FND_TOP/patch/115/import/afsload.lct  | FND_MENU_ENTRIES  |
| 5    | Functions         | FUNCTION       | $FND_TOP/patch/115/import/afscursp.lct | FND_FORM_FUNCTIONS  |
| 6    | Forms             | FORM           | $FND_TOP/patch/115/import/afsecurr.lct | FND_FORM  |
| 7    | Entry             | ENTRY          | $FND_TOP/patch/115/import/afsecurr.lct | FND_FORM_FUNCTIONS  |

<br>

## Workflow & Approval Management Entities

### Workflow
| Code   | Entity Name  | Entity Code   | Configuration File               | Table Name |
| :-:    | :--------    | :----         | :----                            | :----   |
| 1      | Workflow     | WFLOAD        | $FND_TOP/patch/115/import/wf.lct | WF_ITEMS  |

<br>

### Approvals Management Engine (AME)

#### Transaction Types
| Code | Entity Name       | Entity Code          | Configuration File                | Table Name |
| :-:  | :--------         | :----                | :----                             | :----   |
| 1    | Transaction Types | AME_TRANSACTION_TYPE | $AME_TOP/patch/115/import/ame.lct | AME_TRANSACTION_TYPES  |

#### Attributes
| Code | Entity Name           | Entity Code         | Configuration File                | Table Name |
| :-:  | :--------             | :----               | :----                             | :----   |
| 1    | Attributes            | AME_ATTRIBUTE       | $AME_TOP/patch/115/import/ame.lct | AME_ATTRIBUTES  |
| 1    | Attribute Definitions | AME_ATTRIBUTE_DEF   | $AME_TOP/patch/115/import/ame.lct | AME_ATTRIBUTE_DEFINITIONS  |
| 1    | Attribute Usages      | AME_ATTRIBUTE_USAGE | $AME_TOP/patch/115/import/ame.lct | AME_ATTRIBUTE_USAGES  |

#### Conditions
| Code | Entity Name  | Entity Code   | Configuration File                | Table Name |
| :-:  | :--------    | :----         | :----                             | :----   |
| 1    | Conditions   | AME_CONDITION | $AME_TOP/patch/115/import/ame.lct | AME_CONDITIONS  |


<br>


## Reporting & BI Publisher (XDO) Entities

| Code   | Entity Name                      | Entity Code      | Configuration File   | Table Name |
| :-:     | :--------                       | :----            | :----   | :----   |

<br>

## SOA, Integrations & Web ADI Entities

| Code   | Entity Name                      | Entity Code      | Configuration File   | Table Name |
| :-:     | :--------                       | :----            | :----   | :----   |

<br>

## Alerts Entity

| Code   | Entity Name                      | Entity Code      | Configuration File   | Table Name |
| :-:     | :--------                       | :----            | :----   | :----   |

<br>

## Forms Personalization Entities

| Code   | Entity Name                      | Entity Code      | Configuration File   | Table Name |
| :-:     | :--------                       | :----            | :----   | :----   |

<br>

### AOL
| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 1.1    | <a href="#">Concurrent Programs</a>                  | $FND_TOP/patch/115/import/**afcpprog**.lct|
| 1.2    | <a href="#">Request Groups</a>                  | $FND_TOP/patch/115/import/**afcpreqg**.lct|
| 1.3    | <a href="#">Lookup: Lookup Types</a>                  | $FND_TOP/patch/115/import/**aflvmlu**.lct|
| 1.4    | <a href="#">Lookup: Lookup Values</a>                  | $FND_TOP/patch/115/import/**aflvmlu**.lct|
| 1.5    | <a href="#">Profile Option: Definition</a>                  | $FND_TOP/patch/115/import/**afscprof**.lct|
| 1.6    | <a href="#">Profile Option: Values</a>                  | $FND_TOP/patch/115/import/**afscprof**.lct|
| 1.7    | <a href="#">Flexfield: Key flexfields</a>                  | $FND_TOP/patch/115/import/**afffload**.lct|
| 1.8    | <a href="#">Flexfield: Descriptive flexfields</a>                  | $FND_TOP/patch/115/import/**afffload**.lct |
| 1.9    | <a href="#">Flexfield: Value sets</a>                  | $FND_TOP/patch/115/import/**afffload**.lct|
| 1.10   | <a href="#">Attachments</a>                  | $FND_TOP/patch/115/import/**afattach**.lct|
| 1.11   | <a href="#">Messages</a>                  | $FND_TOP/patch/115/import/**afmdmsg**.lct|
| 1.12   | <a href="#">Security: Menu</a>                  | $FND_TOP/patch/115/import/**afsload**.lct|
| 1.13   | <a href="#">Security: Function</a>                  | $FND_TOP/patch/115/import/**afsload**.lct|
| 1.14   | <a href="#">Security: Form</a>                  | $FND_TOP/patch/115/import/**afsload**.lct|
| 1.15   | <a href="#">Security: Entry</a>                  | $FND_TOP/patch/115/import/**afsload**.lct|

<br>

### Alerts

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 2.1    | <a href="#">Alert</a>                 | $ALR_TOP/patch/115/import/**alr**.lct|

<br>


### Approvals Management Engine (AME)

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 3.1    | <a href="#">Transaction Types</a>                 | $AME_TOP/patch/115/import/**amesrulk**.lct|
| 3.2    | <a href="#">Attribute</a>                 | $AME_TOP/patch/115/import/**amesattr**.lct|
| 3.2    | <a href="#">Attribute: Definitions</a>                 | $AME_TOP/patch/115/import/**amesatdf**.lct|
| 3.3    | <a href="#">Attribute: Usages</a>                 | $AME_TOP/patch/115/import/**amesatus**.lct|
| 3.4    | <a href="#">Conditions</a>                 | $AME_TOP/patch/115/import/**amescond**.lct|
| 3.5    | <a href="#">Approver Group</a>                 | $AME_TOP/patch/115/import/**amesagrp**.lct|
| 3.5    | <a href="#">Approver Group: Definitions</a>                 | $AME_TOP/patch/115/import/**amesagdf**.lct|
| 3.6    | <a href="#">Approver Group: Configuration</a>                 | $AME_TOP/patch/115/import/**amesagco**.lct|
| 3.7    | <a href="#">Rule: Definitions</a>                 | $AME_TOP/patch/115/import/**amesrulk**.lct|
| 3.8    | <a href="#">Rule: Usages</a>                 | $AME_TOP/patch/115/import/**amesruus**.lct|

<br>

### Business Intelligence (BI) Publisher (XDO)

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 4.1    | <a href="#">Data Definitions</a>                 | $XDO_TOP/patch/115/import/**xdotmpl**.lct|
| 4.2    | <a href="#">XML Template</a>                 | $XDO_TOP/patch/115/import/**xdotmpl**.lct|

<br>

### Web Applications Desktop Integrator (Web ADI)

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 4.1    | <a href="#">Integrators</a>                 | $BNE_TOP/patch/115/import/**bneintegrator**.lct|

<br>

### Generic

| Code   | Entity Name                           | Configuration File   |
| :-     | :--------                             | :----   |
| 5.1    | <a href="#">Responsibility</a>        | $FND_TOP/patch/115/import/**afscursp**.lct|
| 5.2    | <a href="#">Users</a>                 | $FND_TOP/patch/115/import/**afscuur**.lct|
| 5.3    | <a href="#">Request Set</a>           | $FND_TOP/patch/115/import/**afcprset**.lct|
| 5.4    | <a href="#">Request Set Link</a>      | $FND_TOP/patch/115/import/**afcpreqs**.lct|
| 5.5    | <a href="#">SOA Gateway</a>           | $FND_TOP/patch/115/import/**soa**.lct|

<br>



### WFLOAD

| Code   | Entity Name                           | 
| :-     | :--------                             | 
| 6.1    | <a href="#">Workflow</a>              |
