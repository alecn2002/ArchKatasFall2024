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

In details:
Instead of the unlock service to provide the matched anonymized resumes - the role would be taken by the matching service.
Only then employers selects subset of matches for unlock that go to the unlocking service.

See: Solution/Iteration2nd/Level2-archimate-Business&Application/[Business] Main flow - split to subsystems - updated.svg

### Consequences

##### PROS:
Better separation of duties while mantaining she same security level. 

##### CONS:
More modules exposing write access granted interfaces. 

### Notes 
Hand notes
1
![image](https://github.com/user-attachments/assets/1a76f7ed-33c5-4931-8a3c-1756d31b1891)

2
![image](https://github.com/user-attachments/assets/01d685b6-2428-4bee-a3d4-ef579b99fae0)


