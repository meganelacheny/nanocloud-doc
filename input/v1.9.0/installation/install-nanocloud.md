---
title: "Install Nanocloud"
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
  "title": "The commands indicated in this page are only valid for Ubuntu and Debian!",
  "body": ""
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Prerequisites"
}
[/block]
Down below are listed the prerequisites for a successful installation of Nanocloud.

- You need a Linux server, no matter the distribution, although we highly recommend Ubuntu or Debian.
- Login through ssh on the Linux machine.
- Make sure Linux is updated with the following command:
[block:code]
{
  "codes": [
    {
      "code": "sudo apt-get update",
      "language": "shell"
    }
  ]
}
[/block]
- Install vim, git and curl with the following command:
[block:code]
{
  "codes": [
    {
      "code": "sudo apt-get install -y vim git curl",
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
- Add the user to the Docker host, with the following command:
[block:code]
{
  "codes": [
    {
      "code": "sudo usermod -aG docker <hostname>",
      "language": "shell"
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Installation procedure"
}
[/block]
1. Download Nanocloud's sources with the following command, and save them somewhere on your machine.
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
2. Go into the Nanocloud folder.
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
      "language": "text",
      "name": null
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "User Storage",
  "body": "Before you continue the installation, you need to figure out whether you need and want to create another VM.\n\nYou can use the original VM for the User Storage or you can create another VM dedicated to User Storage only. If you want to create this other VM, re-do all the prerequisites listed at the beginning of this page, and use the commands below."
}
[/block]

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
5. Edit the file config.env, which you will find in the Nanocloud directory. All the variables to configure are listed and explained down below.
[block:callout]
{
  "type": "danger",
  "title": "Comments in variables",
  "body": "Please note that the comments in the variables below are just here to explain you how each variable works. However, **your must delete every comment when configuring the file config.env**!"
}
[/block]
## Variables for the whole installation
[block:code]
{
  "codes": [
    {
      "code": "IAAS=aws # MANDATORY VARIABLE - Choose between \"manual\", \"aws\" and \"openstack\"\n\nHOST=localhost # MANDATORY VARIABLE (USED FOR SELF-REGISTRATION) - Defaults to localhost - Enter Nanocloud's IP or Nanocloud's domain name\n\nEXPIRATION_DATE=30 # Defaults to 0 (deactivated) - Choose the default number of days before user account expiration\n\nAUTO_REGISTER=true # Defaults to \"false\" - Choose if users can register themselves (\"true\") or not (\"false\") \nDEFAULT_GROUP=2b35335b-a71b-4f36-bf27-427f9f8caaef # Defaults to empty string (no default group) - This variable depends on the AUTO_REGISTER one - Enter the UID of the default group for self-registered users\n\nAUTO_LOGOFF=false # Defaults to \"false\" - Choose if you want VDI sessions to automatically sign off when the user leaves the VDI (\"true\") or not (\"false\")\n\nMACHINE_POOL_SIZE=5 # Defaults to 1 - Choose the number of machines to provision in advance for users \n\nMACHINES_NAME=Nanocloud Exec Server # Defaults to \"Nanocloud Exec Server\" - Choose a name for the machines\n\nPLAZA_URI=https://s3-eu-west-1.amazonaws.com/nanocloud/plaza/1.0.0/windows/amd64/plaza.exe # Defaults to https://s3-eu-west-1.amazonaws.com/nanocloud/plaza/1.0.0/windows/amd64/plaza.exe - Choose a URL to download plaza from\n\nPLAZA_PORT=9090 # Defaults to 9090 - Enter the port to communicate with plaza",
      "language": "shell"
    }
  ]
}
[/block]
## SMTP configuration
These variables are only relevant for two features: reset password and auto-registration.
[block:code]
{
  "codes": [
    {
      "code": "SMTP_SERVER_HOST=smtp.nanocloud.com # Choose a host to send emails - IP or domain name\n\nSMTP_SERVER_PORT=25 # Defaults to 25 - Enter the port for the SMTP server\n\nSMTP_LOGIN=Username # Enter the login for the SMTP server\n\nSMTP_PASSWORD=Password # Enter a password for the SMTP server\n\nSMTP_SEND_FROM=mail@nanocloud.com # Defaults to mail@nanocloud.com - Enter the email address of Nanocloud's sender",
      "language": "shell"
    }
  ]
}
[/block]
## Look and Feel
[block:code]
{
  "codes": [
    {
      "code": "TITLE=Nanocloud # Defaults to \"Nanocloud\" - Choose a page title\n\nFAV_ICON_PATH=favicon.ico # Defaults to favicon.ico - Enter a relative path from `assets/dist`\n\nLOGO_PATH=`/assets/images/logo.png` # Defaults to `/assets/images/logo.png` - Enter a relative path from `assets/dist` (a URL works)\n\nPRIMARY_COLOR=#A4DCD1 # Defaults to #006CB6 - Choose a primary color",
      "language": "shell"
    }
  ]
}
[/block]
## AWS Driver
These variables are for AWS users only.
[block:code]
{
  "codes": [
    {
      "code": "AWS_REGION=eu-central-1 # MANDATORY VARIABLE - Enter the name of the region where machines will spawn\n\nAWS_ACCESS_KEY_ID=AccessKeyID # MANDATORY VARIABLE - Enter the AWS key ID\n\nAWS_SECRET_ACCESS_KEY=SecretAccessKey # MANDATORY VARIABLE - Enter the AWS private key\n\nAWS_KEY_NAME=Nanocloud01 # MANDATORY VARIABLE - Enter the name of the private key\n\nAWS_PRIVATE_KEY=/opt/back/id_rsa # Defaults to \"/opt/back/id_rsa\" - Enter the path to where the key will be stored\n\nAWS_IMAGE=ami-09e61366 # Defaults to \"ami-09e61366\" - Enter Nanocloud's execution servers default image - Note that AMI ID depends on the region\n\nAWS_FLAVOR=t2.medium # Defaults to \"t2.medium\" - Enter the size of virtual machines\n\nAWS_MACHINE_USERNAME=Administrator # Defaults to \"Administrator\" - Choose the name of the administrator account on the machine\n\nCREDIT_LIMIT=10 # Defaults to empty string (no limit) - Set a credit limit to users (in dollars)",
      "language": "shell"
    }
  ]
}
[/block]
## OpenStack Driver
These variables are for OpenStack users only.
[block:code]
{
  "codes": [
    {
      "code": "OPENSTACK_USERNAME=Username # MANDATORY VARIABLE - Enter your username to connect to Openstack\n\nOPENSTACK_PASSWORD=Password # MANDATORY VARIABLE - Enter your password to connect to Openstack\n\nOPENSTACK_AUTH_URL=https://identity.example.com:5000 # MANDATORY VARIABLE - Enter the URL of the Openstack's API\n\nOPENSTACK_REGION=RegionOne  # MANDATORY VARIABLE - Enter the name of the region to use on Openstack\n\nOPENSTACK_IMAGE=47131599-4b29-493a-86a0-56848e6529ff # MANDATORY VARIABLE - Choose an image to boot Windows execution servers from\n\nOPENSTACK_FLAVOR=m1.medium # MANDATORY VARIABLE - Choose the flavor for the virtual machine\n\nOPENSTACK_MACHINE_USERNAME=Administrator # Defaults to \"Administrator\" - Enter the username of the Windows' account\n\nOPENSTACK_MACHINE_PASSWORD=Password # Defaults to empty, password will be generated - Enter the password of the Windows' account",
      "language": "shell"
    }
  ]
}
[/block]
## Storage configuration
[block:code]
{
  "codes": [
    {
      "code": "STORAGE_ADDRESS=localhost # MANDATORY VARIABLE - Defaults to \"localhost\" - Enter the storage service's IP (for user storage)\nSTORAGE_PORT=9090 # MANDATORY VARIABLE - Defaults to \"9090\" - Enter the storage service's port\nUPLOAD_LIMIT=500 # MANDATORY VARIABLE - Defaults to 0 (deactivate) - Choose an upload limit, in MB, for each user\n\nTEAM_STORAGE_ADDRESS=localhost # Default to \"localhost\" - Enter the IP address of the storage\nTEAM_STORAGE_PORT=9091 # Default to \"9091\" - Enter the port of the team storage\nTEAM_ENABLED=true # Default to \"false\" - Choose whether you want to enable the creation of teams (\"true\") or not (\"false\") ",
      "language": "shell"
    }
  ]
}
[/block]
6. Use the following command to build the container:
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
7. Use the following command for the container to be up:
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