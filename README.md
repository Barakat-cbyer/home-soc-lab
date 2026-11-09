# Home SOC Lab

## Overview

I built this Home SOC lab to have my own environment where I can practice monitoring endpoints, reviewing alerts, and carrying out security investigations.

For the setup, I used Hyper-V to run Ubuntu Server and installed Wazuh as the main security monitoring platform. My Windows 11 system is connected to Wazuh as the monitored endpoint.

## Lab Setup

- Windows 11 Pro
- Microsoft Hyper-V
- Ubuntu Server 24.04 LTS
- Wazuh 4.14.10
- 4 vCPU
- 7 GB RAM
- 60 GB virtual disk
- Windows Wazuh Agent

## Architecture

```text
Windows 11 Endpoint
        |
    Wazuh Agent
        |
        v
Ubuntu Server VM
        |
      Wazuh
        |
        v
Monitoring & Investigation
```

## What I Did

I created an Ubuntu Server VM in Hyper-V and configured it as my SOC server. I also expanded the Ubuntu storage and set up SSH access so I could manage the server remotely.

I then installed Wazuh, including the manager, indexer, and dashboard.

My first installation got stuck while starting the Wazuh indexer. The VM was initially using 6 GB RAM. I tried increasing it to 8 GB, but my system could not allocate that much memory, so I changed it to 7 GB.

After making the change, I ran the Wazuh installation again and it completed successfully.

I then installed the Wazuh agent on my Windows 11 system and connected it to the server.

The endpoint now appears as **Active** in the Wazuh dashboard.

## Current Status

The Home SOC environment is working successfully.

```text
Windows Endpoint → Wazuh Agent → Wazuh Server → Wazuh Dashboard
```

I now have my own working environment for security monitoring and hands-on SOC investigations.
