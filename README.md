# Architectural Katas: Fall 2024
This repository is the submissiion to [Architectural katas: Fall 2024](https://www.oreilly.com/live-events/architectural-katas-fall-2024/0642572006974/) by team [I2C](I2C_Team.md). 

The team proposes a rough first draft of an architecture for the **ClearView** System (aka "System") according to the [requirements](Diversity%20Cyber%20Council%20Kata%20Requirements%202024.md) proposed by the [Diversity Cyber Council](https://www.diversitycybercouncil.com/).

## Structure of the repository
_Work in progress_
- [ADRs](ADRs) Architectural Decision Records
- [SecurityAspect](SecurityAspect) on System security
- [Solution](Solution) Architectural description
    - [Characteristics](Solution/Characteristics) driving characteristics of the architecture
    - [Iteration1st/Models](Solution/Iteration1st/Models) 1st draft of main [business flow](Solution/Iteration1st/Models/\[Business\]%20Main%20flow.svg) and [System Context](Solution/Iteration2nd/Level1-c4model-SystemContext/System%20Context.md)
    - [Iteration2nd](Solution/Iteration2nd) C4 and Archimate diagrams for current iteration

## Team

We're 2 SW architects from Poland occasionally joined by colleagues from Germany and Italy.
[All](I2C_Team.md) are professionals in SW development with multi-year experience.

Name of the team **I2C**

- **I2C** is a name of a computer platform management interface (quite old one, replaced by I3C - but we all in the team are not young as well)
- **I2C** also could be deciphered as "2 colleagues from Intel and Company" )))

Great experience is, thanks to ArchKatas, to quickly and reliably establish collaboration environment from scratch
for occasional international team.

## Solution

### Architectural characteristics and Architecture Style

After evaluating [Architectural characteristics](Solution%2FCharacteristics%2Farchitecture-characteristics-priority.md)
we've chosen the driving ones:
- Interoperability 
- Security – data privacy
- Data consistency

This list of major characteristics lead to choose _Service-Oriented_ architecture style.

The rest of architectural characteristics that are of high importance for the project:
- Data Integrity
- Workflow
- Responsiveness
- Scalability

### Services

The following services are defined for the overall system structure as shown on the [Main Flow with split to subsystems](Solution%2FIteration2nd%2FLevel1-archimate-Business%2F%5BBusiness%5D%20Main%20flow%20-%20split%20to%20subsystems.png) diagram:

![Main Flow with split to subsystems](Solution%2FIteration2nd%2FLevel1-archimate-Business%2F%5BBusiness%5D%20Main%20flow%20-%20split%20to%20subsystems.png)

Analysis of external communications shows the list of external systems need to communicate with DCC system:
- Job Seekers
- AI engine (implicitly stated that it's hosted outside of DCC)
- HR Management Systems of Employers
- Payment System

![Context Diagram.vpd.svg](Solution%2FIteration1st%2FModels%2FSystemContext%2FContext%20Diagram.vpd.svg)

### Containers

![Container Diagram.svg](Solution%2FIteration2nd%2FLevel2-c4model-Containers%2FContainer%20Diagram.svg)

### Components

![TEE diagram](Solution%2FIteration2nd%2FLevel3-archimate-Application%2F%5BApplication%5D%20HRMS%20Integration%20-%20service%20based.png)

### Security 

[Threat Analysis](SecurityAspect%2F01.ThreatAnalysis.md) was performed, and based on it 
[Security Architecture](SecurityAspect%2F02.SecurityArchitecture.md) was defined.

TEE diagram:

![TEE diagram](Solution%2FIteration2nd%2FLevel3-archimate-Application%2F%5BApplication%5D%20AI%20Engine%20-%20Confidential%20Computing.png)
