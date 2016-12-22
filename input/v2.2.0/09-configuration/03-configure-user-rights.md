---
title: "Configure user rights"
excerpt: ""
---
[block:callout]
{
  "type": "danger",
  "title": "This feature is only available for administrators!"
}
[/block]
In the **User rights** tab, you can:
* decide whether the user can register himself or not, and select a default group and an expiration date for the new users
* decide whether you automatically log off after closing the VDI or not 
* set a credit limit to users using AWS
* enable the creation of teams
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f116b8a-configuration_userrights_220.png",
        "configuration_userrights_220.png",
        1264,
        825,
        "#146cb4"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Registration, default group and expiration date"
}
[/block]
In the **User rights** tab, tick or untick the box next to "User can register himself" to decide if users can register themselves.

**DEFAULT GROUP**
If users can register themselves, you can choose a default group. All new users who registered themselves will then automatically join the default group.

To do so, click on the name of the group to make it the default one.
Your changes are automatically taken into account.
[block:callout]
{
  "type": "success",
  "title": "You have successfully defined a default group for new users!"
}
[/block]
**EXPIRATION DATE**
You can also enter an expiration date which will apply to all new users who registered themselves.

1. Enter the number of days you want the new users to have access to Nanocloud Software.
2. Click :fa-check: to validate your changes.

Your changes are automatically taken into account.
[block:callout]
{
  "type": "success",
  "title": "You have successfully defined an expiration date for new users!"
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Logoff after closing the VDI"
}
[/block]
When you are in the VDI, on the right of the top bar, you have two buttons:
* :fa-power-off: to disconnect from your Windows session
* :fa-home: to redirect you to the main portal while keeping your VDI session open in the background

If you tick the "Logoff after closing VDI" box, the :fa-home: button will not be available anymore. Users will only have the possibility to disconnect from the Windows session everytime they close the VDI.
[block:callout]
{
  "type": "success",
  "title": "Your logoff configuration changes have successfully been taken into account!"
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Computation credits"
}
[/block]
You can set usage limits for the users, for example to be able to set trial periods or to limit resources consumption.

How computation credits work on Nanocloud is easy: the users will not be able to exceed a number of computation credits per month. When the threshold is reached, the user cannot launch an application anymore, until the end of the month.

You just have to enter your chosen amount of credits limits in the provided area, and it will apply to all users.
[block:callout]
{
  "type": "info",
  "title": "Computation credits only apply to users who use AWS."
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Enable teams"
}
[/block]
For any member to be able to create teams, you just have to tick or untick **Enable team**.