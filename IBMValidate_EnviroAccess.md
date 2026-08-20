# Initial findings and notes to Project Manager and Developer 2
Project Manager()

# IBM TechZone/Sandbox login test
Introduction: Although IBM TechZone/Sandbox was successfully verified, it took a while to successfully confirm whether IBM cloud access was conducted successfully due to a discrepency with MacOS terminal and watsonx.ai website project catalog. When the terminal was identified to be the best way to access said model catalog, TechZone/Sandbox were able to be conducted through the terminal with little problems.

Initial login test to the given project in watsonx.ai yielded surprising results. Upon creation and login of developer's email(s4090276@student.rmit.edu.au), the expected project wasn't found in projects list, dispite being added via stakeholder Naresh; although through running **command:**
``` curl -s \
"https://us-south.ml.cloud.ibm.com/ml/v1/foundation_model_specs?version=2024-05-01" \
-H "Authorization: Bearer [generated token access]" \
| jq -r '.resources[].model_id'
```
**Screenshot:**
![ModelAccess](Image_Evidence/ModelAccess.png)

The project and following model catalogs are accessible by this user:

The most surprising aspect upon testing login validation in MacOS terminal was when running **command:**
'''
ibmcloud login
'''
**Screenshot:**
![LiginTest](Image_Evidence/Login_Problem1.png)

That the password validation failed although this developer has checked multiple times that the inputted password is correct, therefore was forced to attempt login with a one time access token running which was successful; **command:**
'''
ibmcloud login --sso
'''
**Screenshot:**
![LoginTest2](Image_Evidence/Login_Validation.png)

Sandbox was then confirmed accessible with **command:**
```

```
**Screenshot:**

# Available project list identified:
Introduction: Project list was done without much issue, and is actually viewable in the IBM cloud website. All models provided by Naresh(IBM) was available for further analysis and review.

In the terminal it's viewable when logged in with **command:**
```
ibmcloud resource service-instances
```
**Screenshot:**
![ModelAccess](Image_Evidence/ModelAccess.png)

# IBM Code Engine availability check
Introduction: IBM code engine availability wasn't available within the project's plugin list and was completely empty. It required running pluigin installations to install IBM code engine to the project, however upon installation, plugin is now available.

In the terminal, I've checked initial availability via **command:**
```
ibmcloud plugin list
ibmcloud resource service-instances
```
**Screenshot:**
![InitialCheckIBMCE](Image_Evidence/InitialIBMCodeEngineCheck.png)

Installed IBM Code Engine via **command:**
```
ibmcloud plugin repo-plugins
ibmcloud plugin install code-engine
```
**Screenshot:**
![InstallIBMCE](Image_Evidence/IBMCodeEngineInstall.png)

Final check for IBM Code Engine is viewing its listed available Projects(Since IBM Code Engine has just been installed, expected result is an empty list with no errors); **command:**
```
ibmcloud ce project list
ibmcloud target -g ce 
ibmcloud plugin list
```
**Screenshot:**
![InitialCheckIBMCE](Image_Evidence/IBMCodeEngineInstallVerification.png)

# Relevant storage services identified
Introduction:

# Relevant database options identified
Introduction:

# Missing access/blockers documentation
Introduction:

Blocker:
University watsonx.ai project does not appear in the web UI's
Projects list despite successful API access using the supplied
Project ID.

Impact:
No impact on programmatic model access. Foundation model discovery
and inference have been successfully tested through the watsonx.ai
API.

Status:
Web UI project visibility unresolved.

