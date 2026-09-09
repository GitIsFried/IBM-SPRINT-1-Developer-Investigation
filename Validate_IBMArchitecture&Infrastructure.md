What to do:
- Review Architecture and finer details
- Confirm all assumptions are correct
- Confirm Code Engine Role
- Confirm Storage Role
- Confirm database direction
- SST placement
- Watsonx.ai Placement

Check
- Dev2 flow consistency check
- Aut/security considerations reviewed: What are the threat? What are the options to counter?
- Human final decisions represneted?
- Confirm all environmental dependencies documented?

Prepare for PM
- Playback architecture visuals: Make a new better, cleaner, more IBM like architectural visual.
- All evidence shared with PM

Goal:
Validate that the IBM architecture actually supports the Core MVP and Dev2 AI/STT flow, identify anything missing or inconsistent, document the decisions/blockers, and provide clear evidence for PM playback.

# Minimal Viable Product
## Summary
In this section we're analysing teh MVP
## Stakeholder Needs: 
## Essential Functions:

## Validation Table

## Dependencies Table

## Software Architecture - AI / STT Flow Inconsistencies

## Resolutions

# Developer 2(Kai Lek Kum) Flow Validation
## Summary
In this section we're exploring whether Dev2's AI and STT flow architecture is compatible. In depth we're analysing:
- Visual Architecture
- Valitation Table of each component's: Steps, Inputs, Outputs, Architectue Components, Status.
- Dependencies Table of each component's:
- Inconsistencies and Resolution


## AI / STT Flow
![diagram_svg](Image_Evidence_3/diagram.svg)
## Validation Table
| Steps | (1) Content Input | (2) AI/STT Processing | (3) Structured Result | (4) Backend |
| --- | --- | --- | --- | --- |
| Input | Video and Audio | Video and Audio | Processed Video and Audio, STT transcript | AI results and OG case |
| Output | Upload Video and Audio | Process video and audio with AI, transcribe with STT | Convert to Json format and match dependencies | Store cases |
| Architecture Component(s) | Application/VPS | IBM watsonx.ai, WML, IBM STT | IBM Code Engine | Object Storage, EDB Postgre |
| Status | Unready | Ready | Ready | Unready | 

## Dependencies Table

## Software Architecture - AI / STT Flow Inconsistencies

## Resolutions

# Architecture Review
## Overall Architecture

## Architectural Assumption

## Architectural Roles and Placement
| Object / Bucket | Role / Placement |
| --- | --- |
| Code Engine | |
| Object Storage | |
| EDB Database | |
| STT model | |
| Watsonx.ai | |

## Network Check

# Security and Access

# Decisions & Dependencies

# Playback Preparations(To use by PM in slides)

# Sources
