=====================
Ansible roles to rollout Container Environment on Windows 2019 hosting
=====================

.. meta::
   :keywords: IaaS platform, Window 2019, Hyper-V, Ansible Tower, Docker, Docker Swarm, Ansible, Consul, Registrator
   :description lang=en: This is a set of scripts to quickly build aka private cloud hosting.

This is a set of scripts to quickly build aka private cloud hosting.

.. contents:: Table of Contents

Part 0: Prerequisites and Virtualization
Part 1: Ansible, Docker, Docker Swarm
Part 2: Service Discovery
Part 3: Consul, Registrator, Consul-Template

Introduction
============

To run scripts used `Ansible <http://www.ansible.com>`_.
-Customization for Ansible Tower /AWX
-Customization for Windows 2019
-Customization for Hyper-V


Before you start...
Because Microsoft & Docker Inc. developed a native Docker implementation on Windows using Hyper-V (or even a thinner layer) which let´s you run tiny little Windows containers inside your Windows box, which are accessible through the Docker API.

Before we start: The most important point here is to start with a correct Build Number of Windows 10 (1607, Anniversary Update)/Windows Server 2016. It took me days to figure that out, but it won´t work with for example 10.0.14393.67 - but will with 10.0.14393.206! I ran over the advice on this howto to fast, because I thought "Windows 10 Anniversary should be enough, don´t bother me with build numbers". But take care! The final docker run won´t work (but all the other steps before, which made it so hard to understand)... Here are two examples of the output of a (Get-ItemProperty -Path c:\windows\system32\hal.dll).VersionInfo.FileVersion on a Powershell:
