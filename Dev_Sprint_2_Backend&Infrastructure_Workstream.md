# Week 1 backend objective defined

## Wednesday, get all containers up and running:
- Get Code Engine online
- Get Object Cloud online
- Get EDB PostgresSQL online
- Get VPC online
- Get VPS online

## Friday connect all containers with code engine:
- Code Code Engine backend API to connect everything together

## Saturday get VPC / VPS to work:
- Get VPC and VPS to work
- Code in a basic page to prototype frontend

# Code Engine work identified
Need to be able to access and create code engine containers for one specific API task. Code Engines to create are:
- **Code Engine Backend API Master:** This code engine container will connect all of the IBM Software Architecture together; **Language:** C++ 
- **Code Engine AI API:** Runs all logic for watsonx.ai and outputs Json strings **Language:** Python
- **Code Engine STT API:** Runs all logic for Speech-To-Text and outputs transcript as a Json string **Language:** Python
- **Code Engine Database API:** Runs all database related logic, including running queries, organising storage of data, separating case content, storing Json into EDB PostgresSQL, storing media into Object Storage **Language:** C++
- **Code Engine Frontend API:** Runs logic for VPC and VPS, including tracking user usage / demands, region tracking, creating / destroying VPS instances, displaying UX designed interfaces, communicating user inputs to Backend API. **Languages**: JavaScript, .js, 

# Storage Work Identified
- Configuring Storage

# Database Work Identified
- Configuring Object Storage to include the following: {caseID: , original_video:, original_audio, processed_video: , processed_audio}
- Configuring EDB PostgresSQL, including following Json format specified by Dev2

# Service / Integration Dependencies Identified

# Week 1 Task Inputs Specific

# Week 2 High-Level Work Proposed

# Week 3 High-Level work Proposed

# Implementation Risks noted

# Notes to PM / BA