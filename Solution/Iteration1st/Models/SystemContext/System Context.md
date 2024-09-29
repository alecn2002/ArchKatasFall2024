### Context of the ClearView System

![Context Diagram vpd](Context%20Diagram.vpd.svg)
- **HiringManager** _System Users_ that access the System as representative of the "Employer" companies invested in providing a more equitable experience to career seekers.
    - Aka "Hiring Managers" in DCC requirements. 
- **JobSeeker** _System Users_ who are professionals seeking a less tedious and more equitable hiring process that values their skills and abilities.
    - Aka "Job Candidate" in DCC requirements. 
- **Admin** _System Users_ who are responsible for the management of the platform, registering users, providing data analytic reports on company performance and solution building services with executives.
    - Aka "Administrators" in DCC requirements. 
- **TrainedLLM** _External System_ which provides the AI functionalities described in the DCC requirements.
    - It is not in the scope of this architectural description to design the AI.
    - Since the DCC requirements state to assume its existence as a given, the TrainedLLM is modeled as an external system as a convenient abstraction, which does not preclude its inclusion as a component or any more integrated part of ClearView.
- **HRMS** _External System_ representing a collection of HR management systems used by the "Employer" companies to manage recruitment and application tracking for the purpose of matching open roles to suitable resumes provided by ClearView.
    - Note that this also needs to represent a single individual "Employer" looking for a contractor or a very small company with no software system for HR management. 
- **PaymentsProcessor** _External System_ representing a collection of systems used by "Employers" and **ClearView** for payment of unlocked resumes.
    - (@TBD verify with DCC if a standard interface to a credit cards Payment Processor is enough, or do they need to interface to any corporate invoicing/billing systems as well?)
