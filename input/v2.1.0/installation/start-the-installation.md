---
title: "Start the installation"
excerpt: "The first part of the installation guides you from the downloading of Nanocloud's sources, to the choice of the version. It is mandatory."
---
1. Download Nanocloud's sources with the following command.
[block:code]
{
  "codes": [
    {
      "code": "git clone https://github.com/Nanocloud/nanocloud.git",
      "language": "shell"
    }
  ]
}
[/block]
2. Go into the nanocloud folder.
3. Use the following command to obtain the list of all available versions:
[block:code]
{
  "codes": [
    {
      "code": "git tag",
      "language": "shell"
    }
  ]
}
[/block]
4. Use the following command to choose the version you want:
[block:code]
{
  "codes": [
    {
      "code": "git checkout <Nanocloud version>",
      "language": "shell"
    }
  ]
}
[/block]
If you want, you can use the following command to verify the version that you have chosen.
[block:code]
{
  "codes": [
    {
      "code": "git status",
      "language": "shell",
      "name": null
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "Great job!",
  "body": "Now, you can [continue the installation by configuring user and team storage](doc:optional-storage-configurations) if you need to. If you do not, and in the case of an installation for 15+ users, [follow the procedure of this page](doc:configuration-for-15-users). If you do not either, directly [go to the next mandatory step of the installation, which is to configure Nanocloud](doc:configure-nanocloud)."
}
[/block]