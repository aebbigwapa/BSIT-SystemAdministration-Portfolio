# Week 2 Portfolio Project — Enterprise Infrastructure Planning for a Startup Company

**Course:** ITEP 414 – System Administration and Maintenance
**Program:** Bachelor of Science in Information Technology
**Institution:** Laguna State Polytechnic University
**Prepared by:** [Student Name]

---

## 📌 Project Overview

Every successful IT infrastructure begins with proper planning. Before purchasing computers, installing servers, configuring networks, or deploying cloud services, a System Administrator must first understand the organization's business requirements and design an infrastructure that supports business operations.

In this project, I assumed the role of a **Junior System Administrator** assigned to prepare the initial IT Infrastructure Plan for a newly established startup company, **ABC Startup Solutions**. The final deliverable, [`EnterpriseInfrastructurePlan.pdf`](./EnterpriseInfrastructurePlan.pdf), is written as a professional document suitable for submission to an IT Manager or company executive.

## 🎯 Learning Objectives

**Knowledge**
- Explain the roles and responsibilities of a System Administrator.
- Identify the hardware, software, and networking requirements of a small business.
- Describe the purpose of IT documentation and infrastructure planning.

**Skills**
- Analyze organizational IT requirements.
- Prepare professional IT inventories.
- Design an enterprise network topology.
- Create technical documentation using Markdown.
- Present infrastructure planning professionally.

**Attitude**
- Professionalism · Organization · Technical communication · Attention to detail · Critical thinking

## 🏢 Company Scenario

**ABC Startup Solutions** is a newly established software development company with **20 employees** across a single office floor, and **no existing IT infrastructure** (no computers, server, network, internet, or security policies).

| Department | Employees |
|---|---|
| Information Technology | 5 |
| Human Resources | 4 |
| Finance | 5 |
| Sales | 6 |
| **TOTAL** | **20** |

The task: design the company's complete IT infrastructure from scratch — hardware, software, network, topology, staffing roles, and security recommendations.

## 🖥️ Hardware Inventory Summary

| Category | Highlights |
|---|---|
| Desktops | 9 units (HR & Finance) |
| Laptops | 11 units (IT & Sales) |
| Server | 1 tower server (Ubuntu Server) |
| Networking | Router, 24-port switch, 2 Wireless APs |
| Peripherals | 2 printers, 20 monitors |
| Resilience | 3 UPS units, 1 NAS, 2 external backup drives |

Full inventory with Asset IDs, quantities, departments, and justifications is in **Part 2** of the [Enterprise Infrastructure Plan](./EnterpriseInfrastructurePlan.pdf).

## 💽 Software Inventory Summary

Windows 11 Pro · Ubuntu Server 22.04 LTS · Microsoft 365 · VS Code · Git · GitHub Desktop · VirtualBox · Google Chrome · Microsoft Defender · AnyDesk · 7-Zip

Full software table with versions, licenses, and purpose is in **Part 3** of the plan.

## 🌐 Embedded Network Diagram

![ABC Startup Solutions Network Topology](./diagrams/network_diagram.png)

The topology flows: **Internet → ISP Modem → Router → Firewall → Core Switch → Wireless AP / Server / Printer / Department LAN segments (IT, HR, Finance, Sales)**.

Exported files: [`network_diagram.png`](./diagrams/network_diagram.png) · [`network_diagram.pdf`](./diagrams/network_diagram.pdf)

## 🛠️ Technologies Used

- **Markdown** — technical documentation (this README)
- **Node.js (docx library)** — generated the formatted Word/PDF report
- **SVG / vector graphics** — network topology diagram (draw.io-style)
- **GitHub** — version control and portfolio hosting
- **LinkedIn** — professional publication of the project summary

## 🚧 Challenges Encountered

The most challenging part of this project was designing the network diagram — translating a flat equipment list into a diagram that clearly shows both physical connectivity and logical traffic flow, from the internet connection down to each department's segment, while keeping it readable and properly labeled with standard networking symbols.

## 💭 Reflection

This project reinforced how closely hardware, software, and network decisions depend on one another, and why planning on paper — before any equipment is purchased — saves far more time, money, and downtime than fixing mistakes after deployment. The full reflection (300–500 words) is in **Part 8** of the [Enterprise Infrastructure Plan](./EnterpriseInfrastructurePlan.pdf).

## 📚 References

- CompTIA. *A+, Network+, and Linux+ Certification Overviews.* [https://www.comptia.org](https://www.comptia.org)
- Cisco. *CCNA Certification.* [https://www.cisco.com/certifications](https://www.cisco.com/certifications)
- Red Hat. *RHCSA Certification.* [https://www.redhat.com/certification](https://www.redhat.com/certification)
- Amazon Web Services. *AWS Certified Cloud Practitioner.* [https://aws.amazon.com/certification](https://aws.amazon.com/certification)
- Microsoft. *Microsoft 365 and Windows 11 Pro Documentation.* [https://learn.microsoft.com](https://learn.microsoft.com)
- Ubuntu. *Ubuntu Server Documentation.* [https://ubuntu.com/server/docs](https://ubuntu.com/server/docs)

---

📁 **Repository structure:**
```
BSIT-SystemAdministration-Portfolio/
└── Week02/
    ├── EnterpriseInfrastructurePlan.pdf
    ├── README.md
    ├── diagrams/
    │   ├── network_diagram.png
    │   ├── network_diagram.pdf
    │   └── network_diagram.svg
    ├── images/
    └── references/
```

#SystemAdministration #InfrastructurePlanning #Networking #GitHub #BSIT #LearningInPublic
