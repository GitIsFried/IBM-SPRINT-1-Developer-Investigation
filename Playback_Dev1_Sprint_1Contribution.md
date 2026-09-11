# Introduction
I am Alexandre Lee, I am on the Team 5's developer team, and I am mainly responsible for designing and creating the software architecture solution for this project, with the stakeholder needs being defined by my PM, BA and UX. In this sprint, I was tasked with cataloging the current existing containers, whether they exist, are configured, their naming conventions, and what they're role is in the architecture, identifying any blockers and issues along the way.

# What I contributed this sprint — specific, not "I helped with the app."
- Validated multiple containers including: IBM Cloud, Code Engine, VPC, VPS, watsonx.ai, STT, EDB PostgresSQL.
- Researched what each container does in detail:
- **Code Engine:** Where the code runs. Runs all application code including containers below, handlss both frontend and backend APIs, connects frontend to IBM Enterprise network.
- **VPC + VPS:** How the server runs, amount varies based on demand, mainly handles frontend stuff.
- **watsonx.ai** Analyses cases with ML, identifies timestamps, summary.
- **STT:** Converts audio into text for documentation and AI analysis.
- **EDB PostgresSQL + JsonB:** Storage of all data.
- Catalog current container naming conventions.
- Identified and escalated blockers
- Designed and refined overall Software Architecture

# Architecture / Infrastructure Explanation:
- How is it scalable: Use of VPC and VPS containers, all run with IBM Code Engine Containers.
- How is it secure: Implements cybersecurity principles such as Separation of Privilege, Planned Blockchain and Zero-Trust Architecture, albeit limited since security isn't the highest priority.
- How is it integrity: A library of SHA1 hash of all files, stored on a .txt file will ensure that no hacker alters the files.
- How does it protect Auditors: Any submitted case must first be processed with AI, Code Engine as a Backend API connects the Frontend to the IBM services such as watsonx.ai, then the processed cased is saved in Json format and media saved in Object Storage, then te case is viewable to the Auditors.
- Transparency: 



# One honest blocker or learning.
- Learning to design and document in a team framework
- Honest blocker, didn't get the project at all, informed PM(Dat) about it
- Mispelled STT and TTS, caused confusion within the team.
- Learn IBM systems