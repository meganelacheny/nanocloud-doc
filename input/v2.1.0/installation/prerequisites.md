---
title: "Prerequisites"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "title": "We highly recommend you to use Ubuntu 16.04 or Debian 8 to install Nanocloud.",
  "body": ""
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "The commands in all the procedures of all the installation are only valid for Ubuntu and Debian!",
  "body": ""
}
[/block]
Down below are listed the prerequisites for a successful installation of Nanocloud.

- You need a Linux server, no matter the distribution, although we highly recommend Ubuntu or Debian.
- Login through ssh on the Linux machine.
- Install vim, git and curl with the following command:
[block:code]
{
  "codes": [
    {
      "code": "sudo apt-get update\nsudo apt-get install -y vim git curl",
      "language": "shell"
    }
  ]
}
[/block]
- Install Docker Compose 1.8.0 with the following commands:
[block:code]
{
  "codes": [
    {
      "code": "curl -fsSL https://get.docker.com/ | sudo sh\ncurl -L https://github.com/docker/compose/releases/download/1.8.0/docker-compose-$(uname -s)-$(uname -m) > docker-compose\nsudo cp docker-compose  /usr/local/bin/docker-compose\nsudo chmod +x /usr/local/bin/docker-compose",
      "language": "shell"
    }
  ]
}
[/block]
- Add the user to the Docker group, with the following command:
[block:code]
{
  "codes": [
    {
      "code": "sudo usermod -aG docker <username>",
      "language": "shell"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "body": "Otherwise, the group change will not be taken into account.",
  "title": "After this last step, you must log in again."
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "Congratulations! You are now ready to start the installation of Nanocloud!",
  "body": "[Click here to start the installation](doc:start-the-installation)."
}
[/block]