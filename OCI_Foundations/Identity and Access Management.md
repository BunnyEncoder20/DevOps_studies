# Identity and Access Management

## IAM Introduction

### OCI IAM
- IAM = Identity and Access Management service a.k.a Fine Grain access control a.k.a Role based access control service.
- There are 2 key ascepts to this:
    1. AuthN (Authentication) - Who are you ?
    2. AuthZ (Autherizations) - What permissions do you have ?
- These allows user to be assigned one or more predetermined roles, and each role comes with a set of permissions.

### OCI Identity Concepts
![](../assets/ociIAMconcepts.jpeg)

### Identity Domains
![](../assets/identitydomains.jpeg)
- It is like a container for our users and groups
- An identity domain represents a user population in OCI and associated configurations and security settings
![](../assets/identiitydomaindiagrame.png)
- In pratice:
    - We create OCI Identity Domain
        - Wihtin which there are users which are part of groups
        - We write policies (role-based access) against these groups
        - Policies are scoped to a tenancy (account or compartments)
        - Each compartment has it's own resources
- Resource include:
![](../assets/resources.png)

- To identify each of these OCI recourses they have their own unqiue OCID (Oracle Cloud ID) which are unique Oracle-Assigned Identifiers
![](../assets/ocid.png)
- Each section:
    - \<Resource Type\> = type of resource (compute instance, block storage)
    - \<REALM\> = set of regions that share same characteristics (Govt. realm, Commercial Realm)
    - \[REGION\] = The region the resource is in
    - \<UNIQUE ID\> = unique to the created resource
![](../assets/egocids.png)

---

## Compartments

- With our Oracle tenancy (account), we also get a Compartment. Think of it as a logical construct which houses all of our related resources.
- Though the Root compartment can house ALL resources, it is best practice to make dedicated compartments for each isolated resources.

- We Create them for Isolate and control access.
    - Each resources we create belongs to a single compartment
    - The resources can be moved from one compartment to another
    - The rources of different comapartments can communicate with each other
![](../assets/compartments.png)

- The Main point of compartment can be summurized in below image:
![](../assets/egcompartmentAccess.png)

- Compartments can be multi-regional and Nested also
![](../assets/multiregionCompartment.png)

- We can set Qoutas and Budgets on Compartments
![](../assets/qoutas&budgets.png)
