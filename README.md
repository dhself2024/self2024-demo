# Southeast LinuxFest 2024 - Beyond tcpdump - using osquery and eBPF for Linux Security Analytics

## Overview
The objective of this project is to provide the infrastructure-as-code necessary to build and manage an osquery+eBPF test environment. The environment consists of a build server for the eBPF tools and plugins, an Osquery FleetDM management server to collect data, manage the Osquery agents, and perform searches from a centralized location, and an Ansible AWX automation controller. There are other choices for ansible like Semaphone or just running on the commandline, but here we use AWX because it is the upstream open source version of Ansible Tower or Automation Platform you'll find in many production environments.

## Test Environment
The test environment can be built using any virtualization or cloud platform. At the time this repository was created, Ubuntu 24.04 was used for all VMs. Other options are Arch Linux, Fedora, or Rocky Linux. Use whatever you are comfortable with, but you will need the ability to create at least 4 VMs. Both the eBPF build server and Ansible AWX VM servers will need at least 2 CPUs with 4 GB of RAM and 50GB of disk space. The Osquery FleetDM VM should have at least 2 CPUs, 4GB of RAM and 100GB disk space.

## Networking
A good way to isolate the test environment, control access and provide unrestricted access between the systems is to tie everything together with a mesh VPN like Tailscale. An email address will be required to sign up for the free Tailscale tier while something like GitHub can act as the identity provider (IdP) for the whole environment. Please be sure to set up GitHub with MFA because it's good security practice.

## Ansible AWX Controller
Ansible AWX controller can be set up several ways. The options are to use containers or set up with the native OS packages. A tutorial is provided here to get the install going with native packages on the default Ubuntu 24.04 VM. Additional instructions will be provided showing how to create a project in AWX and connect that project to the GitHub repository for access to the Ansible automation code.

## Osquery FleetDM
Osquery FleetDM can also be set up using containers or native packages. A tutorial is provided here to get the install going with native packages on the default Ubuntu 24.04 VM. Additional instructions will be provided showing how to use Ansible AWX controller for deployment of the agents as well as configuration management.

## eBPF build server
TODO
