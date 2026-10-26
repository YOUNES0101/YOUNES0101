<!--
  GitHub Profile README
  Repository: YOUNES0101/YOUNES0101

  Before publishing:
    1. Replace YOUR-LINKEDIN-HANDLE in the Connect section.
    2. When SAIP is public, swap its "In progress" badge for a repository link.
    3. Add .github/workflows/snake.yml (provided separately) so the contribution snake renders.
-->

<div align="center">

<picture>
  <source media="(prefers-color-scheme: light)" srcset="https://capsule-render.vercel.app/api?type=waving&height=200&color=0:E6EDF3,50:B6D4E8,100:7FB3D5&text=Younes%20Chemmaoui&fontColor=0D1117&fontSize=44&fontAlignY=36&desc=Infrastructure%20%C2%B7%20Networking%20%C2%B7%20Security&descSize=17&descAlignY=57&animation=fadeIn" />
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=200&color=0:0D1117,50:102A43,100:164E63&text=Younes%20Chemmaoui&fontColor=E6EDF3&fontSize=44&fontAlignY=36&desc=Infrastructure%20%C2%B7%20Networking%20%C2%B7%20Security&descSize=17&descAlignY=57&animation=fadeIn" alt="Younes Chemmaoui — Infrastructure, Networking and Security" />
</picture>

<a href="https://github.com/YOUNES0101">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=18&duration=3000&pause=1000&color=58A6FF&center=true&vCenter=true&width=620&lines=Building+and+securing+infrastructure;Automating+what+shouldn't+be+manual;Segmenting+networks%2C+hardening+hosts;Turning+logs+into+useful+signals;Build.+Break.+Investigate.+Document." alt="Building and securing infrastructure, automating what shouldn't be manual, turning logs into useful signals" />
</a>

<p>
  <img src="https://img.shields.io/badge/Focus-Infrastructure%20%26%20Security-123C69?style=flat-square" alt="Focus: Infrastructure and Security"/>
  <img src="https://img.shields.io/badge/Lab-Proxmox%20bare--metal-E57000?style=flat-square&logo=proxmox&logoColor=white" alt="Lab: Proxmox bare-metal"/>
  <img src="https://img.shields.io/badge/Mindset-Hands--on%20learning-116466?style=flat-square" alt="Mindset: Hands-on learning"/>
  <img src="https://komarev.com/ghpvc/?username=YOUNES0101&style=flat-square&color=58A6FF&label=Profile%20views" alt="Profile views"/>
</p>

<sub>
  <a href="#whoami">whoami</a> &nbsp;·&nbsp;
  <a href="#projects">projects</a> &nbsp;·&nbsp;
  <a href="#methodology">methodology</a> &nbsp;·&nbsp;
  <a href="#toolbox">toolbox</a> &nbsp;·&nbsp;
  <a href="#activity">activity</a> &nbsp;·&nbsp;
  <a href="#connect">connect</a>
</sub>

</div>

---

<a id="whoami"></a>
## `$ whoami`

I like understanding what happens behind the scenes: how machines communicate, how infrastructure is put together, where security boundaries belong, and what happens when something goes wrong.

My work sits at the intersection of **Linux, networking, infrastructure automation, and cybersecurity**. I learn by building labs, breaking configurations on purpose, investigating the failures, and documenting what I find — because understanding *why* something works matters more to me than getting a tool to run.

```yaml
engineer:
  name: Younes Chemmaoui
  focus:     [Linux, Networking, Infrastructure Automation, Cybersecurity]
  building:  SAIP — Secure Autonomous Infrastructure Platform
  approach:  build → break → investigate → document
  principle: "If it isn't monitored, it isn't secured."
```

---

<a id="projects"></a>
## `$ ls -l ./projects`

<table>
<tr>
<td width="50%" valign="top">

<h3>🛡️ SAIP</h3>

<strong>Secure Autonomous Infrastructure Platform</strong>

<img src="https://img.shields.io/badge/Status-In%20progress-F5A623?style=flat-square" alt="Status: in progress"/>

A hands-on lab exploring how to deploy, isolate, secure, and monitor services on bare-metal Proxmox — treated like production, not a sandbox.

- **Network** — segmented zones behind an nftables gateway
- **Provisioning** — reproducible infrastructure with Terraform
- **Hardening** — Linux configuration as code with Ansible
- **Observability** — metrics, logs, and SIEM alerting
- **Validation** — controlled failure and attack simulations

<strong>Core stack</strong><br/>
`Proxmox` `Linux` `Terraform` `Ansible` `nftables` `Wazuh` `Prometheus` `Grafana` `Loki`

</td>
<td width="50%" valign="top">

<h3>🔥 Firewall Security</h3>

<strong>Java-based packet filtering application</strong>

<a href="https://github.com/YOUNES0101/Firewall-Security"><img src="https://img.shields.io/badge/Repository-Firewall--Security-58A6FF?style=flat-square&logo=github&logoColor=white" alt="Firewall Security repository"/></a>

A desktop application that captures live traffic, applies configurable filtering rules, and shows allowed and blocked packets in real time.

- **Capture** — live packet capture with Pcap4J
- **Rules** — pluggable rule engine built on the Strategy pattern
- **Filtering** — by IP, port, protocol, and packet size
- **History** — traffic logs persisted to MySQL
- **Persistence** — Hibernate / JPA, containerized with Docker

<strong>Core stack</strong><br/>
`Java 21` `JavaFX` `Pcap4J` `Hibernate` `MySQL` `Docker`

</td>
</tr>
<tr>
<td colspan="2" valign="top">

<h3>🧪 Cybersecurity Portfolio</h3>

Hands-on exercises, investigations, technical notes, and lessons learned — the working notebook behind everything above.

<a href="https://github.com/YOUNES0101/cybersecurity-portfolio"><img src="https://img.shields.io/badge/Repository-cybersecurity--portfolio-161B22?style=flat-square&logo=github&logoColor=white" alt="Cybersecurity portfolio repository"/></a>

</td>
</tr>
</table>

<details>
<summary><strong>🗺️ SAIP — architecture overview</strong></summary>
<br/>

```mermaid
flowchart LR
    NET([Internet]) --> GW

    subgraph PVE[Proxmox VE host]
        GW{{nftables gateway}}
        GW --> MGMT[Management zone<br/>Terraform · Ansible]
        GW --> SVC[Services zone<br/>application workloads]
        GW --> MON[Monitoring zone<br/>Prometheus · Grafana · Loki · Wazuh]
        GW --> ATK[Simulation zone<br/>failure & attack tests]
    end

    SVC -. metrics & logs .-> MON
    ATK -. generates events .-> SVC
    MON -. alerts .-> MGMT
```

<sub>Default-deny between zones; every allowed flow is explicit, logged, and monitored.</sub>

</details>

---

<a id="methodology"></a>
## `$ cat ./methodology`

<table>
<tr>
<td align="center" width="25%"><h3>🔧</h3><strong>Build</strong><br/><sub>Infrastructure as code, reproducible from scratch</sub></td>
<td align="center" width="25%"><h3>🔍</h3><strong>Understand</strong><br/><sub>Trace packets, read logs, learn why it works</sub></td>
<td align="center" width="25%"><h3>🛡️</h3><strong>Secure</strong><br/><sub>Segment, harden, and enforce least privilege</sub></td>
<td align="center" width="25%"><h3>📈</h3><strong>Improve</strong><br/><sub>Break it on purpose, measure, iterate</sub></td>
</tr>
</table>

---

<a id="toolbox"></a>
## `$ cat ./toolbox`

<table>
<tr>
<td width="28%"><strong>Infrastructure & automation</strong></td>
<td><img src="https://skillicons.dev/icons?i=linux,bash,docker,ansible,terraform,git&perline=8" alt="Linux, Bash, Docker, Ansible, Terraform, Git"/></td>
</tr>
<tr>
<td><strong>Virtualization & network</strong></td>
<td>
<img src="https://img.shields.io/badge/Proxmox%20VE-E57000?style=for-the-badge&logo=proxmox&logoColor=white" alt="Proxmox VE"/>
<img src="https://img.shields.io/badge/nftables-334155?style=for-the-badge&logo=linux&logoColor=white" alt="nftables"/>
</td>
</tr>
<tr>
<td><strong>Security & observability</strong></td>
<td>
<img src="https://skillicons.dev/icons?i=prometheus,grafana" alt="Prometheus, Grafana"/>
<img src="https://img.shields.io/badge/Wazuh-SIEM-5C4EE5?style=for-the-badge" alt="Wazuh SIEM"/>
<img src="https://img.shields.io/badge/Loki-Logs-F5A623?style=for-the-badge&logo=grafana&logoColor=white" alt="Grafana Loki"/>
</td>
</tr>
<tr>
<td><strong>Software development</strong></td>
<td><img src="https://skillicons.dev/icons?i=java,python,django,mysql,postgres&perline=8" alt="Java, Python, Django, MySQL, PostgreSQL"/></td>
</tr>
</table>

---

<a id="activity"></a>
## `$ git log --stat`

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=YOUNES0101&show_icons=true&include_all_commits=true&count_private=true&hide_border=true&bg_color=0D1117&title_color=58A6FF&icon_color=58A6FF&text_color=C9D1D9&rank_icon=github" alt="GitHub stats"/>
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUNES0101&layout=compact&langs_count=6&hide_border=true&bg_color=0D1117&title_color=58A6FF&text_color=C9D1D9" alt="Most used languages"/>

<img src="https://streak-stats.demolab.com?user=YOUNES0101&hide_border=true&background=0D1117&ring=58A6FF&fire=58A6FF&currStreakLabel=58A6FF&sideLabels=C9D1D9&dates=8B949E&currStreakNum=E6EDF3&sideNums=E6EDF3&stroke=30363D" alt="GitHub contribution streak"/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/YOUNES0101/YOUNES0101/output/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/YOUNES0101/YOUNES0101/output/github-snake.svg" />
  <img src="https://raw.githubusercontent.com/YOUNES0101/YOUNES0101/output/github-snake-dark.svg" alt="Contribution graph animation" />
</picture>

</div>

---

<a id="connect"></a>
<div align="center">

## `$ ssh younes@connect`

<a href="https://github.com/YOUNES0101"><img src="https://img.shields.io/badge/GitHub-Explore%20my%20work-161B22?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/></a>
<a href="https://www.linkedin.com/in/YOUR-LINKEDIN-HANDLE/"><img src="https://img.shields.io/badge/LinkedIn-Let's%20connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>

<br/><br/>

<sub><code>Build it. Understand it. Secure it. Improve it.</code></sub>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:164E63,100:0D1117&height=100&section=footer" alt=""/>

</div>
