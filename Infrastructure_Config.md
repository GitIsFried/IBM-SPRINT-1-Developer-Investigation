# Introduction
This document investigates whether the IBM Baseline Infrastructure is properly configured to be immediately usable for use, and make judgement on whether it can be adaptable to the specified infrastructure design as outlined in the document: **Infrastructure_Config.md**. The main parameters on whether an infrastructure component is ready for use is:
- Is the component present? (either in IBM Cloud or IBM catalog)
- Is the component accessible?
- Is the component configured?

The componenets being tested are:
- Cloud Object Storage
- Watsonx Artificial Intelligence (watsonx.ai)
- Watsonx Machine Learning (WML)
- Code Engine Environment
These will be documented under **Component Configuration and Validation**

The document later will also document: 
- Service permissions confirmed? [yes / no]
- Current/new naming and environment conventions? [what / how]
- Credentials are exposed? [safe / exposed]
These will be documented under **Explorations and Suggestions / Remidiations**

The document will also report any blockers to the PM to be resolved and whether it is resolved or not will be documented.

# Component Configuration and Validation
Each component will have a beginning description on what it's being tested and a summary of the outcome, then followed by a more detailed documentation with screenshot evidence, and any relevant steps on how the validation of the component is conducted. We'll mainly explore this through IBM Cloud Console website, to do so, follow these steps:
| Log into IBM Cloud Console > |  Click **☰** in the left-side menu bar > | Click **Resource List** under **Projects** |
| --- | --- | --- |
| ![Confirm_Login_IBM_Cloud](Image_Evidence_2/IBM_Cloud_Login.png) | ![Click_Menu](Image_Evidence_2/IBM_Cloud_NavMenu.png) | ![Click_ResourceList](Image_Evidence_2/IBM_Cloud_ProjectList.png) |

## Cloud Object Storage
### Summary
Upon first investigation in IBM Cloud Catalog, we can see that IBM Cloud Object Storage is already present within the system and that the component is easily accessible, however it isn't configured yet for different storage categories, ie. Standard and Archive Teir.
### Documentation
#### Is the component present? 
| Look for anything named **Cloud Storage** that verifies the environment |
| --- |
| ![Verify_Cloud_Storage](Image_Evidence_2/Cloud_Object_Verification.png) |

#### Is the component accessible?
| Click on **Cloud Object Storage-pv** > | In **Buckets** menu console, click on **ibm-rcs-team2-storage** > | Click Upload > | Upload random file | Confirm upload |
| --- | --- | --- | --- | --- |
| ![Click_Object_Storage](Image_Evidence_2/Click_Object_Storage.png) | ![Click_Bucket](Image_Evidence_2/Click_Storage_Bucket.png) | ![Click_Upload](Image_Evidence_2/Upload_Button1.png) | ![Upload_Random_Object](Image_Evidence_2/Upload_Object_Random.png) | ![Verify_Upload](Image_Evidence_2/Object_Lists.png) |

#### Is the component configured?
Check the following statistics
| Overview | Object lifecycle | Data management |
| --- | --- | --- |
| ![Object_Overview](Image_Evidence_2/Object_Overview.png) | ![Object_Lifecycle](Image_Evidence_2/Object_Lifecycle.png) | ![Object_Data_Management](Image_Evidence_2/Object_DataManagement.png) |
|  Observability | Permissions | Backup policies | 
| --- | --- | --- |
| ![Object_Observability](Image_Evidence_2/Object_Observability.png) | ![Object_Permissions](Image_Evidence_2/Object_Perms.png) | ![Object_Backup_Policies](Image_Evidence_2/Object_Policies.png) |

## Watsonx.ai
### Summary
Upon first inspection, there seems to be plugins relating to the ai, however upon further investigations, they seem to contain only basic management systems and a price sheet.
### Documentation
#### Is the component present? 
| Search up **ai** in the Resource List search function, everything watsonx.ai relevant should appear |
| --- |
| ![Confirm_Validate_Watsonx](Image_Evidence_2/Watsonx_Validation.png) |

#### Is the component accessible?
| Click on **watson.ai Runtime-xe** > | Check Manage Page > | Check Plan Page |
| --- | --- | --- |
| ![Runtime_Click](Image_Evidence_2/Watsonx_JP.png) | ![Runtime_Manage](Image_Evidence_2/Runtime_Manage.png) | ![Runtime_Plan](Image_Evidence_2/Runtime_Plan.png) |

| Click on **watson.ai Studio-jp** > | Check Manage Page > | Check Plan Page |
| --- | --- | --- |
| ![jp_Click](Image_Evidence_2/Watsonx_Runtime.png) | ![jp_Manage](Image_Evidence_2/JP_Manage.png) | ![jp_Plan](Image_Evidence_2/JP_Plan.png) |

| Click on **watson.ai Studio.ud** > | Check Manage Page > | Check Plan Page |
| --- | --- | --- |
| ![ud_Click](Image_Evidence_2/Watsonx_UD.png) | ![ud_Manage](Image_Evidence_2/UD_Manage.png) | ![ud_Plan](Image_Evidence_2/UD_Plan.png) |

#### Is the component configured?
The component is not configured at all, a lot of work is needed to get the AI up to specs.

## Watsonx Machine Learning
### Summary
Upon first inspection, there seems to be a plugin relating to the machine learning, however upon further investigations and like the ai, they seem to contain only basic management systems and a price sheet.
### Documentation

#### Is the component present? 
| Search up **wml** in the Resource List search function, everything WML related should appear |
| --- |
| ![Confirm_Validate_WML](Image_Evidence_2/WML_Validation.png) |

#### Is the component accessible?
| Click on **watson.ai Studio.ud** > | Check Manage Page > | Check Plan Page |
| --- | --- | --- |
| ![wml_Click](Image_Evidence_2/WML_Click.png) | ![wml_Manage](Image_Evidence_2/WML_Manage.png) | ![wml_Plan](Image_Evidence_2/WML_Plan.png) |

#### Is the component configured?
The component is not configured at all, a lot of work is needed to get the WML up to specifications.

## Code Engine
### Summary
When checking for the Code Engine Environment, instead of checking resource catalog, we should check **Containers**
### Documentation
#### Is the component present? 
| Click **Containers** > | **Serverless Projects** > | Look for anything named **Code Engine** that verifies the environment |
| --- | --- | --- |
| ![Navigate_Containers](Image_Evidence_2/Containers_Path.png) | ![Serverless_Projects](Image_Evidence_2/Serverless_Button.png) | ![Verify_Code_Engine](Image_Evidence_2/Code_Engine_Validation.png) |

#### Is the component accessible?
| Click on **ce-itz-wxo-6a7a76ec3dae69a2d9ca20** > | Check Overview > | Check Application |
| --- | --- | --- |
| ![ce_Click]() | ![ce_Overview]() | ![ce_Application]() |

| Check Functions > | Check Jobs > | Check Fleets |
| --- | --- | --- |
| ![ce_Functions]() | ![ce_Jobs]() | ![ce_Fleets]() |

| Check Event subscription > | Check Service bindings > | Check Image builds |
| --- | --- | --- |
| ![ce_EventSubs]() | ![ce_ServiceBinds]() | ![ce_ImageBuilds]() |

| Check Domain mappings > | Check Persistent data stores > | Check Secrets and configmaps |
| --- | --- | --- |
| ![ce_DomainMaps]() | ![ce_PersistentData]() | ![ce_SecretsNConfigsMaps]() |

| Open **Project settings** menu > | Check Intergrations | Check Connectivity
| --- | --- | --- |
| ![ce_PS]() | ![ce_Integration]() | ![ce_Connectivity]() |

| Click on **web application** > | Check Overview > | Check Application |
| --- | --- | --- |
| ![web_Click](Image_Evidence_2/web_Click.png) | ![web_Overview](Image_Evidence_2/web_Overview.png) | ![web_Application](Image_Evidence_2/web_Apps.png) |

| Check Functions > | Check Jobs > | Check Fleets |
| --- | --- | --- |
| ![web_Functions](Image_Evidence_2/web_Func.png) | ![web_Jobs](Image_Evidence_2/web_Jobs.png) | ![web_Fleets](Image_Evidence_2/web_Fleets.png) |

| Check Event subscription > | Check Service bindings > | Check Image builds |
| --- | --- | --- |
| ![web_EventSubs](Image_Evidence_2/web_EventSubs.png) | ![web_ServiceBinds](Image_Evidence_2/web_ServiceBinds.png) | ![web_ImageBuilds](Image_Evidence_2/web_ImgBuilds.png) |

| Check Domain mappings > | Check Persistent data stores > | Check Secrets and configmaps |
| --- | --- | --- |
| ![web_DomainMaps](Image_Evidence_2/web_DomainMaps.png) | ![web_PersistentData](Image_Evidence_2/web_PerDataStorage.png) | ![web_SecretsNConfigsMaps](Image_Evidence_2/webs_Secrets.png) |

| Open **Project settings** menu > | Check Intergrations > | Check Connectivity
| --- | --- | --- |
| ![web_PS](Image_Evidence_2/web_ProjectSettings.png) | ![web_Integration](Image_Evidence_2/web_Integrations.png) | ![web_Connectivity](Image_Evidence_2/web_Connect.png) |

#### Is the component configured?
The component is not configured at all, however it is easy to configurate Code Engine for backend heavy lifting.

# Explorations and Suggestions / Remidiation

## Service Permissions 
All service permissions have been confirmed

### Screenshot Proofs

## Naming and Environment Conventions?
Naming conventions are still the "default" from initial creation. They either contain a "Catalog Name" + "Specific Purpose / Service" or a computer created name such as "wml-itz-wxo-[randon strings of letters and numbers]".

I recommend for easier documentation that all services and catalogs be renamed to this standard:
[Catalog Name] + [Purpose specified in Infrastructure design]

Moreover, many services will be abbreviated as follows:
| Service | Abbreviation(s) |
| --- | --- |
| Cloud Object Storage | Obj_Data |
| Watsonx Artificial Intelligence (watsonx.ai) | Wat_AI |
| Watsonx Machine Learning (WML) | Wat_ML |
| Code Engine | CE |
| EDB Postgres | EDB_Data |

An example being an IBM Code Engine Daemon Catalog that services the backend of the Auditor's console, which means it handles the input from the Auditor's frontend, that means it'll be named: 
**Code Engine Auditor Backend**

## Credentials Exposed?
All credentials are not exposed.

### Screenshot Proofs

## Blocker Reports to Project Manager (Dat Nguyen Minh)
No blockers needed to be reported to PM.

### Screenshot Proofs

## Findings Reports to Developer 2 (Kai Lek Kum)
For works on AI and Text-to-Chat functions I've listed the important Containers / Plugins + what they do + Connections / Relations / Dependencies Mapping with explanation
| Containers / Plugins | What they Do | Connection map | Why Connection? |
| --- | --- | --- | --- |
| --- | --- | --- | --- |

## Code Engine Setup[ Extra ]

### How to create new Code Engine Environment
**NOTE: I didn't know what to do initially and believed that Code Engine wasn't configured, so these are the compiled steps to setup a Code Engine bucket.**
When checking for the Code Engine Environment, the two ways to confirm is in the IBM Cloud Console or IBM Code Engine Console. Upon checking fo
### Documentation
We first check by viewing the IBM Cloud Console, if it exist it should be in Project list:
| Log into IBM Cloud > |  Click **Projects** in the left-side menu bar > | Look for Code Engine |
| --- | --- | --- |
| ![Login_IBM_Cloud](Image_Evidence_2/IBM_Cloud_Login.png) | ![Click_Projects](Image_Evidence_2/IBM_Cloud_ProjectList.png) | ![Validate_Code_Engine](Image_Evidence_2/Cloud_Project_Contents.png) |

Since it doesn't exist, we should setup IBM Code Engine so that we can immediately utilise it for Sprint 2 development. Assuming we're still in the IBM Cloud Console:
| Click **Catalog** button in the menu bar above > |  Search up Code Engine > | Click **Code Engine** > | Click **Start Creating** under Title "Serverless - Code Engine" > |
| --- | --- | --- | --- |
| ![Catalog_Plugins](Image_Evidence_2/IBM_Cloud_Catalog_Button.png) | ![Search_Code_Engine](Image_Evidence_2/Code_Engine_Search.png) | ![Click_Code_Engine](Image_Evidence_2/Code_Engine_Plugin.png) | ![Create_Code_Engine](Image_Evidence_2/Create_Code_Engine_Enviro.png) |

When creating catalog, the necessary options selected are:
| Options | General | Code | Resources & Scaling  | Summary_Details |
| --- | --- | --- | --- | --- | 
| Description | Select The option **Job** for Content type since IBM Code Engine will be used to handle backend function and Job is built to run and execute code. Then name it **backend67** in Name input field since the main task is to validate IBM Code Engine Environemnt | Select **Build container image from source code** and relabel Code repo URL as: **https://github.com/IBM/CodeEngine_backend67** for easier identification  | Since this is just a test case, set Array size to: **1**, CPU and Memory as **1v CPU / 4GB**, and Resilliency setting Mode to **Dameon** so it lasks forever. | Checkout the summary details, it lists the **Job** and **Image build** costs total, since this is a test, the overall cost is virtually free |
| Screenshot | ![General_Option_Config](Image_Evidence_2/General_opt.png) | ![Code_Option_Config](Image_Evidence_2/Code_opt.png) | ![R&S_Option_Config](Image_Evidence_2/R&S_opt.png) | ![Summary_Config](Image_Evidence_2/Summary_Specs.png) |

Again, since we're only validating Code Engine environment, optional values such as Environment variables, Volume mounts, Image start options and Service access will be left untouched. Only when we're creating specific Code Engine Dameon Backends such as the backend for Auditors console or intergrating watsonx.ai API that these options chosen. Although out of scope of the task, I find it necessary to at least research what these options do, which are listed below:

| Option | Description |
| --- | --- |
| Environment variables | |
| Volume mounts | |
| Image start options | |
| Service access | |

To confirm whether IBM COde Engine Environment is setup, we should check IBM Cloud Console Project's list, here we can now see that the environment exist now.
| Log into IBM Cloud > |  Click **Projects** in the left-side menu bar > | Look for Code Engine |
| --- | --- | --- |
| ![Confirm_Login_IBM_Cloud](Image_Evidence_2/IBM_Cloud_Login.png) | ![Confirm_Click_Projects](Image_Evidence_2/IBM_Cloud_ProjectList.png) | ![Confirm_Validate_Code_Engine](Image_Evidence_2/Cloud_Project_Contents.png) |

# Sources
- [1] “Cloud database solutions | IBM,” Ibm.com, 2025. [https://cloud.ibm.com/docs/codeengine?topic=codeengine-getting-started&locale=en ](https://cloud.ibm.com/docs/codeengine?topic=codeengine-getting-started&locale=en ) (accessed 03/09/2026)
- [2]https://cloud.ibm.com/docs/codeengine?topic=codeengine-job-plan
- [3]https://cloud.ibm.com/docs/codeengine?topic=codeengine-plan-build