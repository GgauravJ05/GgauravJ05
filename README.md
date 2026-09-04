<div align="center">

# Gaurav Jadhav

**Machine learning systems for risk and anomaly detection — and the systems programming underneath them.**

Director of Technology, Renascent Mirai Foundation · B.Tech Information Technology, MMCOE Pune

[![Portfolio](https://img.shields.io/badge/Portfolio-0B132B?style=for-the-badge&logo=vercel&logoColor=C9A24B)](https://gauravjadhav.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0B132B?style=for-the-badge&logo=linkedin&logoColor=C9A24B)](https://www.linkedin.com/in/ggauravj05)
[![Medium](https://img.shields.io/badge/Medium-0B132B?style=for-the-badge&logo=medium&logoColor=C9A24B)](https://medium.com/@ggauravj5)
[![Email](https://img.shields.io/badge/Email-0B132B?style=for-the-badge&logo=gmail&logoColor=C9A24B)](mailto:ggauravj05@gmail.com)
[![Resume](https://img.shields.io/badge/Resume-0B132B?style=for-the-badge&logo=googledocs&logoColor=C9A24B)](https://gauravjadhav.vercel.app/resume)

</div>

<br>

## Selected Work

Full write-ups, with the engineering decisions behind each, on the [work page](https://gauravjadhav.vercel.app/work).

<table>
<tr>
<td width="50%" valign="top">

### InsureTrust
**Insurance claim fraud screening** · 🥇 1st, FinTech — MIT ADT AI Grand Challenge

Two independent lanes — a gradient-boosted model on tabular claim features, a separate image forensics pass on submitted documents — fuse into one SHAP-explained verdict that routes to a human reviewer.

`Python` `XGBoost` `Image Forensics` `SHAP`
[Demo](https://youtu.be/FLbIlEuwKX8) · [Case study](https://gauravjadhav.vercel.app/work)

</td>
<td width="50%" valign="top">

### NextGen Virtual File System
**Block allocation and fragmentation, from first principles**

C++ file system over a flat block device — bitmap free space, inode-style records, First-Fit allocation. Under a fixed 3,000-cycle workload at 80% occupancy, longest usable run drops from 189 → 32 blocks; 6.7% of writes get refused on a disk that's never full.

`C++` `TypeScript` `Data Structures`
[Code](https://github.com/GgauravJ05/NextGen-Virtual-File-System) · [Live simulator](https://neon-vfs-console.lovable.app/)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### LunarComm
**Delay-tolerant lunar relay mesh**

ISRO–JAXA LUPEX mission-control sim. Rovers hold RFC 9171-style bundles in per-node FIFOs through Permanently Shadowed Region blackouts, burst-flushing on reconnect. 10 Hz tick, bilinear LOLA heightfield LOS, RSSI path-loss modeling, NetworkX RF graph.

`Python` `FastAPI` `NetworkX` `React Three Fiber`
[Demo](https://youtu.be/6sMI-IlAhr8) · [Case study](https://gauravjadhav.vercel.app/work)

</td>
<td width="50%" valign="top">

### PulseRoute
**Predictive emergency dispatch**

XGBoost triage on EMT-reported vitals feeds a weighted constraint engine ranking hospitals on ICU beds, ventilators, specialties, ER load and travel time — hard-filtering facilities that can't treat the patient rather than just ranking them low. Edge build falls back to a local model + cached grid.

`Python` `XGBoost` `FastAPI` `OSMnx` `Streamlit`
[Case study](https://gauravjadhav.vercel.app/work)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### Conflux
**Peer-to-peer video meetings**

Direct media between peers, server only signals. `getStats()` sampled every 2s for bitrate/loss/RTT/jitter, ICE restart on network change, `replaceTrack` for mute/share without renegotiation. Captions via browser Web Speech API — no audio leaves the device.

`WebRTC` `Node.js` `Socket.IO` `React` `MongoDB`
[Code](https://github.com/GgauravJ05/conflux) · [Case study](https://gauravjadhav.vercel.app/work)

</td>
<td width="50%" valign="top">

### FlowState
**On-device cognitive load estimation**

Cognitive load and burnout risk inferred from behavioral telemetry, entirely on-device — no upload, no server-side store to breach. Trade-off: no cross-user baseline. In-progress prototype, not clinically validated.

`Python` `On-device Inference`
[Demo](https://youtu.be/gaAN8GJqN3w) · [Case study](https://gauravjadhav.vercel.app/work)

</td>
</tr>
</table>

<br>

<details>
<summary><b>Open Questions</b> — exploratory work, tracked on the <a href="https://gauravjadhav.vercel.app/research">research page</a></summary>
<br>

- **Deterministic block allocators for resource-constrained file systems** — how external fragmentation accumulates across allocate/delete cycles under First-Fit over a contiguous block device. Not peer reviewed.
- **Latency behaviour in multi-agent LLM pipelines** — agent handoff vs. model inference, and whether a local vector cache meaningfully cuts lookup latency. No results yet.

</details>

<br>

## About

ML systems for risk and anomaly detection, and the systems programming underneath them. 1st Prize, FinTech domain, MIT ADT AI Grand Challenge · Top 5%, IGNISIA '26 · Top 6, XENIA Hackathon 2026 · CGPA 9.55.

**Roles**
- Director of Technology — Renascent Mirai Foundation
- IEEE Region 10 (Asia-Pacific) ACEI Entrepreneurship Ambassador 2026, representing India
- Member Relations, Student Activities Committee — IEEE Pune Section
- Webmaster and Core Committee — IEEE Student Branch, MMCOE
- President — IT Tech Club, MMCOE

<details>
<summary><b>How I work</b></summary>
<br>

- Optimisation follows a measurement, not an intuition. Correctness and clean boundaries first; profile before rewriting anything for speed.
- All code is a liability. Decoupled, local modules mean a component can be removed without unpicking the rest of the system.
- A feature is not finished while its specification and README are missing.

</details>

<br>

## Tools

**ML & data**
![Python](https://img.shields.io/badge/Python-0B132B?style=flat-square&logo=python&logoColor=C9A24B)
![NumPy](https://img.shields.io/badge/NumPy-0B132B?style=flat-square&logo=numpy&logoColor=C9A24B)
![Pandas](https://img.shields.io/badge/Pandas-0B132B?style=flat-square&logo=pandas&logoColor=C9A24B)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-0B132B?style=flat-square&logo=scikitlearn&logoColor=C9A24B)
![XGBoost](https://img.shields.io/badge/XGBoost-0B132B?style=flat-square&logoColor=C9A24B)
![SHAP](https://img.shields.io/badge/SHAP-0B132B?style=flat-square&logoColor=C9A24B)

**Systems**
![C++](https://img.shields.io/badge/C%2B%2B-0B132B?style=flat-square&logo=cplusplus&logoColor=C9A24B)
![C](https://img.shields.io/badge/C-0B132B?style=flat-square&logo=c&logoColor=C9A24B)
![FastAPI](https://img.shields.io/badge/FastAPI-0B132B?style=flat-square&logo=fastapi&logoColor=C9A24B)
![NetworkX](https://img.shields.io/badge/NetworkX-0B132B?style=flat-square&logoColor=C9A24B)
![OSMnx](https://img.shields.io/badge/OSMnx-0B132B?style=flat-square&logoColor=C9A24B)

**Web**
![React](https://img.shields.io/badge/React-0B132B?style=flat-square&logo=react&logoColor=C9A24B)
![TypeScript](https://img.shields.io/badge/TypeScript-0B132B?style=flat-square&logo=typescript&logoColor=C9A24B)
![Node.js](https://img.shields.io/badge/Node.js-0B132B?style=flat-square&logo=nodedotjs&logoColor=C9A24B)
![Express](https://img.shields.io/badge/Express-0B132B?style=flat-square&logo=express&logoColor=C9A24B)
![MongoDB](https://img.shields.io/badge/MongoDB-0B132B?style=flat-square&logo=mongodb&logoColor=C9A24B)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-0B132B?style=flat-square&logo=tailwindcss&logoColor=C9A24B)
![WebRTC](https://img.shields.io/badge/WebRTC-0B132B?style=flat-square&logo=webrtc&logoColor=C9A24B)

<br>

## GitHub

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=GgauravJ05&show_icons=true&include_all_commits=true&count_private=true&rank_icon=github&hide_title=true&bg_color=ffffff&title_color=0B132B&icon_color=C9A24B&text_color=222222&ring_color=C9A24B&border_color=D9DDE3&border_radius=10" height="170" alt="GitHub statistics for GgauravJ05" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=GgauravJ05&layout=compact&langs_count=8&hide=html,css&card_width=340&bg_color=ffffff&title_color=0B132B&text_color=222222&border_color=D9DDE3&border_radius=10" height="170" alt="Most used languages by GgauravJ05" />

<br><br>

<img src="https://streak-stats.demolab.com?user=GgauravJ05&background=ffffff&border=D9DDE3&stroke=D9DDE3&ring=C9A24B&fire=C9A24B&currStreakNum=0B132B&sideNums=222222&currStreakLabel=0B132B&sideLabels=222222&dates=666666&border_radius=10" width="72%" alt="GitHub contribution streak for GgauravJ05" />

</div>

<br>

<div align="center">

<sub>Open to research collaborations and to internships in machine learning and systems.<br>
Email is the surest way to reach me — <a href="mailto:ggauravj05@gmail.com">ggauravj05@gmail.com</a> · <a href="https://www.linkedin.com/in/ggauravj05">LinkedIn</a></sub>

</div>
