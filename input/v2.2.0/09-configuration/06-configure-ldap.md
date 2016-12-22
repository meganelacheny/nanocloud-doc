---
title: "Configure LDAP"
excerpt: ""
---
[block:callout]
{
  "type": "danger",
  "title": "This feature is only available for administrators!"
}
[/block]
In the **LDAP** tab, you can activate users authentication against LDAP. In other words, if you activate this option, users will not have to register one by one: if they are identified in their company's Active Directory, they will automatically have access to Nanocloud.

To activate this option:
1. Tick the **Activate authentication against LDAP** box.
2. Enter the LDAP URL.
3. Enter the base DN.
4. (optional) Select a default group for LDAP users.
[block:callout]
{
  "type": "info",
  "title": "LDAP users information",
  "body": "Please note that for LDAP users, their personal information displayed in Nanocloud are read-only. The administrator nor the user can modify these information, because they are in the Active Directory of the company, not saved in Nanocloud."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/05c071b-configuration_LDAP_220.png",
        "configuration_LDAP_220.png",
        1278,
        677,
        "#e0e5e7"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "Great job! You have activated the LDAP option!"
}
[/block]