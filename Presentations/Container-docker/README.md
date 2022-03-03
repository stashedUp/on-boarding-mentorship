<img src="../readme_files/docker-vm-container.png" width="440"/>   
READ : https://www.backblaze.com/blog/vm-vs-containers/   

Basic Definitions — VMs and Containers
What are VMs?
A virtual machine (VM) is an emulation of a computer system. Put simply, it makes it possible to run what appear to be many separate computers on hardware that is actually one computer.

The operating systems (OS) and their applications share hardware resources from a single host server, or from a pool of host servers. Each VM requires its own underlying OS, and the hardware is virtualized. A hypervisor, or a virtual machine monitor, is software, firmware, or hardware that creates and runs VMs. It sits between the hardware and the virtual machine and is necessary to virtualize the server.


With containers, instead of virtualizing the underlying computer like a virtual machine (VM), just the OS is virtualized.

Containers sit on top of a physical server and its host OS — typically Linux or Windows. Each container shares the host OS kernel and, usually, the binaries and libraries, too. Shared components are read-only. Sharing OS resources such as libraries significantly reduces the need to reproduce the operating system code, and means that a server can run multiple workloads with a single operating system installation. Containers are thus exceptionally light — they are only megabytes in size and take just seconds to start. Compared to containers, VMs take minutes to run and are an order of magnitude larger than an equivalent container.   


   
