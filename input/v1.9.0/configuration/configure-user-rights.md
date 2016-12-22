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
As for user rights configuration, you can:
* decide whether the user can register himself or not, and select a default group
* decide whether you automatically logoff after closing the VDI or not
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/vLJlOqhuSSmVs9E59nsT_configuration-userrights.png",
        "configuration-userrights.png",
        "2542",
        "1366",
        "#046cb4",
        ""
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Registration and default group"
}
[/block]
In the **User rights** section of the Configuration tab, tick or untick the box next to "User can register himself" to decided if users can register themselves.

If users can register themselves, you can choose a default group. All new users who registered themselves will then automatically join the default group.

To do so:
1. Click on the name of the group to make it the default one.
2. Click on the **Save** button.
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
  "type": "warning",
  "title": "Do not forget to click on the Save button for your changes to be taken into account."
}
[/block]