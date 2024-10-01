## 003 Appply Container Level Separation Of Duties
The Solution shall separate duties at container level.

### Status
ACCEPTED -> SUPERSEDED

### Context
To realize security considerations as well as provide the assumed level of modulatity - system level duties shall be separated at container level.

### Decision
To protect user private data (The Full Resume in our case) by spliting the containers in order to make the attack and potential bug surface smaller w.r.t. to avoid premature, unauthorized accessing of the protected resource. 
Two containers were specified: 

 1. Resume Open-Role Matching Container
 2. Payment and Resume Unlocking Container

Only the second one would expose data to the HiringManager (representative of the Employer Actor). 

In details:
The "Resume/Open..Match" service should not deal with unlocking and not all matched Resumes will be approved for application by the JobSeeker. So, the match service should give _some_ de-identified resumes to the unlock service, but not all. Only the unlock service should deal with the HRMS. It is the business part, the match service should just tell to the rest of the system "this resume matches this set of open roles". The unlock service does the business decision of unlocking a matched resume if it is sold.

We do not want the HRMS to read anything from the match service. A bug may let it have a resume that is not approved for release. Moreover, it is the unlock service that need to know what it is offered to the HRMS. So the matched resumes pass through the unlock service, and not directly go to the HRMS.

See: Solution/Iteration2nd/Level2-c4model-Containers/Container Diagram.svg

### Consequences

##### PROS:
Better security than realizing discussed functions in a single container. 

##### CONS:
Higher cost of implementing more modules.

