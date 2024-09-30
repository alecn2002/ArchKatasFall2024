# Architecture characteristics
A list of the most relevant architecture characteristics for the System, with explanations. 

## Top–three. 
These are the driving characteristics that the System _must have_ or it will not be useful: 

### Interoperability 
- **Definition**: The ability of the system to interface and interact with other systems to complete a business request. 
- **Rationale**: the system is inefficient unless it can communicate with the Employer's HRMS.
    - Note that "Configurability" is not what we need, because ClearView does not provide custom on–demand versions of itself. The adapter component that will interface with the external HR may be able to add a new peer by means of a configuration file, rather than adding code, but it is not a issue for the architecture as a whole.  

### Security – data privacy
- **Definition**: The ability of the system to restrict access to sensitive information or functionality. 
- **Rationale**: good Security, especially of the PII provided by the users is critical. 
    - The System interoperates with HRMS, which may have strong security and confidentiality requirements depending on what they will expose to our system.
    - The System manages PII (Personal Identifying Information) of a sensitive nature, whose disclosure may have legal consequences. 

### Data consistency
- **Definition**: The data across the system is in sync and consistent across databases and tables. 
- **Rationale**: this is necessary for the business credibility of the System, as lack of consistency in the data flow from original Resume to matching Open Role may lead to missed hiring opportunities for the "Job Candidate" and, possibly, breach–of–contract or loss of confidentiality situations involving both "Employer" and "Job Candidates" stakeholders. This is necessary for the collection of metrics and KPIs, which is a _hard requirement_ of the System and which needs consistent data. 

## Other Driving Characteristics. 
These are what should be expected from this kind of System, besides the implicit characteristics. Roughly in order of priority: 

### Data Integrity
- **Definition**: The data across the system is correct and there is no data loss in the system. 
- **Rationale**: can't have missing resume or role offers, once they have been accepted by the system.
    - Moreover, one hard requirement for the System is that it must allow the collection of measurements of significant metrics, which must be correct and complete. 

### Workflow
- **Definition**: The ability of the system to manage complex workflows that require multiple parts (services) of the system to complete a business request. 
- **Rationale**: the workflows in the System are not very complex, but they do need to access at least two subsystems each.
    - Moreover, if the System is succesfull, the expected "solution building services with executives" will very likely require the expansion of services and to the introduction of related workflows. 
 
### Responsiveness
- **Definition**: The amount of time it takes to get a response to the user.
- **Rationale**: this is a user–interactive system.
    - Attention should be given to reasonable response times.
    - The AI–Candidate interaction is a dialogue. Once a De–identified Resume is submitted, matching with Open Roles should be displayed with speed comparable to an ordinary search query on the internet.
    - While this implies some System performance elasticity during peak usage hours, Elasticity in itself is not a Driving Characteristic as we do not expect JobSeeker(s) to suddendly generate extreme load surges.
    - Moreover, the System should serve a four time zones span, which implies some load distribution along the 24 hours. 

### Scalability
- **Definition**: A function of system capacity and growth over time; as the number of users or requests increase in the system, responsiveness, performance, and error rates remain constant. 
- **Rationale**: If successful, the System may see increasing adoption as the potential user pool is quite large. While we expect that the "Employer" and HMRS pool will be capped, "Job Candidate" users are many more. They may grow faster and to a greater total amount. Hence, the System architecture must be able to evolve to satisfy future growth. 
