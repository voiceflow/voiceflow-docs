---
title: Roles and permissions
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
***How to set Workspace and Assistant-level permissions for your workspace members?***

Depending on the responsibilities of your team members, they may require different access permissions on an organizational, workspace or assistant level. 

## Owner

The highest level of administration in Voiceflow, Owners can access and edit all Workspaces in an organization. Owners can:

* Access all Workspaces (Enterprise)
* Access Organization Settings (Enterprise)
* Create new Workspaces (Enterprise)
* Manage member permissions on any Workspace
* Invite or remove members
* Modify billing and subscriptions on any Workspace
* Edit and publish all Assistants

*Note: Owners are counted as a Workspace editor. Typically, the person who created the workspace is automatically assigned as an Owner.*

## Admin

Workspace-level administrators that can access + edit everything in their workspace. Admins can:

* Access Workspace settings
* Manage member permissions on the Workspace
* Invite or remove workspace members
* Modify the Workspace’s billing and subscription details
* Edit and publish all Workspace Assistants

## Editors

Editors are Workspace members who build the Assistant experience. As an Editor, you can:

* Edit all Workspaces Assistants
* Access an Assistant’s Settings
* Edit all aspects of the design canvas
* Import and Export Assistant or NLU data
* Publish the Assistant

*Note: Editors can no longer invite new members to the Workspace*

## Viewers

Viewer roles are meant for collaborators that consume a Workspace’s Assistant designs. Viewers can:

* View all Assistant canvases
* Leave comments

## Billing

A workspace-level billing administrator that can:

* View Assistants
* Leave comments on Assistants
* Invite or remove workspace members
* Modify the workspace’s billing and subscription details

## Assistant Level Permissions

Assistant-level permissions let you grant granular access to view-only roles. This means you can let a Viewer have edit rights for a specific Assistant while maintaining their view-only access to other Workspace Assistants. 

*Note*: 

1. *Assistant-level permissions only work if the user is a Viewer or Billing role on the Workspace. Owners, Admins, and Editors can’t be downgraded to the Assistant level as they have global edit privileges.*

2. *When you grant a Viewer Assistant-level access, they are counted as an Editor seat*
