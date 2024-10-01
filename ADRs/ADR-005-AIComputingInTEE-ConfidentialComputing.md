## 005 Perform AI Processing in the Trusted Execution Environment (TEE) provided by the Cloud Confidential Computing infrastructure

### Status
ACCEPTED

### Context
The solution requires a clear security architecture as it's dealing with sensitive data as well as valuable assets as trained AI models.

### Decision
Considering the value and sensitivity of the assets, as well as the wide availability of Cloud Confidential Computing solutions the decision is to perform all processing in the Trusted Execution Environment (TEE) provided by the Cloud 
Confidential Computing infrastructure.
Either Application or VM Level Isolation solutions might be used.

### Consequences
Utilitizing HW aided cryptographic solution will provide measurable level of security matching the value of the assets.

##### PROS:
Cryptographicly protected assets. 
Smaller attack surface than with other soultions.

##### CONS:
Higher cost of implemenation of the secure and regular running application. Limited deployment HW - that needs to support HW encryption.
