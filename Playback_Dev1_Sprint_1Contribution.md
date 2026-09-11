# Introduction
I am Alexandre Lee, I am on the Team 5's developer team, and is mainly responsible for designing and creating the software architecture solution for this project, with the stakeholder needs being defined by my PM, BA and UX.

# Architecture / Infrastructure Explanation:
- How is it scalable: Use of VPC and VPS containers, all run with IBM Code Engine Containers.
- How is it secure: Implements cybersecurity principles such as Separation of Privilege, Planned Blockchain and Zero-Trust Architecture, albeit limited since security isn't the highest priority.
- How does it protect Auditors: Any submitted case must first be processed with AI, Code Engine as a Backend API connects the Frontend to the IBM services such as watsonx.ai, then the processed cased is saved in Json format and media saved in Object Storage, then te case is viewable to the Auditors.
- Transparency: 

# What I contributed this sprint — specific, not "I helped with the app."
- Validated multiple containers including: IBM Cloud, Code Engine, VPC, VPS, watsonx.ai, STT, EDB PostgresSQL
- Identified and escalated blockers
- Designed and refined overall Software Architecture

# One honest blocker or learning.
- Learning to design and document in a team framework
- Honest blocker, didn't get the project at all, informed PM(Dat) about it
- Mispelled STT and TTS, caused confusion within the team.
- Learn IBM systems