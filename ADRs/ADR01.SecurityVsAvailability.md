# TITLE

<span style="color:grey">*Short description stating the architecture decision.*</span>

<H2>ADR01. How to keep data secret without sacrificing availability</H2>

# STATUS

*Proposed, Accepted, Superseded*

<span style="color:yellow">Proposed</span>

# CONTEXT

<span style="color:grey">*What is forced me to make this decision?*</span>

Security keys shall be kept secret, including - as small amount of people shall have access to them, also as small number of copies shall be produced as possible.

But loosing of keys will make all encrypted data (full CVs on persistent storage) unavailable.

<span style="color:grey">*What were alternatives to decision done?*</span>

# DECISION

<span style="color:grey">*The decision and corresponding justification.*</span>

1. Private keys shall be stored encrypted with Key Encryption Keys (KEK, distinct set of keys) and be decrypted for the time of usage only.
2. Copies of KEK-encrypted private keys shall be created on external security pendrives by responsible people of the company like GM, CIO/IT manager, System Admin, etc.
    * Each copy is encrypted with its own key on top of KEK encryption.

Thus, we will have multiple copies of private keys while being hardly available for unauthorized people.

<span style="color:grey">*Tradeoffs of the decision.*</span>

Increased complexity of restoring keys in case if they're lost on the primary storage (inside the system) is a small cost that allows to ensure sensitive data availability.

# CONSEQUENCES

<span style="color:grey">*What is the impact of the decision?*</span>

# COMPLIANCE

<span style="color:grey">*Optional: How I will ensure compliance with the decision?*</span>

# NOTES

<span style="color:grey">*Optional: Metadata for the decision (author, date, etc.)*</span>

* **Author:** Alexander Novitskiy
* **Date:** 2024-09-26

