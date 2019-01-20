# Introduction to Containers and Docker for NodeJS applications

## Introduction

Text goes here

- Only about linux

### How are they different to virtual machines

Containers are a type of OS-level virtualization. That means that eveything
above the operating system is virtualized as opposed to virtual machine where
every system resource - like CPU, memory and network - is virtualized.

![VM vs
Container](https://blog.netapp.com/wp-content/uploads/2016/03/Screen-Shot-2018-03-20-at-9.24.09-AM-935x500.png)

Containers invoke the hosts kernel directly. Making them faster to run (no
privilege-escalation) and faster to start (no guest OS).

## What are Linux Containers exactly

Analogy: shipping containers

The idea of separating applications on a single host has been around for quite
some time. In 1979 chroot could limit file system access and FreeBSD Jails could
provide multiple indepentend mini-systems, so called "jails" as early as 2000.

However a major leap came from a google project in 2006 as they open sourced
their "Process Containers" (later changed to "control groups", abbreviated as
"cgroups"). They have four main goals:

- Resource limiting
- Prioritization
- Accounting
- Control

Since 2008 we have Linux Containers (LXC), that combine cgroups and namespacing
to completely isolate applications.

Docker has started to build its software on top of LXC in 2013 but changed to
its own virtualization engine (libcontainer) one year later, but still relying
on linux kernel features like cgroups and namespacing.

In 2015 Docker established the Open Container Initiative (short: OCI) to
standardize the runtime and image specifications. Nowadays there a several OCI-
based container runtimes like containerd, cri-o, frakti, rkt , ... and of
course: docker.

### Advantages and disadvantages

- Pro
  - Small (10s of MB instead of GB)
  - Resource-friendy (running same kernel)
  - Fast to boot (can react to user demand, cost effective)
  - Reproducable environment (finding bugs, testing)
  - Easy to manage
- Con
  - Security (Shared kernel, if kernel compromised all containers are too)
  - Less operating systems (VMs can run any OS)
  - Networking (secure and easy compromise)
  - Ecosystem fractured
  - Data persistence (all data lost when container stopped)

## What is Docker

- CE vs. EE
- Image formats
  - Dockerfile
    - Layering
- Runtime formats
  - docker-compose.yml
