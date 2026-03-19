---
title: ExCL March Meeting 2026
toc: false
toc_sticky: false
categories: [ExCL]
tags: [User Meetings]
excerpt_separator: <!--more-->
header:
    image: /assets/images/ExCL-Header-web-no-text.png
    teaser: /assets/images/2026-03-march-excl-meeting-splash.jpg
---

March 2026 ExCL meeting slides.

<!--more-->

<object data='{% link /assets/presentations/2026-03-march-excl-meeting.pdf %}' type='application/pdf' width='560' height='700'><p>It appears that you don't have a PDF plugin for this browser. You can <a href='{% link /assets/presentations/2026-03-march-excl-meeting.pdf %}'>click here to download the PDF file.</a></p></object>

----

Below is a LLM-generated summary from the meeting slides.

---

# 🚀 ExCL Monthly Update — March 2026


This month’s updates focus on **storage usability, CI improvements, shared infrastructure, and data management best practices**.

---

## 📂 Improved Project Storage Navigation

We’ve made a small but impactful usability improvement:

* You can now **read project folder names under `/auto/projects`**
* Permissions remain unchanged, but **directory discovery is much easier**
* Tools like `vim`, `yazi`, and tab completion now work more effectively

💡 *Note:* The first access still triggers automount—after that, navigation is seamless.

---

## 📦 New Shared Storage for Apptainer Images

To better support large container workflows:

* New shared location:

  ```bash
  /auto/projects/apptainer
  ```
* Designed for **large, reusable Apptainer images**
* Current use cases include:
  * Unreal Engine containers
  * AMD Vitis environments
* Storage policy:
  * Default cap: **1 TB**
  * Adjustable as needed

---

## ⚙️ CI on ExCL: Slurm + GitLab (Recommended)

Running CI through Slurm is now the **standard and recommended approach for jobs running across multiple ExCL systems**.

### Key Improvements

* ✅ **CI template now checks `sbatch` return codes**
* ⚠️ Standard error is treated as a **warning**, not immediate failure
* 🧪 New **system-device-smoke-test**:
  * Validates CUDA, HIP, OpenMP, OpenCL
  * Runs across major ExCL systems
  * Uses shared IRIS setup scripts:

```bash
source /auto/software/iris/setup-system.source
```

📌 This significantly improves **reliability and portability of CI pipelines** across heterogeneous nodes.

---

## 📊 DVC for Data Management on ExCL

We now recommend **DVC (Data Version Control)** for managing datasets and pipelines.

### Why DVC Works Well on ExCL

* Shared cache model:
  * Store data in a **project-level shared cache**
  * Avoid duplication across repos
* Hybrid workflow:
  * Same cache can act as:
    * Local shared storage (on ExCL)
    * Remote storage (outside ExCL)

👉 See the **[DVC Quick Start Guide in ExCL Docs](https://docs.excl.ornl.gov/quick-start-guides/dvc)** for setup instructions.

---

## 📚 Documentation Best Practices Highlight

We highlighted an excellent resource:

**[“Minimum Viable Documentation Product (MVDP)”](https://cass.community/events/hpcbp-097-onegoodtutorial)**
from the Consortium for the Advancement of Scientific Software

### Key Takeaway

Follow a **documentation checklist**:

- [ ] 🗺️ **[Synopsis](https://onegoodtutorial.org/in-depth/synopsis/):** 1–3 sentence summary of your project
- [ ] 📑 **[Tutorial](https://onegoodtutorial.org/in-depth/tutorial-planning/):** ✨ Show people what your software can do! ✨
- [ ] 👩‍🔧 **[Contact Information](https://onegoodtutorial.org/in-depth/contact-information/):** How to ask a human about your software
- [ ] 🚀 **[Install Instructions](https://onegoodtutorial.org/in-depth/installation-instructions/):** How to install your software
- [ ] 📜 **[Citation Instructions](https://onegoodtutorial.org/in-depth/software-citation/):** How to cite your software
- [ ] 🙌 **[Contribution Statement](https://onegoodtutorial.org/in-depth/contribution-statements/):** How users can contribute to your project
- [ ] 📚 **[Reference Material](https://onegoodtutorial.org/in-depth/reference-material/):** Precise specifications of APIs, etc.
- [ ] ⚖️ **[Licensing Statement](https://onegoodtutorial.org/in-depth/licensing-statements/):** The legal status of your code
- [ ] 🙏 **[Acknowledgments](https://onegoodtutorial.org/in-depth/acknowledgments/):** Credit your funders


🔗 Resource: [https://onegoodtutorial.org](https://onegoodtutorial.org)

---

## 🖥️ System & Infrastructure Updates

* ⏳ Migration of **MI100 / V100 system** delayed until after SC26 submissions
* 🔄 Work ongoing to restore **Groq inference hardware**
* 🆕 **Tenstorrent Blackhole** acquisition in progress
* 🔧 Scheduled downtime:
  * **Tuesday, March 24, 9–11 AM**
    * OS updates + system reboots
    * No NVIDIA driver updates (unless requested)

---

## 💬 Open Topics & Discussion Areas

We’re actively gathering feedback on:

* Legacy system usage (e.g., *Leconte PowerPC + V100*)
* Hudson access policies. Request to limit system to Slurm-only access.
* Cloud GPU access options

---

## 📌 Summary

This month’s updates continue to push ExCL toward:

* **More usable shared infrastructure**
* **Scalable data workflows (DVC)**
* **Robust CI across heterogeneous systems**
* **Better documentation practices**

If you have feedback or want help adopting any of these tools, reach out!
