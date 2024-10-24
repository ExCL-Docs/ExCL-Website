---
title: ExCL October Meeting 2024
toc: false
toc_sticky: false
categories: [ExCL]
tags: [User Meetings]
header:
    image: /assets/images/circuit.jpg
    teaser: /assets/images/october-meeting-2024-splash.jpg
---

October 2024 ExCL meeting slides.

<object data='{% link /assets/presentations/2024-10-october-excl-meeting.pdf %}' type='application/pdf' width='560' height='700'><p>It appears that you don't have a PDF plugin for this browser. You can <a href='{% link /assets/presentations/2024-10-october-excl-meeting.pdf %}'>click here to download the PDF file.</a></p></object>

Below is largely LLM-generated summary of the meeting based on the presentation slides.

----

## October 2024 Monthly Meeting Highlights: Experimental Computing Laboratory

Welcome to our October 2024 update! In this post, we'll cover the key topics from the recent Experimental Computing Laboratory meeting. From system updates to deployment plans, here’s everything you need to know about our recent strides in computing infrastructure and technology.

### **System and Infrastructure Updates**

1. **Ubuntu 24.04 Rollout**: The new Ubuntu 24.04 has been announced but is pending approval for ORNL use. Until then, we are holding off on installations or upgrades due to stability concerns.
2. **Migration Progress**: Nearly all user-facing systems have been transitioned to Ubuntu 22.04. We have one remaining CentOS 7 system and a new Rocky 9 system built for testing in that environment.
3. **Control Groups Version**: All rebuilt systems now support cgroups v2. Users needing v1 should contact the ExCL staff for configuration help. This change was done as part of the upgraded slurm deployment.

### **Three-Month Outlook**

- **Documentation Improvements**: Continuation of updates to system use and assignment documentation on our [documentation site](https://docs.excl.ornl.gov).
- **UID & GID Stabilization**: We're stabilizing UID & GID assignments across ExCL to facilitate service deployment and integration.
- **Deployment of Mi300a Systems**: A new Mi300a system with integrated GPUs is awaiting deployment in the 5100 data center to support a heterogeneous accelerator environment.

### **Mi300a Specifications**

The Mi300a system features:
- 4x Mi300A system APUs (integrated CPUs and GPUs)
- 128 GB HBM3 memory per APU
- Infinity Fabric Links and PCIe 5.0x16 slots for peripherals
- [More about Mi300a](https://www.amd.com/en/products/accelerators/instinct/mi300/mi300a.html)

## SSH Keys for Authentication

Using SSH keys is now the preferred method for user authentication and connecting with private Git repositories. We recommend using SSH keys with a passphrase for added security. This approach helps avoid potential account lockouts caused by automatic login tools, which can exceed retry limits when using cached passwords.

### **Proposed Host Layout Changes**

- **Milan0 GPU Reconfiguration**: A proposal to reconfigure Milan0 with two AMD M100 GPUs and deploy additional accelerators to create a more diverse and efficient computing environment.

## IRIS Setup Scripts

We now have setup scripts available for configuring ExCL systems for IRIS accelerator use. These scripts can be found at `/auto/software/iris` and used by sourcing `setup_system.source`. To request changes, users can fork the repository and create a merge request, which will be reviewed and then deployed.

### **Host Quarantine and Compliance**

- **Compliance Updates**: Updates on ITSD compliance enforcement and the status of ExCL systems under the DOE-mandated host quarantine policy.

### **Container Registry Transition**

- **From GitLab to Harbor**: The container registry has been moved from GitLab to Harbor, enhancing our capabilities in managing containers more effectively. Training and documentation for Harbor are available online.

## Discussions and Questions

- **IRIS Container**: There were discussions regarding the feasibility of using Harbor for IRIS containers. Though IRIS does not currently have a container, it is feasible for future use.
- **HiFive in ExCL**: Ongoing discussions about integrating HiFive into our infrastructure, pending approval.

----

We hope this summary provides a helpful overview of our October meeting. For any further questions or comments, feel free to reach out to the ExCL team. Stay tuned for our monthly newsletter and future updates!

*Keep exploring, keep computing!*