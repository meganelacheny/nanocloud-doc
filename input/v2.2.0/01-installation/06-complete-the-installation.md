---
title: "Complete the installation"
excerpt: "The fifth and last part guides you to complete the installation of Nanocloud. Its is mandatory."
---
[block:callout]
{
  "type": "success",
  "title": "",
  "body": "At this point, you should have:\n1. Followed the prerequisites.\n2. Followed the steps of the first part of the installation.\n3. (optional) Configured the storages.\n4. (optional) Configured Nanocloud to support 15+ users.\n5. Configured Nanocloud.\n\nYou can now follow the steps below to complete the installation!"
}
[/block]
1. Use the following command to build the container:
[block:code]
{
  "codes": [
    {
      "code": "docker-compose build",
      "language": "shell"
    }
  ]
}
[/block]
2. Use the following command for the container to be up:
[block:code]
{
  "codes": [
    {
      "code": "docker-compose up -d",
      "language": "shell"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "Great job! You have successfully installed Nanocloud!"
}
[/block]