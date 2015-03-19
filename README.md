# plugin_manage_groups
Web2py plugin to manage groups and group membership of the users.

(C) Zvolsky, license as Web2py

zvolsky@seznam.cz, mirek.zvolsky@gmail.com,
github.com/zvolsky/plugin_manage_groups

- Auto-**create the 'admin' group** and **make the first user its member**.
- Allow **creating new groups** via (app)/plugin_manage_groups/group/(new-group-name).
- Allow **add and delete memberships** to the group at (app)/plugin_manage_groups/group/(group-name).
  - For the 'admin' group there is shortcut: (app)/plugin_manage_groups
- Links to switch managed groups at (app)/plugin_manage_groups/group/(group-name).
- **Deleting of empty groups** at same page.
- Adaptive with small or large count of users/members.
- Non default table names for auth are allowed.

## Configuration
Configuration is not necessary, but it is possible with the PluginManager, i.e. set
```
plugins.manage_groups.(configuration-parameter)=(value)
```
in model db.py (or other, alphabetically after db.py but before plugin_.py).

Configuration parameters and their defaults:

| param | default | meaning |
| ------ | ------ | ------ |
| first_admin | True | if admin group will be auto-created and the 1st user made admin member |
| admin_group | 'admin' | name of the admin group |
| create | True | if new groups can be created when navigating to plugin_manage_groups/group/(group_name) |
| limit_dense_rows | 11 | when less users/members, it will output each user on separate line |
| limit_hide_users | 61 | when so many or more users, they will be not listed and are selectable with the html input field |
