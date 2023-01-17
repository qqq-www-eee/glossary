# Users and Roles

There are different roles in the system:

1. A foreman / construction site manager
2. A technical supervisioner
3. A workman  

All of them are able to:
1. Create-browse-edit-delete their own chessboards and all the dictinaries and settings (originated from theselves!)  
2. Users can never create-browse-edit-delete the others' chessboards, dictionaries and settings.  
3. Sometimes, when an access is granted, users can browse others' chessboards. But not setting, or dictionary, or others' access.  
4. Sometimes, when an access is granted, users can edit the others' chessboards. But not setting, or dictionary, or others' access.  
5. ASDF
6. Edit their own chessboards! And never others' chessboards.
7. Assign jobs/orders to others / to themselves
8. Assign tech.check to others / to themselves
9. Give right to view data
10. Give right to edit data
11. Browse the site-manager-view

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

What can and can not a foreman (ordinary user) do:

| Feature | Foreman |
|----|-|
| | |




HAVE:
Creating accounts for Workmen and Techmen - without any SMS confirmations.
- Account has fields: Name, Surname, Middlename, Phone number, email
- We do not want the user to scrupulously write down all his wormen's full names. But for users they are obligatory.
- What about state-models - for invitations and for accounts.


ALTERNATIVES:
- Creating not accounts but rather a handbook?
- ~~Asking everyone for confirmation~~

PROBLEMS:
- A user is able to insert incorrect telephone number
- A user is NOT able to correct neither phone number nor name
- What is "a position"?
- user fulfills only 1 field, and system decided what it is on its own.
- Whenever someone is registered in system (on his own or via invitation link = access granted) his name in almost any case will be changed - through the entire system. 
- previous user can loose in their contacts! User is confused
- The system cannot work with semantics of the given string and will always think that it is, for example, just Middle name. incorrect parsing and lost of semantics
- We can loose the real data, if firstly name was entered correctly and after that substituted with dummy data. Data loss



