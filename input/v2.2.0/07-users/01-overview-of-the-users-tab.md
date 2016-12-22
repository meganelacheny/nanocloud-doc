---
title: "Overview of the Users tab"
excerpt: ""
---
[block:callout]
{
  "type": "danger",
  "title": "The Users tab is only available for administrators!"
}
[/block]
The Users tab is composed of three different sub-tabs: Users, Groups and Teams (which is optional).
[block:api-header]
{
  "type": "basic",
  "title": "Users"
}
[/block]
In the Users tab, you can [create](doc:create-a-new-user), [edit](doc:modify-the-users-information) and [delete](doc:delete-a-user) a user.

The Users tab displays the list of registered users, including the administrators.

For each registered user, the information below are listed:
* Name: first name and last name
* Email: which is also the ID to login
* Type of user: Administrator or Regular user
* Connection status: the dot is grey when the user does not use a VM at the moment, and green when the user uses a VM
* (optional) Team: name of the team the user belongs to
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fed6bea-users_overview_220.png",
        "users_overview_220.png",
        1277,
        676,
        "#146cb4"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Groups"
}
[/block]
In the Groups tab, you can [create groups](doc:create-a-new-group), [add and remove applications from groups](doc:add-remove-an-application), [add and remove groups members](doc:add-remove-a-group-member), and also [delete groups](doc:delete-a-group).

The Groups tab displays the list of users groups, as well as:
* the number of users in the group
* the number of images available for this group 

Groups are intended to manage the users rights to access applications. You can create a pool of applications only available for a given set of users. 
*Example: you can create a group for developers, a group for current users, a group for sales demonstrations and a group for customers or for partners. The possibilities are endless!*
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e851189-groups_overview_220.png",
        "groups_overview_220.png",
        1278,
        677,
        "#146cb4"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Teams"
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Teams are optional.",
  "body": "You can activate or deactivate this feature in the [User rights](doc:configure-user-rights) section of the Configuration tab."
}
[/block]
In the Teams tab, you can [create and manage teams](doc:create-a-team) and [manage a team's files](doc:manage-a-teams-files).

How teams function on Nanocloud is very simple. 
Any user can create a team and add members to this team. Then, from the VDI, the members of the same team will be able to share files that them only will view and manage.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5ed31d2-teams_overview_220.png",
        "teams_overview_220.png",
        1263,
        767,
        "#e9eaeb"
      ]
    }
  ]
}
[/block]