# Introduction to Containers and Docker for NodeJS applications

## Introduction

Text goes here

- Only about linux

## What are Linux Containers

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

### How are they different to virtual machines

- VM vs Containers

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
