# Users and Roles

There are different roles in the system:
    1. foreman + construction site manager
    2. technical supervision
    3. workman

All of them are able to: 
    1. Create new chessboards
    2. Edit their own chessboards! And never others' chessboards.
    2. Assign jobs/orders to others / to themselves
    3. Assign tech.check to others / to themselves
    4. Give right to view data
    5. Give right to edit data
    6. Browse the site-manager-view

LEFT assigns a job to UPPER

| ...     | foreman | tech | workman |
|---------|---------|------|---------|
| foreman |    +    |      |    +    |
| tech    |         |      |    +    |
| workman |         |      |    +    |

If two workmen are given the rights to edit chessboard, and one of them deleted some stuff, for example, the list of works, what will user do?

Restoration of cheesboard! 
Logs of versions!

And still, we shall not give an opportunity to anyone to alter dictionaries, such as Workman list, TechSV list, and still - how can two foremen become friends of get access to one another's chessboards?
 - via links
 - via access


---





    
