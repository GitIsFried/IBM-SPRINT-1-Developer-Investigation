# Introduction
This document investigates whether the IBM Baseline Infrastructure is properly configured to be immediately usable for use, and make judgement on whether it can be adaptable to the specified infrastructure design as outlined in the document: **Infrastructure_Config.md**. The main parameters on whether an infrastructure component is ready for use is:
- Is the component present? (either in IBM Cloud or IBM catalog)
- Is the component accessible?
- Is the component configured?

The componenets being tested are:
- Code Engine Environment
- Cloud Object Storage
- EDB Postgres Database
- Watsonx.ai
- WML

The document later will also document: 
- Service permissions confirmed? [yes / no]
- Current/new naming and environment conventions? [what / how]
- Credentials are exposed? [safe / exposed]

The document will also report any blockers to the PM to be resolved and whether it is resolved or not will be documented.

# Component Validation
Each component will have a beginning description on what it's being tested and a summary of the outcome, then followed by a more detailed documentation with screenshot evidence, and any relevant steps on how the validation of the component is conducted.

## Code Engine

### Summary
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

## Cloud Object Storage
### Summary
### Documentation
| Log into IBM Cloud > |  Click **☰** in the left-side menu bar > | Click **Resource List** under **Projects** > | View Resource List Catalog | Look for anything named **Cloud Storage** that verifies the environment |
| --- | --- | --- | --- | --- |
| ![Confirm_Login_IBM_Cloud](Image_Evidence_2/IBM_Cloud_Login.png) | ![Click_Menu](Image_Evidence_2/IBM_Cloud_NavMenu.png) | ![Click_ResourceList](Image_Evidence_2/IBM_Cloud_ProjectList.png) | ![View_ResourceList_Catalig](Image_Evidence_2/IBM_Cloud_ResourceList.png) | ![Verify_Cloud_Storage](Image_Evidence_2/Cloud_Object_Verification.png) |


## EDB Postgres Database
### Summary
### Documentation
| Log into IBM Cloud > |  Click **☰** in the left-side menu bar > | Click **Resource List** under **Projects** > | View Resource List Catalog | Look for anything named **Cloud Storage** that verify's environment |
| --- | --- | --- | --- | --- |
| ![Confirm_Login_IBM_Cloud](Image_Evidence_2/IBM_Cloud_Login.png) | ![Click_Menu](Image_Evidence_2/IBM_Cloud_ProjectList.png) | ![Click_ResourceList](Image_Evidence_2/Cloud_Project_Contents.png) | ![Verify_Cloud_Storage]() |


## Watsonx.ai
### Summary
### Documentation
| Log into IBM Cloud > |  Click **Projects** in the left-side menu bar > | Look for Code Engine |
| --- | --- | --- |
| ![Confirm_Login_IBM_Cloud](Image_Evidence_2/IBM_Cloud_Login.png) | ![Confirm_Click_Projects](Image_Evidence_2/IBM_Cloud_ProjectList.png) | ![Confirm_Validate_Code_Engine](Image_Evidence_2/Cloud_Project_Contents.png) |


## WML
### Summary
### Documentation
| Log into IBM Cloud > |  Click **Projects** in the left-side menu bar > | Look for Code Engine |
| --- | --- | --- |
| ![Confirm_Login_IBM_Cloud](Image_Evidence_2/IBM_Cloud_Login.png) | ![Confirm_Click_Projects](Image_Evidence_2/IBM_Cloud_ProjectList.png) | ![Confirm_Validate_Code_Engine](Image_Evidence_2/Cloud_Project_Contents.png) |


## Service Permissions 

## Naming and Environment Conventions?
### Current
### New

## Credentials Exposed?

## Blocker Reports to Project Manager

# Sources
- [1] “Cloud database solutions | IBM,” Ibm.com, 2025. [https://cloud.ibm.com/docs/codeengine?topic=codeengine-getting-started&locale=en ](https://cloud.ibm.com/docs/codeengine?topic=codeengine-getting-started&locale=en ) (accessed 03/09/2026)
- [2]https://cloud.ibm.com/docs/codeengine?topic=codeengine-job-plan
- [3]https://cloud.ibm.com/docs/codeengine?topic=codeengine-plan-build