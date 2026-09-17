---
title: ExCL September Meeting 2026
toc: false
toc_sticky: false
categories: [ExCL]
tags: [User Meetings]
excerpt_separator: <!--more-->
header:
    image: /assets/images/ExCL-Header-web-no-text.png
    teaser: /assets/images/2026-09-september-excl-meeting-splash.jpg
---

September 2026 ExCL meeting slides.

<!--more-->

<object data='{% link /assets/presentations/2026-09-september-excl-meeting.pdf %}' type='application/pdf' width='560' height='700'><p>It appears that you don't have a PDF plugin for this browser. You can <a href='{% link /assets/presentations/2026-09-september-excl-meeting.pdf %}'>click here to download the PDF file.</a></p></object>

----

Below is a LLM-generated (and reviewed for correctness) summary from the meeting slides.

---

# 🚀 ExCL Monthly Update — September 2026

This month's meeting covered the rollout of interactive-only Slurm access on `faraday`, `hudson`, and `maxwell`, an upcoming DOE-mandated multi-factor authentication requirement for off-site SSH and web access, the retirement of Freshdesk in favor of the ExCL support request form, and new self-service tooling for checking login-node quota usage.

---

## 🔒 Policy Changes — High-Utilization Systems

* ExCL is seeing much higher utilization as the user base grows and more AI-space work is done, leading to resource contention.
* Following this meeting, `faraday`, `hudson`, and `maxwell` will be restricted to interactive Slurm access only.
  * This enables finer-grained allocation (e.g., by GPU count) and eases off-hour exclusive holds when needed.
  * The [pam_slurm_adopt](https://slurm.schedmd.com/pam_slurm_adopt.html) module will limit SSH access to users holding a Slurm allocation on the node, with the SSH session constrained to the allocated resources.
* See the [Slurm section of the ExCL User Docs](https://docs.excl.ornl.gov/quick-start-guides/slurm) for updated documentation, including example `srun` commands:
  * `srun -p nvidia --gres gpu:P100:2 --mem 128G -c 16 --pty bash`
  * `srun -p nvidia -w hudson --exclusive --pty bash`
* See the [Primary Usage Notes](https://docs.excl.ornl.gov/system-overview#primary-usage-notes) for guidance on recommended places to run jobs.

---

## 🔐 External Login Changes — Multi-Factor Authentication

* DOE has mandated multi-factor authentication for SSH and web services (e.g., ThinLinc) accessed from outside the ORNL network envelope.
* Full details aren't finalized, but the process will look like:
  1. Access `login.excl.ornl.gov` via SSH.
  2. Receive a QR prompt.
  3. Configure a Google/Microsoft/FreeOTP authenticator using the QR prompt.
  4. Use the authenticator-generated, single-use, time-limited key as your password into ExCL.
* Full details will be shared via the excl-users mailing list once in place.
* `login-int.excl.ornl.gov` will bypass this procedure but is not available from off-site.
* ExCL is modeling this approach on a similar facility already set up and documented by ITSD.

---

## 🎫 excl-help Changes — Freshdesk Retirement

* ExCL is discontinuing Freshdesk for ticket management as of end of day Thursday, September 17 — the free subscription doesn't provide enough benefit to justify converting to paid.
* The primary ticketing channel is now the [ExCL Support Request Form](https://www.excl.ornl.gov/support-request/), also reachable from www.excl.ornl.gov via the Support Request tab.
  * Requests are emailed to ExCL and tracked in Todoist; all documentation references have been updated.
* The excl-help@ornl.gov mailing list remains available to reach ExCL staff.
* No changes to the Slack group — informal contacts are still welcome.

---

## 💬 Questions / Projects / Comments / Discussions

* Checkmk monitoring of cgroup resource limit counters for the login limits?
  * Users can now view their own resource use and limit counters with `login-quota-check`.
    * See [Access to ExCL # Login Server Quotas](https://docs.excl.ornl.gov/excl-support/access#login-server-quotas) in the ExCL User Docs.

---

## 📌 Summary

September's meeting centered on tightening access controls as ExCL usage continues to grow: interactive-only Slurm access is coming to `faraday`, `hudson`, and `maxwell`, and a DOE-mandated multi-factor authentication process is on the way for off-site SSH and web access. It also covered the retirement of Freshdesk in favor of the ExCL support request form and Todoist-based tracking, plus the new `login-quota-check` tool for users to monitor their own login-node resource limits.
