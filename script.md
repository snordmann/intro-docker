# Introduction to Containers and Docker for NodeJS applications

## Introduction

Text goes here

## What are Linux Containers

Analogy: shipping containers

### A quick history

- chroot (1979)
  - Restricting file access
- FreeBSD Jails (2000)
  - Partition FreeBSD systems into smaller systems
- Process Containers and LXC (2006 & 2008)
  - namespaces and cgroups
- Docker (2013)
  - Adding container management capabilities
- OCI (2015)
  - Standardization

### How do they work

- VM vs Containers
- cgroups and namespaces

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
