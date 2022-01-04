### How people used to dual or multi-boot many OS before the Virtualization Technology was available?
 - Boot Loaders Utlities
    1. LILO ( Linux Loader ) - Open source
    2. GRUB - open source
 - Boot loaders are installed in Sector 0, byte 0 (MBR - Master Boot Record) of your Hard Drive
 - When your system boots, CPU learns from BIOS that it has to load the utility present in MBR
 - Eventually CPU starts running the Boot Loaders installed in MBR
 - Boot Loader then detects if there is any OS installed on your system, it is possible you may multiple OS
 - Boot Loader then gives a menu for you to choose between the OS installed on your system
 - This way, only one OS can be booted at a time

### What is Hypervisor?
 - general term used to refer the Virtualization Technology
 - heavy-weight technology
      each virtual machine (VM) requires dedicated CPU Core, RAM and storage
 - Hypervisor allows you to run multiple OS simultaneously side by side in the same system
 - it is combination of Hardware + Software technology
 - Processor
     AMD 
       - processors that support Virtualization it has AMD-V feature enabled
     Intel
       - processors that support Virtualization it has VT-X feature enabled
  - Hypervisor are of 2 types
      Type 1 - meant for Servers/Workstations ( Bare Metal Hypervisors )
      Type 2 - meant for laptops/Desktops/Workstations
  - Examples
      VMWare 
          - Fusion (Mac) - Type 2
          - Workstation (Windows/Linux/Mac) - Type 2
          - vSphere - Type 1
      Parallels(Mac) - Type 2
      Microsoft
          - Hyper-V - Type 2
      Oracle
          - VirtualBox - Type 2
     
     Datacenter
        - a collection of many many servers ( 1,00,000 Servers put together is called as 1 Datacenter )
     
     Requirement
     I need 1,00,000 RHEL OS running simultaneously
     
     Without Virtualization Technology
      - How many servers you need to deploy 1,00,000 RHEL OS?
         - We need 1,00,000 physical servers to support 1,00,000 RHEL OS simultaneously
           
     With Virtualization Technology
      - How many servers you need to deploy 1,00,000 RHEL OS?
         - Processor with 1024 cores 
  
     
     CRM
      - Oracle DB Server ( Hyderabad - BOA )
      - Apache Kafka ( Message Queue, Streaming ) - (Hyderabad - BOA )
      - Weblogic App Server - ( US - BOA)
      - Nginx Load Balancer - ( Singapore - BOA )
      - Email Server - ( Bangalore - BOA )
   
 Containers - Application virtualization
   - typically one application runs per container
   - container are not Operating System
   - container looks in many ways like an OS but technically they are just application process
   - containers has their shell just like OS has their shells(command prompt, ksh, bash, sh, etc .,)
   - containers has dedicated network stack ( 7 OSI Layers )
   - containers get their IP Address
   - light-weight technolgy
       - all the containers running in a system share the CPU, RAM and storage just like regular application process.
   - even in laptop with Dual cores with 8 GB RAM, you can easily run 50~100 containers

### Listing Docker Images in the Local Docker Registry
```
docker images
```

### Downloading a docker image from Docker Hub(Remote Registry) to Local Docker Registry
```
docker pull hello-world:latest
```

### Creating a container
```
docker run hello-world:latest
```
The expected output is
<pre>
[jegan@tektutor ~]$ <b>docker run hello-world:latest</b>

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
</pre>

### Listing the running containers
```
docker ps
```

### Listing all containers
```
docker ps -a
```