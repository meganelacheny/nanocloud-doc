---
title: "Optional storage configurations"
excerpt: "The second part of the installation is optional. It allows you to configure user storage and team storage."
---
[block:callout]
{
  "type": "success",
  "title": "",
  "body": "At this point, you should have:\n1. Followed the prerequisites.\n2. Followed the steps of the first part of the installation.\n\nYou can now follow the steps below to configure user and/or team storages in Nanocloud!"
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "User storage"
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "The procedure below is optional.",
  "body": "You need to figure out whether you need and want to create another VM.\nYou can use the original VM for the User Storage or you can create another VM dedicated to User Storage only.\nIf you do not need or want to create another VM, simply skip this procedure."
}
[/block]
If you need or want to create another VM, dedicated to User Storage only:

1. Create a new machine.
[block:callout]
{
  "type": "info",
  "title": "Reminder: how to create a new machine",
  "body": "1. Provision your machine.\n2. Follow the steps of [Prerequisites](doc:prerequisites).\n3. Clone Nanocloud's repository."
}
[/block]
2. Use the commands below:
[block:code]
{
  "codes": [
    {
      "code": "docker-compose build plaza && docker-compose up -d plaza\ndocker-compose up -d storage",
      "language": "shell"
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Team storage"
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "Team Storage and User Storage must be in two different machines.",
  "body": "If you have already created a new machine and dedicated it to User Storage, please keep in mind that you cannot use that same machine for Team Storage. They must be in two separate machines."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "The procedure below is optional",
  "body": "You need to figure out whether you want to enable the creation of teams or not.\nIf you enable the creation of teams, you will need to create another VM entirely dedicated to Team Storage.\nIf you do not want to enable the creation of teams, simply skip this procedure."
}
[/block]
To enable the creation of teams, by creating another VM dedicated to Teams Storage:

1. Create a new machine.
[block:callout]
{
  "type": "info",
  "body": "1. Provision your machine.\n2. Follow the steps of [Prerequisites](doc:prerequisites).\n3. Clone Nanocloud's repository",
  "title": "Reminder: how to create a new machine"
}
[/block]
2. Use the commands below:
[block:code]
{
  "codes": [
    {
      "code": "docker-compose -f docker-compose-extra.yml build && docker-compose -f docker-compose-extra.yml up -d plaza \ndocker-compose -f docker-compose-extra.yml up -d storage-team",
      "language": "shell"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "Great job! You have successfully configured User and Team Storage in Nanocloud!",
  "body": "Now, continue the installation. If you install Nanocloud for more than 15 users, [click here](doc:configuration-for-15-users). If you do not, directly go to the step after that, which is mandatory, to [configure Nanocloud](doc:configure-nanocloud)."
}
[/block]