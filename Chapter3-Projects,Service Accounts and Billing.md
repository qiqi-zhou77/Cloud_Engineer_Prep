## Projects and Accounts
Resource Hierarchy:  way to group resources and manage them as a single unit
The access to resources in the resource hierarchy is controlled by a set of policies that zou can define

### Google Cloud Resource Hierarchy
Organization -> Foler -> Projects
**Organization**
- Corresponds to a company or organization
- A single cloud identity is associated with one org
- Cloud identities have super admins, and the super admin assign the role of Organization administrator identity and access management to users who manage the organization.
- Org admin IAM role are reponsible for:
    - Define the structure of the resource hierarchy
    - Define identity and access management policies over the resource hierarchy
    - Delegate ovther management roles to other users


**Folder**
- Optional, Folder can contain folders and projects

**Projects**
It is in projects that we create resources, use google cloud services, manage permissions and manage billing options


### Org Policies
The service control the access to an org"s resources

***IAM let you assign permissions so that users or roles can perform specific operations in the cloud***
***Policy lets you specify limits on the ways resources can be used***
***IAM specifies who can do things, and policy specifies what can be done with resources***

**Constraints**
- List Constraints  and Boolean Constraints


### Managing Project
- Number of projects can be created is limited by quota


## Roles and Identities

### Roles in google cloud
- role is a collections of permissions. Roles are granted to users by binding a user to a role
- Basic Role: Owner,Editor, Viewer
- Predefined roles: principle of least privilege, granular permission
- Custom roles: assemble by using permissions defined in IAM, but some are not available

### Granting roles to Identities
- Permissions can not be assigned to users, it must be assigned to roles then the roles are assigned to users

## Service account
Having applications or VMs act on behalf of a user or perform operations that user odes not have permissions to perform

- user managed : up to 100 per project
- google managed
- Can be managed as a group of accounts at project levle or at the individual service account level
- Created automaticaly when resources are created

## Billing

### Billing Accounts
- Store info about how to pay charges for resources used
- A billing account is associated with one or more projects
- Self service: charged automatically, pay by credit card or debit card
- Invoiced billing account: large enterprise
- Roles related to billing:
    - Billing account creator: create new self-service billing accouts
    - Billing account admin: manage billing accounts but cannot create them
    - Billing account user: enable users to link projects to billing accounts
    - Billing account viewer: view billing accounts cost and transations

    - 
### Billing Budgets and Alerts
Defining budget and setting billing alerts

### Exporting Billing Data
Can be exported to BigQuery


## Enable APIs
All google services has api associated with them, most, however, are not enabled by default