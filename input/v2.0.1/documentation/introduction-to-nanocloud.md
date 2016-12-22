---
title: "Introduction to Nanocloud"
excerpt: "This page gives insights on how the Nanocloud Platform is architectured: which kind of computing resources is need, which systems are used etc."
---
Nanocloud Software platform is based on a multi-components architecture. 

The core part is a set of containers (based on Docker technology) hosted in a Linux system which can be a bare-metal server or a virtual machine (VM). Each container is in charge of a Nanocloud Software module. These modules are a backend with a REST API, a database, an HTML5 frontend, and a HTTP/HTTPS web proxy.

Administrator and users can access to this platform through its web interface. Nanocloud Software is then also a gateway between the user's network (Internet, Enterprise Intranet, VPN) and the application used.

Any application transformed in a service available in a browser is hosted in another part of the architecture: one or a set of several Windows Server virtual machine(s), depending on the number of users and of the application type. This application server does not need to be connected to a public network, thanks to the Nanocloud platform which is in charge of the service exposure. Depending on the user needs, Nanocloud platform may also provide an access to a complete Virtual Desktop Interface (VDI).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/52f4d0b-architecture_nanocloud_2.png",
        "architecture_nanocloud_2.png",
        1528,
        840,
        "#dce4ef"
      ]
    }
  ]
}
[/block]
The needed resources can be provisioned from a private cloud (based on Openstack) or from Amazon Web services (AWS).

Indeed, Nanocloud Software platform must be understood as a PaaS. It helps you to abstract the IaaS layer. Then, you don’t need any particular skill at the infrastructure low layer since Nanocloud is compatible with any available technology from private clouds or from public clouds.