---
title: ExCL October Meeting 2025
toc: false
toc_sticky: false
categories: [ExCL]
tags: [User Meetings]
excerpt_separator: <!--more-->
header:
    image: /assets/images/circuit.jpg
    teaser: /assets/images/2025-10-october-excl-meeting-splash.jpg
---

October 2025 ExCL meeting slides.

<!--more-->

<object data='{% link /assets/presentations/2025-10-october-excl-meeting.pdf %}' type='application/pdf' width='560' height='700'><p>It appears that you don't have a PDF plugin for this browser. You can <a href='{% link /assets/presentations/2025-10-october-excl-meeting.pdf %}'>click here to download the PDF file.</a></p></object>

----

Below is a LLM-generated summary from the meeting slides.

---

## Highlights from the October 2025 ExCL Monthly Meeting

### Introduction

On October 16, 2025, the Experimental Computing Laboratory (ExCL) held its monthly meeting in Oak Ridge, Tennessee. The meeting was presented by Steve Moulton, Aaron Young, and Jeffrey Vetter from the Advanced Computing Systems Research Section. Here are the key topics and updates discussed during the meeting.

### New Hardware List and State

#### Hardware for FPGA and Software Development

- **AMD Versal VHK158 Evaluation Kit**: FPGA development, currently in a box for user deployment.
- **AMD Xilinx VCU118 Evaluation Kit**: FPGA development, similar status as the Versal kit.
- **Apple Studio M3 MAX**: Software development and GitLab runners, not deployed yet.
- **GeForce RTX 1090 (Nvidia consumer grade)**: Development and analysis of software using GPUs, awaiting deployment.
- **AMD Radeon RX 9070 XT**: Development and analysis of software using GPUs, requires 775 watts and will be deployed in one of the Milans.

#### Networking and Remote Management

- **Cisco C9216 Network Switches**: Core networking, deployment requested for 3700 and K200.
- **Hubbell Rack Cabinet (lockable)**: Secure enclosure for Cisco switch, deployment requested for 3700.

### 2026 Hardware Requests and Availability

- **AI/LLM Desktop (Framework Desktop)**: LLM development, shipping in Q4.
- **NVIDIA DGX Spark (Grace Blackwell)**: LLM development and performance analysis, purchase invitation received.
- **Tenstorrent Blackhole P100a**: AI accelerator, awaiting availability.

### TRC Lab A102

The TRC Lab A102 will be used for embedded system and microelectronics development. It will be on the ExCL private network with access to ORNL workstations network if needed. RHACS compliance will be required for admission.

### General Updates

- **Slurm Accounting**: Setup and configuration updates.
- **Account and Project Request Flows**: Improved with automation.
- **System Specific Notes**: Now included in the message of the day (MOTD) shown on every system.

### Gentle Reminders

- **Login.excl.ornl.gov**: Not for computation or compiling, only for ssh and thinlinc access.
- **VSCode Usage**: Avoid running VSCode on the login node via Remote-SSH or ThinLinc.

### Questions and Discussion

The meeting concluded with a Q&A session where various topics such as power measurement at the host, CPU, and APU levels were discussed.
