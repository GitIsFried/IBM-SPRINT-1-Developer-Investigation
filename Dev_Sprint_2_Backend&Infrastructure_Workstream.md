# Week 1 backend objective defined

## Wednesday, get all containers up and running:
- Get Code Engine online
- Get Object Cloud online
- Get EDB PostgresSQL online
- Get VPC online
- Get VPS online
- Create correlating APIs to connect all services together.

## Friday connect all containers with code engine:
- Code Code Engine backend API prototype running
- Code Engine database API prototype running
- Code Engine frontend API prototype running
- Connect frontend API and database API to backend API

## Saturday get VPC / VPS to work:
- Connnect Object Cloud and EDB PostgresSQL to database API
- Connect VPC and VPS to frontend API
- Code in a basic page to prototype frontend

# Code Engine work identified
Need to be able to access and create code engine containers for one specific API task. Code Engines to create are:
- **Code Engine Backend API Master:** This code engine container will connect all of the IBM Software Architecture together; **Language:** C++ 
- **Code Engine AI API:** Runs all logic for watsonx.ai and outputs Json strings **Language:** Python
- **Code Engine STT API:** Runs all logic for Speech-To-Text and outputs transcript as a Json string **Language:** Python
- **Code Engine Database API:** Runs all database related logic, including running queries, organising storage of data, separating case content, storing Json into EDB PostgresSQL, storing media into Object Storage **Language:** C++
- **Code Engine Frontend API:** Runs logic for VPC and VPS, including tracking user usage / demands, region tracking, creating / destroying VPS instances, displaying UX designed interfaces, communicating user inputs to Backend API. **Languages**: JavaScript, .js, 

Conections include:
- Connecting all components with necessary API keys
- Connecting frontend and database API to backend API
- Connecting backend API to IBM Enterprise Services

# Storage Work Identified
- Configuring Storage formatting to be Json
- Configure Standard and Archive Teirs

# Database Work Identified
- Configuring Object Storage to include the following: {caseID: , original_video:, original_audio, processed_video: , processed_audio}
- Configuring EDB PostgresSQL, including following Json format specified by Dev2

# Service / Integration Dependencies Identified

# Week 1 Task Inputs Specific
Roadmap: Get all components online, setup foundation to finish prototype in week 2.

Goal: Get all components online, start connecting everything together via code

# Week 2 High-Level Work Proposed
Roadmap: Finish initial prototying, list all bugs, blockers and problems encounted.

Goal: Creating specific Code Engine APIs specified above, create relevant APIs

# Week 3 High-Level work Proposed
Roadmap: Finalise prototype debugging

Goal: Finish prototype meeting MVP, debugging and prepare product for showcase in Playback 2.

# Time inputs
| Task | Activities | Time |
| --- | --- | --- |
| | |

# Implementation Risks noted
- Unexpected delays and timely configuration of buckets and containers will throw this optimistic timeline out of the window

# Notes to PM / BA
- **To the PM(Dat Nguyen Minh):** Save all the API keys for safe keeping, use my suggested sprint planning to define my tasks for next week, below are the tasks I suggest you should organise, but is only a suggestion:
- **To Dev2(Kai Lek Kum):** Prepare AI and STT outputs to be JsonB, be compatible with C++ Code Engine containers.

https://chatgpt.com/share/6aa4b913-05e8-83ec-bf34-24ccc896d055