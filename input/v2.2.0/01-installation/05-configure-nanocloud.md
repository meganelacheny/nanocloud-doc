---
title: "Configure Nanocloud"
excerpt: "The fourth part of the installation of Nanocloud displays the different variables that you may need to configure Nanocloud. It is mandatory."
---
[block:callout]
{
  "type": "success",
  "body": "At this point, you should have:\n1. Followed the prerequisites.\n2. Followed the steps of the first part of the installation.\n3. (optional) Configured the storages.\n4. (optional) Configured Nanocloud to support 15+ users.\n\nYou can now follow the steps below to configure Nanocloud!"
}
[/block]
Edit the file config.env, which you will find in the Nanocloud directory. All the variables to configure are listed and explained down below.
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
## RDP/Guacamole options

For more information about RDP/Guacamole options, please [check their own documentation](http://guacamole.incubator.apache.org/doc/gug/configuring-guacamole.html#rdp).
[block:code]
{
  "codes": [
    {
      "code": "RDP_SECURITY=nla # Nanocloud defaults to \"nla\"\nRDP_IGNORE_CERT=true # Nanocloud defaults to \"true\"\nRDP_WIDTH=0 # Nanocloud defaults to 0 (automatic)\nRDP_HEIGHT=0 # Nanocloud defaults to 0 (automatic)\nRDP_DPI=0 # Nanocloud defaults to 0 (automatic)\nRDP_ENABLE_PRINTING=true # Nanocloud defaults to \"true\"\nRDP_PRECONNECTION_ID=0 # Nanocloud defaults to 0 (desactivated)\nRDP_ENABLE_WALLPAPER=true # Nanocloud defaults to \"true\"\nRDP_ENABLE_FONT_SMOOTHING=true # Nanocloud defaults to \"true\"",
      "language": "shell"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "Great job! You have successfully configured Nanocloud!",
  "body": "Now, [click here to complete the installation](doc:complete-the-installation)!"
}
[/block]