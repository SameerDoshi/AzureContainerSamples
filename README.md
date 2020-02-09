# AzureContainerSamples

Containes samples of differnt hosting methods for Containers

So you've decided to host your app as a container?  Do you need to host as a container?  If you're running Java, Python, dotnet, PHP, PowerShell, or Javascript you might want ot host using [App Service for WebApps](https://docs.microsoft.com/en-us/azure/app-service/)- and bypass needing to build a container.  

Assuming you / your org wants to host on containers- no problem- there are plenty of options- many of which won't require you to manage a VM.   
Below are the options with samples on the current (as of 2/10/20) options.

* ## App Service for Containers [Sample TODO]()
     - Host internally or externally facing apps!  
     - Microsoft manages: OS, load balancing, scale up/out (based on config), SSL, domain name, CDN, DR/backup (based on configuration), logging, debugging, vertical stacking, balancing AppService Plans on shared infrastructure
     - You manage: how code is deployed (git, SFTP, folder, etc)
     - Cost: you pay based on size (CPU, memory, disk) and instances of the AppService plan you select
     - Limitations: you cannot manage inbound/outbound ports (inbound is limited to 80/443 (you can disable 80), all incoming traffic must be HTTP/S
* ## (ASE) App Service Environment for Containers [Sample TODO]()
     - Host internally or externally facing apps!  
     - Microsoft manages: OS, load balancing, scale up/out (based on config), SSL, domain name, CDN, DR/backup (based on configuration), logging, debugging, vertical stacking
     - You manage: how code is deployed (git, SFTP, folder, etc), balancing AppService Plans on shared infrastructure, network security (in/out)
     - Cost: you pay for the entire ASE and all App Service Plans hosted on it.
     - Limitations: all incoming traffic must be HTTP/S
* ## (ACI) Azure Container Instances [Sample](https://github.com/SameerDoshi/AzureContainerSamples/tree/master/AzureContainerInstance)
     - Host internally or externally facing apps!   
     - Microsoft manages: OS, load balancing, domain name, logging 
     - You manage: container registry providing images, ports, SSL, networking configuration
     - Cost: you pay for the allocated CPU/mem/disk and instances (container count) you've requested
     - Limitations: anything you can run in a container can run on ACI.
* ## (AKS) Azure Kubernetes Service [Sample TODO]()
     - Host internally or externally facing apps!   
     - Microsoft manages: placement of nodes on shared infrastructure, K8S management node, spin up/down of nodes, allocation of public IPs
     - You manage: nodes' OSes, VM sizes, DR, backup, SSL, CDN, storage, networking rules and security
     - Cost: you pay for the infrastructure allocated (nodes, networking, etc)
     - Limitations: anything you can run in Kubernetes can be run here.  
* ## IaaS [Sample TODO]()
     - Host internally or externally facing apps!   
     - Microsoft manages: placement of VM on shared infrastructure 
     - You manage: VMs, container registry providing images, ports, SSL, networking configuration
     - Cost: you pay for the allocated CPU/mem/disk and instances (container count) you've requested
     - Limitations: anything you can run in a container can run on ACI.

Note: This code is provided as-is without warranty and is not supported.  This is meant as samles only. Do not use this code in production.