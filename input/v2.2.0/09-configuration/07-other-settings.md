---
title: "Other settings"
excerpt: ""
---
[block:callout]
{
  "type": "danger",
  "title": "This feature is only available for administrators!"
}
[/block]
In the **Other settings** tab, you can:
 * configure the host
 * change the machines name

For each of these settings:
1. Edit by simply replacing the information by the new setting.
2. Click :fa-check: to validate your changes.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2ff30e-configuration_othersettings_220.png",
        "configuration_othersettings_220.png",
        1276,
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
  "title": "Photon"
}
[/block]
You can also activate Photon, which is a high performance remote application streaming engine.
This feature is still experimental and has a few limitations for its users:
 * It is only available for users of Nanocloud on AWS.
 * You cannot use the Clipboard for copy and paste in the VDI.
 * You cannot print anything via the VDI.
 * There is no auto-scaling when you resize the window while using the VDI.
Also, note that for now, Photon is less performant when it comes to latency, however, it offers better performances for applications requiring a lot of reactivity and resources.

To activate Photon, simple tick **Activate Photon**.
[block:callout]
{
  "type": "success",
  "title": "Good job! You have configured the host and the machines name!",
  "body": "You might even be one of the first Photon users: thank you for supporting this new feature!"
}
[/block]