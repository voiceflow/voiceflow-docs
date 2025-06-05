---
title: Roles and permissions
excerpt: Manage the level of access users have to your workspace.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Voiceflow supports different permission levels based on what your team members need to do. Roles are defined at the organization, workspace, and project levels.

## Owner

Owners have full control over their workspace. Owners on Enterprise plan have full control over all workspaces owned by an organization. Owners can:

<Tabs>
  <Tab title="Pro and Team Plans">
    * Invite or remove members from the workspace
    * Manage permissions for users in the workspace
    * Change billing and subscription settings
    * Edit and publish any project
  </Tab>

  <Tab title="Enterprise Plan">
    * Access and manage all workspaces in an organization
    * Modify organization settings
    * Create new workspaces inside an organization
    * Invite or remove members from any workspace
    * Manage permissions across all workspaces
    * Change billing and subscription settings
    * Edit and publish any project
  </Tab>
</Tabs>

> ℹ️
>
> The person who creates a workspace is automatically made its Owner. Owners also count as Workspace Editors.

<br />

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