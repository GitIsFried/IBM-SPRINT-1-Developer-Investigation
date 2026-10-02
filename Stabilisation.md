# Introduction
This documentation will cover five topics. Errors encountered(fixed / documented), MVP implementation for cases, auditor case retrieval, and final human decision persistence errors encountered in wee 2 E2E, and testing IBM services, mainly COS runtime, deployment and limitations, and AI results(integrating Dev2's watsonx.ai and STT work into this project) 

# Week 2 E2E Errors Reproduced, Fixed or Documented
| Error[Document, fixed, broken] | Steps to reproduce, cause | Fixed / Documented |
| --- | --- | --- |
| Submission page crash[Document] | Just enter the page | ![How?](Stab_images/Case_Page_Crash.png) |
| Submission page crash[fix] | Removed '!' in backend/IBM_src/case.js function createCase(), file.mimetype.includes(allowed_Format_Video) reading valid file type as negatifalseve | ![Invalid_file_fix](Stab_images/Case_Sub_!debacle.png) |
| Valid submission read as invalid [fix] | Submitting mp4 doesn't work | ![False_Invalid](Stab_images/Invalid_File_Err.png) |
| Duplicate submissions[Documented] | Just submit the same thing twice | ![Submit_Duplication](Stab_images/Case_Duplication.png) |

# Submission -> Case Creation, Case Persistence and Retrieval Verified
Verified and confirmed with application + IBM COS console
- Submission proof
![Case_Submission_Application](Stab_images/Case_ID_Show.png)
- Case creation proof(Check IBM COS Console)
![Case_Submission_Proof](Stab_images/Case_Creation_Val.png)
- Case persistence proof
**Json**
![Json_overview](Stab_images/Case_OW1.png)
![Json_overview_Persistence](Stab_images/Case_OW1_Per.png)
**Video**
![Video_overview](Stab_images/Case_OW2.png)
![Video_overview_Persistence](Stab_images/Case_OW2_Per.png)
- Retrieval verified in Auditor Console
![Retrieve_Verified](Stab_images/Retrieve_Proof.png)

# Auditor UI Receives Correct Case Result
Auditor can receive cases in IBM COS, but cannot get specific cases, assigned to them from the manager, since Manager workflow MVP isn't implemented yet
![Json_Proof](Stab_images/Get_Info_Proof.png)
![Video_proof](Stab_images/Cannot_Get_Vid.png)

# IBM COS / Runtime / Deployment Path Verified or Limitations Recorded
- **NOTE:** Not all MVP features were fully developed when testing this, especially auditor editing and final human decision persistence, and following UX elements
- Testing with: http://localhost:8080/api/storage-test, we can see that IBM COS Runtime and deployment path is verified, as well as with the above case submission proving that IBM COS servicc implementation is working as expected. However, a possible limitation is that case retrieval cannot pull videos and display it(however that feature hasn't been worked on yet).
![IBM_COS](Stab_images/IBM_COS_PROOF.png)

# Final Human Decision Persistence Verified
- Need to create menu items regarding timestamps, showing AI transcript
- Need to intergrate AI transcript in there
- 67
- Not done yet

# Dev2 AI Result Retrieval 
- Haven't verified yet

# Synthetic E2E Run Completed and Evidence Captured
- I'm confused what this means

# Plan
- Test on actual code engine
