# Roles and Privileges

## Users : 

| Space      | Role | Privileges     |
| :---        |    :----:   | :---        |
| Organization       | Admin       | Can add users into organization<br>Can add team into organization<br>Can manage role of the user<br>Can delete user from organization<br>Can manage team in the organization<br>Can delete team from the organization<br>Can create workspace    |
| Organization    | Collaborator        | Can add users into organization<br>Can manage role of the user<br>Can add team into organization<br>Can manage team in the organization<br>Can create workspace       |
| Organization       | Member        | Can see users in the organization<br>Can see teams in the organization<br>Can see workspace details    |
| Workspace   | Admin        | Can create cluster<br>Can create Pipeline<br>Can see workspace details<br>Can add users into workspace<br>Can add teams into workspace<br>Can update role of each users<br>Can update role of the team in  workspace<br>Can delete users from workspace<br>Can delete teams from workspace       |
| Workspace   | Collaborator       | Can create cluster<br>Can create Pipeline<br>Can see workspace details<br>Can add users to workspace<br>Can update role of each users<br>Can add teams into workspace<br>Can update role of the team in  workspace    |
| Workspace   | Member        | Can see cluster<br>Can see pipelines<br>Can see workspace details       |
| Cluster      | Admin       | Can see cluster<br>Can add users into cluster<br>Can add teams into cluster<br>Can update the role of each user<br>Can update the role of team<br>Can delete user from the cluster<br>Can delete team from the cluster    |
| Cluster   | Collaborator        | Can see cluster<br>Can add users into cluster<br>Can add team into cluster<br>Can update the role of team<br>Can update the role of user       |
| Cluster      | Member       | Can see cluster<br>Can see pipeline    |
| Pipeline   | Admin        | Can see pipeline<br>Can add users into pipeline<br>Can add teams into pipeline<br>Can update the role of each user<br>Can update the role of team<br>Can delete user from the pipeline<br>Can delete team from the pipeline<br>Can see alerts<br>Can create alerts<br>Can update alerts<br>Can delete alerts       |
| Pipeline      | Collaborator       | <br>Can see pipeline<br>Can add users into pipeline<br>Can add teams into pipeline<br>Can update the role of each user<br>Can update the role of team<br>Can see alerts<br>Can create alerts<br>Can update alerts   |
| Pipeline   | Member        | Can see pipeline<br>Can see alerts       |

## Teams: 

For the convenience of setting same privilege to multiple users they can be added into teams. So, team privilege will be reflected on them. **In case, if a user has multiple privileges within a given context, then the highest privilege among them will apply.** 

For example, if a user has member access in workspace and admin access in team, then he will get admin access 
