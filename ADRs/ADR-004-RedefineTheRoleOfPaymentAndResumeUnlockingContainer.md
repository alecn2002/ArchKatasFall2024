## 004 Redefine the role of the Payment and Resume Unlocking Container
The Solution shall separate duties at container level - redefined approach

### Status
ACCEPTED

### Context
To realize security considerations as well as provide the assumed level of modulatity - system level duties shall be separated at container level: in this solution focus on separating the Payment and Unlocking function from the Matching function.

### Decision
To protect user private data (The Full Resume in our case) by spliting the containers in order to make the attack and potential bug surface smaller w.r.t. to avoid premature, unauthorized accessing of the protected resource. 
Two containers were specified: 

 1. Resume Open-Role Matching Container
 2. Payment and Resume Unlocking Container

The change in the architecture is that the Matching Container would also serve the matches on the anonymized data - which is not introducing threat to the Full Resume data.

See: Solution/Iteration2nd/Level2-archimate-Business&Application/[Business] Main flow - split to subsystems - updated.svg

### Consequences

##### PROS:
Better separation of duties while mantaining she same security level. 

##### CONS:
More modules exposing write access granted interfaces. 