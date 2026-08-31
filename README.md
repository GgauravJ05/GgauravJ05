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

Most of what I build sits between machine learning and systems: a model constrained by a real latency budget, or a data structure chosen for how it fails rather than how it benchmarks. Full write-ups, with the engineering decisions behind each, are on the [work page](https://gauravjadhav.vercel.app/work).

<table>
<tr>
<td width="50%" valign="top">

### InsureTrust
**Insurance claim fraud screening** · 🥇 1st Prize, FinTech domain — MIT ADT AI Grand Challenge

A claim splits into two independent lanes. A gradient-boosted model scores tabular claim features; a separate image forensics stage inspects submitted document photographs for signs of manipulation. The lanes never touch until the end, where the scores combine into one verdict that routes the claim to a human reviewer rather than approving or rejecting it. They are kept independent because they fail differently — a claim has to look ordinary on both to pass.

Backend developer, two-person team. SHAP output accompanies each score, so a flagged claim is arguable rather than asserted.

`Python` · `XGBoost` · `Image Forensics` · `SHAP`

[▶ Demo](https://youtu.be/FLbIlEuwKX8) · [Case study](https://gauravjadhav.vercel.app/work) · *Source on public release*

</td>
<td width="50%" valign="top">

### NextGen Virtual File System
**Block allocation and fragmentation, from first principles**

A file system in C++ over a flat block device: free space in a bitmap (one bit per block, so a lookup is a bit test rather than a walk over metadata), inode-style records, and First-Fit allocation over contiguous runs.

Built to confront the trade-off First-Fit implies. Against a fixed workload — a 1024-block device held at 80% occupancy for 3,000 delete/allocate cycles — the longest usable run falls from 189 blocks to about 32 while total free space stays near 198, and 6.7% of writes are refused on a disk that was never full. A browser reimplementation of the allocator makes that visible.

`C++` · `TypeScript` · `Data Structures`

[Code](https://github.com/GgauravJ05/NextGen-Virtual-File-System) · [Live simulator](https://neon-vfs-console.lovable.app/)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### LunarComm
**Delay-tolerant lunar relay mesh**

Mission-control simulation for ISRO–JAXA LUPEX operations around Shackleton crater. Rovers lose line of sight inside Permanently Shadowed Regions, so the system never assumes a continuous link: it drops breadcrumb relays, holds RFC 9171-style bundles in per-node FIFOs until a hop reopens, and burst-flushes on reconnect.

The backend runs a 10 Hz tick — bilinear LOLA heightfield sampling for line of sight, RSSI from free-space path loss minus terrain attenuation, NetworkX for the RF graph. On blackout the rover keeps driving a bounded 29 s speculative probe, then reverses along its own 35 s pose history if no hop is found.

Judged in demo rehearsal rather than against a published DTN benchmark, so no delivery-ratio figure is claimed.

`Python` · `FastAPI` · `NetworkX` · `React Three Fiber`

[▶ Demo](https://youtu.be/6sMI-IlAhr8) · [Case study](https://gauravjadhav.vercel.app/work) · *Source on public release*

</td>
<td width="50%" valign="top">

### PulseRoute
**Predictive emergency dispatch**

Golden-hour ambulance routing. Nearest-hospital dispatch is a poor proxy for care — an ambulance can arrive at a full ICU or a missing ventilator and lose minutes that matter.

XGBoost triage on EMT-reported vitals predicts severity and resource needs; a weighted constraint engine then ranks hospitals over ICU beds, ventilators, specialties, ER load and travel time, with a hard filter so a facility that cannot treat the patient is excluded rather than merely ranked low. Batch mode redistributes mass-casualty arrivals across the grid. An edge build falls back to a local model, a shadow-cached hospital grid and an OSMnx road graph, so losing the API degrades dispatch rather than stopping it.

`Python` · `XGBoost` · `FastAPI` · `OSMnx` · `Streamlit`

[Case study](https://gauravjadhav.vercel.app/work) · *Source on public release*

</td>
</tr>
<tr>
<td width="50%" valign="top">

### Conflux
**Peer-to-peer video meetings**

Media travels directly between participants; the server only relays signalling. The interesting part is everything after "video appears": sampling `getStats()` every two seconds for bitrate, loss, RTT, jitter and whether media is going direct or through a relay, so a degrading call can be diagnosed rather than guessed at; restarting ICE when someone's network changes under them; and swapping tracks via `replaceTrack` so mute and screen share never renegotiate.

Captions run on the browser's own Web Speech API — no audio leaves for a service I operate.

`WebRTC` · `Node.js` · `Socket.IO` · `React` · `MongoDB`

[Code](https://github.com/GgauravJ05/conflux) · [Case study](https://gauravjadhav.vercel.app/work)

</td>
<td width="50%" valign="top">

### FlowState
**On-device cognitive load estimation**

Estimates cognitive load and burnout risk from behavioural telemetry — and every model runs locally. That constraint is the project: the signals most useful for inferring mental state are exactly the ones users should be most reluctant to upload, so the architecture removes the upload rather than promising to handle it responsibly. No upload means no server-side store to breach or subpoena.

The cost is accepted: no cross-user baseline, no aggregate learning, inference bounded by the user's own hardware.

In-progress prototype, not validated against any clinical measure of cognitive load.

`Python` · `On-device Inference`

[▶ Demo](https://youtu.be/gaAN8GJqN3w) · [Case study](https://gauravjadhav.vercel.app/work) · *Source on public release*

</td>
</tr>
</table>

<br>

## Open Questions

Exploratory work, tracked on the [research page](https://gauravjadhav.vercel.app/research).

- **Deterministic block allocators for resource-constrained file systems** — how external fragmentation accumulates across allocate/delete cycles under First-Fit over a contiguous block device. Not peer reviewed.
- **Latency behaviour in multi-agent LLM pipelines** — where the time actually goes: agent handoff versus model inference, and whether a local vector cache meaningfully reduces lookup latency. No results to report yet.

<br>

## About

I work on machine learning systems for risk and anomaly detection, and on the systems programming that sits underneath them. Recent work includes the fraud screening pipeline that took 1st Prize in the FinTech domain of the national MIT ADT AI Grand Challenge, and a file system written in C++ to understand block allocation from first principles.

**Roles**
- Director of Technology — Renascent Mirai Foundation
- IEEE Region 10 (Asia-Pacific) ACEI Entrepreneurship Ambassador 2026, representing India
- Member Relations, Student Activities Committee — IEEE Pune Section
- Webmaster and Core Committee — IEEE Student Branch, MMCOE
- President — IT Tech Club, MMCOE

**Also** — 1st Prize, MIT ADT AI Grand Challenge 2026 · Top 5%, IGNISIA '26 · Top 6, XENIA Hackathon 2026 · CGPA 9.55. Away from the keyboard, a black belt in Taekwondo and a standing appointment with Japanese grammar.

<br>

## Tools

**ML & data** — Python, NumPy, Pandas, Scikit-learn, XGBoost, SHAP
**Systems** — C++, C, FastAPI, NetworkX, OSMnx
**Web** — React, TypeScript, Node.js, Express, MongoDB, Tailwind CSS, WebRTC

<br>

## How I work

- Optimisation follows a measurement, not an intuition. Correctness and clean boundaries first; profile before rewriting anything for speed.
- All code is a liability. Decoupled, local modules mean a component can be removed without unpicking the rest of the system.
- A feature is not finished while its specification and README are missing. Technical context decays faster than source code does.

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
