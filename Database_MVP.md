# Introduction
This documentation showcases how Dev1 has confirmed and implemented database backend including, outlining case schema, persistence and retrieval by Case ID, defining databases based on Dev2 specifications, and defining multiple fields and ensuring Cloud Object Storage data persists indefinitely. Share relevant information about database backend working to Dev2 and PM.


# Database Service / Technology Explicitly Confirmed
Confirm whether:
- Cloud Object Storage exists: 
- EDB PostgreSQL exist

If not create them, then inject testing infomation:
- Cloud Object Storage(Stores original video and audio, AI processed video and audio, and reference to EDB PostgreSQL Json caseID)
- EDB PostgreSQL(Stores Dev2 defined Json structure of case)

Verification Documentation
- Cloud Object Storage: It is present in the console and able to use it in backend documentation. THe Object storred is shown here![Object_Storage](Prototype_Documentation/S2W1_Documentation/database_images/COS_case_storage_b.png)
- EDB PostgreSQL: Not using anymore, everything is on Cloud Object Storage. The cost to use SQL on IBM Cloud is too much 400-500$ range per month.

# Database Connection from Backend Works
Confirm whether specified database API is connected to
- Cloud Object Storage services
- EDB PostgreSQL services
- Code Engine services
- The connection is secure, private and based.

Look in "Basic Input Validation Implemented" in "Backend_MVP.md"

# Case Schema / Data Model Documentation
Confirm whether the database services store the case schema in a data model structure specified by Dev2.

# Case Can be Persisted / Media Bytes Remain in Cloud Object Storage
Validate whether the cases last forever. This is done by checking the persistence variable value. Showcase screenshot as proof that test data persists. In the screenshot in "Database Service / Technology Explicitly Confirmed", said case has existed for more than a day and there hasn't been any specification to not terminate case by a certain date, therefore case can be 

# Case Can be Retrieved by Case ID
Look in "Retrieve-Case Endpoint Implementation" in "Backend_MVP.md"

# Processing-Status Model Implementation
Look in "Create-Case Endpoint Implementation" in "Backend_MVP.md"

# Defining Fields
This table explains how important database fields are being defined within the architecture.
| Field | Defined | 
| --- | --- |
| Media-Reference | {"case_ID": "CASE-XXX", "og_Video": "XXX.[video format]", "og_Audio: "XXX.[Audio format]", "ai_Video": "XXX.[video format]", "ai_Audio": "XXX.[Audio format]"} |
| Transcript | {"transcript": "...", "confidence": 0.92 }  | 
| CaseID, Severity, Summary, Categories, Incident Timestamps | {"caseId": "CASE-001", "severity": "high", "summary": "Short AI-generated summary", "categories": ["violence"], "timestamps": [{"start": 12.4, "end": 18.2, "reason": "Potential harmful content"} ] 
| Auditor Final-Decision Location | A duplicate of the transcript and Json database structure would be created, where the auditor can then edit so that both the AI and the final human decision data is present |

# Database Secrets Not Commited
Ensure database secrets are in the .env files.