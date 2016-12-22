---
title: "Configure sessions"
excerpt: ""
---
[block:callout]
{
  "type": "danger",
  "title": "This feature is only available for administrators!"
}
[/block]
In the **Session** tab, you can configure:
 * after how long the session must expire
 * the default machine pool size
 * the default machine size
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/52b0008-configuration_sessions_220.png",
        "configuration_sessions_220.png",
        1264,
        758,
        "#146cb3"
      ]
    }
  ]
}
[/block]
For each of these settings:

1. Edit by simply replacing the information by the new setting.
2. Click :fa-check: to validate your changes.

As for the default machine size, you just have to tick the size of your choice, between Small, Medium, Large and Very large. Your changes are automatically taken into account. 
[block:callout]
{
  "type": "info",
  "title": "Pool size and machine size",
  "body": "Note that in the Session configuration area, you choose the default pool size and machine size, which means that the values will apply by default to every new machine per image.\nHowever, you can change these values for one particular image, [as it is explained in this section of the documentation](doc:manage-an-image)."
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "You successfully changed session configurations!"
}
[/block]