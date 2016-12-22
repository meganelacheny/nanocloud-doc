---
title: "Configuration for 15+ users"
excerpt: "The third part of the installation guides you to prepare Nanocloud to support 15+ users. It is only mandatory for those who need to install Nanocloud for 15+ users."
---
[block:callout]
{
  "type": "success",
  "title": "",
  "body": "At this point, you should have:\n1. Followed the prerequisites.\n2. Followed the steps of the first part of the installation.\n3. (optional) Configured the storages.\n\nYou can now follow the steps below to configure Nanocloud in order to enable it to support 15+ users!"
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "The procedure below is optional.",
  "body": "Obviously, if less than 15 users will use Nanocloud, you can skip this procedure and directly go to the next step, which is mandatory: [configure Nanocloud](doc:configure-nanocloud)."
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Launching of the Video Engine Server container"
}
[/block]
Use the following command to launch the Video Engine Server:
[block:code]
{
  "codes": [
    {
      "code": "docker-compose -f docker-compose-dev.yml up -d guacd",
      "language": "shell"
    }
  ]
}
[/block]
The listening port will be 4822. To verify that the Video Engine Server container is listening on port 4822, use the following command:
[block:code]
{
  "codes": [
    {
      "code": "netstat -aptn",
      "language": "shell"
    }
  ]
}
[/block]
Repeat these steps each time you create a new VM dedicated to Video Engine Server. Keep in mind that each new VM can support approximately 15 users. Therefore, you must follow the procedure above each time you want Nanocloud to be able to support approximately 15 more users.
[block:api-header]
{
  "type": "basic",
  "title": "Creation of the Load Balancer on AWS"
}
[/block]
For Nanocloud to be able to communicate with all your VMs, you need to create a load balancer on AWS.

1. In the AWS website, select **Services > EC2**.
2. In the **Load Balancing** section, click on **Load Balancer**.
3. Click on the "Create load balancer" button.
4. Choose to create a "Classic Load Balancer". Go to the next step.
5. Fill in the fields to create your load balancer:
- enter a name of your choice
- choose a VPC
- select the option "Create an internal load balancer"
- in the table, enter the value of the correct port, which is "4822"
Go the next step.
6. Add a security group. Go to the next step.
7. To configure the health check, you just have to leave all the default values. Go to the next step.
8. Add the EC2 instances, for the load balancer to communicate with the right VMs. Go to the next step.
9. Add tags, which means that you can choose a name for your load balancer.

To verify that the creation of the load balancer was successful:
1. In AWS, select **Load Balancer > Instance**.
2. Check that the status indicates "InService". If that is what is written, the creation of the load balancer was successful.
[block:callout]
{
  "type": "success",
  "title": "Great job! You have successfully configured Nanocloud for it to support 15+ users!",
  "body": "Now, [click here to go to the next step, which is mandatory: configure Nanocloud](doc:configure-nanocloud)!"
}
[/block]