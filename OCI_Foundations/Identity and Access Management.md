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

- Compartments can be multi-regional and Nested (6 levels deep) also
![](../assets/multiregionCompartment.png)

- We can set Qoutas and Budgets on Compartments
![](../assets/qoutas&budgets.png)

---

## Demo: Create a Compartment and Identity Domain
![](../assets/compartment&IdentityDomain.jpeg)

1. Go to compartments dashboard:
![](../assets/go2compartments.png)

2. Create the Compartment:
![](../assets/createCompartment.png)
![](../assets/compartmentMade.png)

3. Can check all our recourses in Tenancy Explorer
![](../assets/tenancyExplorer.png)

4. Go to Identity Domain Page
![](../assets/go2domains.png)

5. Creat Domain:
![](../assets/createDomainBtn.png)
![](../assets/fillDetails.png)
![](../assets/clickCreateDomain.png)

---

## AuthN & AuthZ

### Principals

- IAM entities that are allowed to interact with OCI resources
- There are two kinds of principals:
    1. IAM users (people logging to console, using recources, etc)
    2. Resources Principals (instance principals that can make API calls)
    3. Groups - Collection of Users who have same type of access to resources

### AuthN
- Authentication - Who are you? Are you who you say you are ?
- Eg:
    - when we visit a website and it asks username and password, we are being authenticated
    - In cloud resources we usually use API signing keys (OCI API + SDK/CLI or RSA key pair (PEM))
    - Auth Tokens (Oracle generated token strings or Authenticate third party APIs)

### AuthZ
- Autherization - What permissions you have? What are you allowed to do?
- These are given through policies. These can be attached to tenancies or compartments
![](../assets/AuthZpoliciesSyntax.png)

---

## Demo: AuthN & AuthZ

### Creating a User:
1. Do to Identity Domain of choice
2. Under Users Tab, Click on Create User
    1. Now just signin in as the new user (after activation), we will be able to log into the domain, but we cannot do anything as we do not have any autherization.
![](../assets/createUser.png)
3. Policies are not defined for an individual user, but for group level. Now in the Group tab, we will create a new group
![](../assets/createGroup.png)
4. Once the user account has be activated, we can add them to the group
5. At the Domain level we can make policies from the policies tab:
![](../assets/createPolicies.png)
6. Fill the Policies with necessary group and permissions
![](../assets/fillPolicyForm.png)

---

## Tenancy Setup

### Ideal Tenancy Setup includes:
    1. Don't usse root tenancy Admin for day-to-day tasks, always make a OCI Admin group and give them admin policies/permissions and their own compartment.
    2. Use MFA
![](../assets/idealTenancySetup.png)
4. OCI Admins Policies
![](../assets/OCIAdminPolicies.png)
