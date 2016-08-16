# OBSOLETE, MOVED TO https://github.com/web2py-plugins/web2py-plugins

## plugin_manage_groups
**Web2py plugin to manage groups and group membership of the users.**

(C) Zvolsky, licensing same as Web2py

zvolsky@seznam.cz, mirek.zvolsky@gmail.com,

sources: ```github.com/zvolsky/plugin_manage_groups```

download (published using gh-pages branch): [zvolsky.github.io/plugin_manage_groups/web2py.plugin.manage_groups.w2p](https://zvolsky.github.io/plugin_manage_groups/web2py.plugin.manage_groups.w2p)

- Auto-**create the 'admin' group** and **make the first user its member**.
- Allow **creating new groups** via ```(app)/plugin_manage_groups/group/(new-group-name)```.
- Allow **add and delete memberships** to the group at ```(app)/plugin_manage_groups/group/(group-name)```.
  - For the 'admin' group there is shortcut: ```(app)/plugin_manage_groups```
- Links to switch managed groups at ```(app)/plugin_manage_groups/group/(group-name)```.
- **Deleting of empty groups** at same page.
- Adaptive with small or large count of users/members.
- Non default table names for auth are allowed.

## How to use it

Navigate to: ```(app)/plugin_manage_groups```

or to: ```(app)/plugin_manage_groups/group/(group-name)```

Use defined group membership in the standard manner, i.e. @auth.requires_membership('groupname') -or- if auth.has_membership('groupname').

## Configuration

Configuration is not necessary, but it is possible with the PluginManager, i.e. set
```
plugins.manage_groups.(configuration-parameter)=(value)
```
in model db.py (or other model, alphabetically after db.py but before plugin_.py).

**Configuration parameters and their defaults**:

| param | default | meaning |
| ------ | ------ | ------ |
| first_admin | True | should be admin group auto-created and the 1st user made admin member? |
| admin_group | 'admin' | name of the admin group |
| create | True | can be new groups created when navigating to plugin_manage_groups/group/(group_name)? |
| limit_dense_rows | 11 | when there are less users they will output each user on separate line |
| limit_hide_users | 61 | starting from this user count, users will be not listed and are selectable with the html input field only |

## Caveats

Use only ASCII characters in group names. Hope this is not problem, because membership administration and group names are accessible for admins only.
