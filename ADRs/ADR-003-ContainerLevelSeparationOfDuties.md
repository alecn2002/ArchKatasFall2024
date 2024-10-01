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

See: Solution/Iteration2nd/Level2-c4model-Containers/Container Diagram.svg

### Consequences

##### PROS:
Better security than realizing discussed functions in a single container. 

##### CONS:
Higher cost of implementing more modules.