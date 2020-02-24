# Salesforce

## Data Security

- 4 levels of data access control
    - Organization
        - maintain list of authorized users, set password policeis, limit logins
    - Objects
        - set object permissions
    - Fields
        - set field permissions
    - Records
        - allow particular users to view only certain records
        - you can manage record-level access in 4 ways:
            - Organization-wide defaults
                - set default level of access all users in the org can have
                - lock down to most restrictive level
                - use the following security tools to selectively give access
            - Role hierarchies
                - give access for users higher in hierarchy to all records owned by users in lower positions
            - Sharing rules
                - automatic exceptions to organization-wide defaults to particular gorups of users
            - Manual sharing
                - allow owners of particular records to share them with other users
- Object Permissions
    - user can have only one profile and multiple permission sets

- Profiles
    - Standard profiles
        - Read only
        - Standard User
        - MArketing User
        - Contract Manager
        - System Admin
    - Standard permissions override all other sharing settings
    - You can't edit object permissions on a standard profile
 

## Customizing Lightning Experience App
- In Lightning Exp. apps give users access to **set of objects, tabs, and other items in one convenient bundle**

- What can you put in a Lightning app?
    - standard/custom objects
    - visualforce tabs
    - lightning component tabs
    - canvas apps via visualforce
    - web tabs
    - lightning page tabs
    - utilities
    - 