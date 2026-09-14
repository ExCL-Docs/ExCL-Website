---
title: ExCL August Meeting 2026
toc: false
toc_sticky: false
categories: [ExCL]
tags: [User Meetings]
excerpt_separator: <!--more-->
header:
    image: /assets/images/ExCL-Header-web-no-text.png
    teaser: /assets/images/2026-08-august-excl-meeting-splash.jpg
---

August 2026 ExCL meeting slides.

<!--more-->

<object data='{% link /assets/presentations/2026-08-august-excl-meeting.pdf %}' type='application/pdf' width='560' height='700'><p>It appears that you don't have a PDF plugin for this browser. You can <a href='{% link /assets/presentations/2026-08-august-excl-meeting.pdf %}'>click here to download the PDF file.</a></p></object>

----

Below is a LLM-generated summary from the meeting slides.

---

# 🚀 ExCL Monthly Update — August 2026

This month's meeting covered several policy changes driven by rising resource utilization (accelerator access, NVHPC updates, and login server limits), an update on Claude Code sandboxing mechanism to add Codex support, the upcoming move of benchtop systems to the TRC (3700) Lab A102, a new shared Apptainer image space, and the nvtop monitoring rollout.

---

## 🔒 Policy Changes — High-Utilization Systems

* ExCL is seeing much higher utilization as the user base grows and more AI-space work is done, leading to resource contention
* Popular accelerator systems will move to require slurm allocations, enabling finer-grained allocation (e.g., by GPU count) and easing off-hour exclusive holds
  * This will be well-documented, including guidance on which resources remain available for non-accelerator applications
  * Case in point: a large, non-accelerator design-space search on a popular system was blocking accelerator access for others
* The "triple crown" servers (affirmed, justify, pharaoh, secretariat) — 128 physical cores (256 virtual), 1 TB memory — are powerful but currently underutilized and well suited to larger problems

---

## 🧩 Policy Clarification — NVHPC

* Systems engineering is minimizing NVHPC (including CUDA) and driver updates
* NVIDIA/AMD driver updates are applied automatically as part of OS updates for stability and security, but drivers aren't always reloaded automatically
  * If `nvidia-smi` reports a driver mismatch, use [ExCL Support Request Form](https://www.excl.ornl.gov/support-request/) to report — this is often fixable without a reboot
* NVHPC itself is *not* auto-updated; it's updated on request or as new NVHPC/Linux runtime features require it
* If an NVHPC update causes problems, contact ExCL — rollback and virtualization remediation options are available

---

## 🖧 Policy Changes — Login Services

* New per-user aggregate resource limits on the ExCL login server, to prevent individual sessions from starving others:
  * CPU: 1 core worth of aggregate CPU time
  * Memory pressure threshold: 1 GiB
  * Maximum memory: 1.5 GiB
  * Maximum swap: 512 MiB
* A VS Code server with extensions can no longer run on the login node — connect directly to a worker node instead (see the ExCL User Docs)
  * Good underutilized systems for a VS Code server: oswald, odswald00, oswald02, oswald03
* Caution: exceeding your quota on the login node also degrades responsiveness to worker nodes, since the login node is your jump host

---

## 🤖 Claude Code in ExCL — Updated with Codex Support

* The Claude Code Quick-Start Guide in the ExCL User Docs now also covers Codex
* A dedicated VM for running Claude is coming soon; in the meantime, launch sessions on Explorer and use Slurm for jobs needing specific accelerators
* Claude tends to launch sub-agents and other long-running jobs that can persist after exiting the TUI, so keep that in mind when closing Claude

---

## 📦 Planning Move to TRC (3700) Lab A102

* Progress continues on moving into the A102 lab space
* Benchtop systems will need to be powered down and packed, affecting all benchtop FPGA systems and desktop systems including the Zenith systems
* The move is planned for early-to-mid September; ORNL-mover moves typically take ~14 days
  * Loose accelerators will be packed first, with enclosed systems powered down later, closer to the narrower moving window

---

## 🗂️ Shared Large Apptainer Image Space

* Container images under 50G can be stored and shared via Harbor
* Larger, general-purpose images (>50G) can be shared via the new Apptainer shared project space
* Writing requires group membership, but any ExCL user can read from the space

---

## 📊 nvtop

* `nvtop`, a simple GPU performance visualization tool supporting NVIDIA, AMD, and Intel GPUs, is being deployed to all systems via the excl-utils module
* Also useful as a quick way to check what GPU architecture (if any) a system has
* Already natively available on several systems, including Maxwell

---

## 💬 Questions / Projects / Comments / Discussions

* Interest in Checkmk monitoring of cgroup resource limit counters for the new login limits

---

## 📌 Summary

August's meeting focused on policy changes addressing rising utilization: interactive-only access for popular accelerator systems, clarified NVHPC update practices, and new per-user resource limits on the login server (including the end of login-node VS Code servers). It also covered Codex support landing in the Claude Code quick-start guide, plans to move into the TRC (3700) Lab A102 in early-to-mid September, a new large-image Apptainer shared space, and the rollout of the nvtop GPU monitoring tool.
