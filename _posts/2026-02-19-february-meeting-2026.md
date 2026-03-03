---
title: ExCL February Meeting 2026
toc: false
toc_sticky: false
categories: [ExCL]
tags: [User Meetings]
excerpt_separator: <!--more-->
header:
    image: /assets/images/ExCL-Header-web-no-text.png
    teaser: /assets/images/2026-02-february-excl-meeting-splash.jpg
---

February 2026 ExCL meeting slides.

<!--more-->

<object data='{% link /assets/presentations/2026-02-february-excl-meeting.pdf %}' type='application/pdf' width='560' height='700'><p>It appears that you don't have a PDF plugin for this browser. You can <a href='{% link /assets/presentations/2026-02-february-excl-meeting.pdf %}'>click here to download the PDF file.</a></p></object>

----

Below is a LLM-generated summary from the meeting slides.

---

# ExCL Monthly Update – February 2026

**February 19, 2026 – Oak Ridge, Tennessee**

*Experimental Computing Laboratory (ExCL), Advanced Computing Systems Research Section*

The February ExCL Monthly Meeting highlighted significant infrastructure upgrades, documentation improvements, and ongoing efforts to expand our heterogeneous computing capabilities in support of growing AI and accelerator-driven workloads.

Below is a summary of key updates.

---

## 🚀 New System Deployment: Maxwell (Formerly hyp-100)

Maxwell is being redeployed from ORC to ExCL and will soon be integrated into the ExCL environment (including home directories and shared resources).

### System Specifications

* **2× AMD EPYC 7763 (64 cores each)**
  * Expected to run hyperthreaded (256 cores total)
* **1 TB Main Memory**
* **4× NVIDIA A100 (40GB, no NVLink)**
* **4× AMD MI100 (32GB)**

This system is particularly well suited for:

* General compute workloads
* Large language model (LLM) experimentation
* Heterogeneous accelerator research

Configuration is non-trivial, so the current OS release will likely remain in place during integration.

---

## 🖥 ThinLinc Updates and Licensing

ThinLinc has undergone both licensing and version updates.

### Key Changes

* Standard license reverted from **10 → 3 concurrent users**
* Upgraded to **ThinLinc 4.20.0**
* Secured **90-day licenses for 10 concurrent users** while permanent licensing is pursued

### Important Reminder

ThinLinc sessions are persistent (similar to `tmux`). Please **log off when not actively using your session** to avoid consuming licenses unnecessarily.

Idle sessions may be terminated if needed.

---

## ⚠️ ThinLinc XFCE Configuration Reset

If your XFCE desktop environment becomes unstable or misconfigured, reset it using:

```bash
rm -rf ~/.config/xfce4
rm -rf ~/.cache/sessions
rm -rf ~/.local/share/xfce4
rm -rf ~/.config/xfce4/panel
```

This restores a clean session state.

---

## 📦 Apptainer Deployment Expands

Apptainer has been successfully deployed and tested on:

* **Affirmed**
* **Justify**
* **Pharaoh**
* **Secretariat**
* **Faraday**

As additional systems are redeployed, Apptainer will be installed where appropriate to support containerized workflows.

Documentation is available in the ExCL User Docs.

---

## 📚 Documentation Updates

Several improvements have been made to ExCL documentation:

* [**Python Virtual Environments Using `uv`**](https://docs.excl.ornl.gov/quick-start-guides/python#python-virtual-environments-using-uv)
* [**Marimo Quick Start Guide**](https://docs.excl.ornl.gov/quick-start-guides/marimo)
* [**Jupyter Notebook Access via FoxyProxy (Recommended)**](https://docs.excl.ornl.gov/quick-start-guides/jupyter-quick-start#using-foxyproxy-recommended)

These updates streamline environment management and interactive development workflows.

---

## 🎥 Live Demonstration

The meeting included a demonstration covering:

* ThinLinc usage
* FoxyProxy configuration
* Python environment setup with `uv`
* SSH port forwarding

These tools continue to form the recommended workflow for interactive ExCL usage.

---

## 🔬 ExCL Microelectronics & Neuromorphic Lab (3700/A102)

Progress continues on the ExCL microelectronics and neuromorphic laboratory space:

* ExCL VLAN networking completed
* Device relocation from 5100/227 being scheduled
* Infrastructure adjustments ongoing

(We are also tracking down the mysteriously relocated stools.)

---

## 🎮 New GPU Deployments (AI Inference Focus)

To support increasing AI inference workloads, we are preparing to deploy:

* **NVIDIA GeForce RTX 5090**
* **AMD Radeon RX 9070 XT**

These are consumer-grade but high-power GPUs intended to supplement current infrastructure.

We are also:

* Re-engaging with **Grok** regarding accelerator support
* Holding discussions with **Tenstorrent**

Long-term, these accelerators may help shift workload away from traditional GPUs.

---

## 🧠 Slurm Reminder (GPU Jobs)

If your job requires GPUs, ensure you request them explicitly via Slurm:

```bash
--gpus=2
```

Failure to request GPU resources may result in improper scheduling or runtime errors.

---

## Looking Ahead

ExCL continues to expand its heterogeneous computing capabilities across CPUs, GPUs, and emerging accelerator platforms. With growing AI and inference demands, our infrastructure roadmap remains focused on flexibility, containerization, and performance experimentation.

If you have questions, project ideas, or would like systems deployed with specific configurations (e.g., Apptainer), please reach out.
