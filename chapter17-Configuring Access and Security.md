# Managing Identity and Access Management

## Viewing Account IAM Assignments
- Viewer: read only
- Editor: Viewer + modify an entity
- Owners: Editor + Manage roels and permission on an entity, set up billing for a project
- IAM roles are collections of permissions

## Assigning IAM Roles to Accounts and Groups
- Least Privilege
- Separation of Duties
- Defense in Depth, which applies multiple, overlapping security Contorls

## Defining Custom IAM Roles
- not all permissions are availble for use in a custom role


# Managing Service Accounts
- SA are used to provide identities independent of human users
- SA are assigned to VMs, which then use the permissisons available to the service accoutns to carry out tasks

## Managing Service Accounts with Scope
- Scopes are permissions grated to a VM to perform some operations
- Scope Authorize the access to API methods
- VM needs both IAM and scope configured
- An instance can only perform operations allowed by both IAM roles assigned to the servie account and scopes defined on the instacne
- Default access, Full Access, Set access for each API

## Assigning a service account to a VM instance
- to grant access to a project, navigate to the IAM page of the console and add a member. Use the SA email as the entity to add,

## Viewing Audit logs

**What is Scope**









