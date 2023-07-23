#devOps #architecture #book

## Architecture Consists of:
### 1. Structure
- [ ] type of **architecture style** the system is implemented in.
	- [ ] e.g: Microservice, layered, microkernel, etc

### 2. Architecture Characteristics
- [ ] Defines the **success criteria** of the system.
- [ ] e.g: -ilities
	- [ ] Availability, Reliability, Scalability, Security, Fault tolerance, Performance, etc

### 3. Architecture Decisions
- [ ] Defines the **rules** for how a system should be constructed.
    - [ ] e.g: decision to restrict presentation layer from making direct database calls.

#### Variance
- [ ] If a particular architecture decision cannot be implemented in on part of the system due to some condition or other constraint, that decision (or rule) can be **broken** through something called variance.
- [ ] An exception to the decision or rule is analysed by Architecture Review Board (**ARB**) or **Chief** Architect and is either approved or denied **based on justifications and trade-offs**

### 4. Design Principles
- [ ] Design Principle is more of a **guideline** than a hard-and-fast rule like architecture decision.
    - [ ] e.g: Whenever possible, leverage async messaging between services to increase performance.
        - [ ] Architecture decision cannot cover every single condition, so design principle can be used to provide guidance for preferred method to allow developers to choose more appropriate communication protocol give a specific circumstance.