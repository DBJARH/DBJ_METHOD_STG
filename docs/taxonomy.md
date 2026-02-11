---
layout: default
title: Taxonomy
description: Key organization communication aid
---
>**Note**
>
> Taxonomy concept is necessary knowledge to start "climbing" the [CMM Levels](cmm.md#levels-and-characteristics)
{: note}

# What is a Taxonomy?

>**Important**
>
> Taxonomy is Hierachycal structure describing the Organization Inormation Space
> 
> It is a Positioning System (OPS) of the Information Space. 
> 
> It is essential aid for communication, smooth development and quick information location.
{: important}

![alt text](taxonomy_assets/taxonomy-role-bw.png)


- A taxonomy is a hierarchical organizational structure across various domains
- In commercial enterprises it is used to solve business problems like improving data discovery, knowledge management, and content governance.
  - It provides a predefined classification system that categorizes technical assets, documentation, and resources from general to specific topics, enabling IT organizations to efficiently organize, locate, and reuse information.
- Taxonomy is Location Positioning System of the Information Space. 
- It is essential communication "aid" for cross disciplined activities 
- Simple well defined Taxonomy is applicable for various types of business activities, undertaken by various actors in the organization information space.
- Taxonomy is underlying mesh holding the organization information space together

### Iron Code Labs Enterprise Taxonomy (ICL ET)

IT Architecture Taxonomies represent structured organizational communication aid that cover various IT domains. Not presumably inside one organization.

#### Top Level
>
> Top level of ICL ET is made of four key categories ordered by level of abstractions they cover.
>
> 1. **Concepts** (foundational principles and business requirements)
> 2. **Logical** architecture (system designs and relationships)
> 3. **Physical** architecture (infrastructure and deployment models)
> 4. **Implementation** architecture (internal software technologies and deployment)

This top level, simple progression supports better decision-making and operational efficiency by creating intuitive pathways for information access, while helping organizations maintain consistency in how technical knowledge is classified, shared, and leveraged across different teams and systems. 


>**Common Terminology**
>
> Please note the overarching, technology neutral terminology. Taxonomy as a concept is applicable across various disciplines. Terminology for "anything" that can be defined and stored following the common logic of classification. 
> 

## ICL Enterprise Taxonomy Hierarchy

- As Organization IT Landscape Classification, ICL Taxonomy is essential for cataloguing, ordering and succinct communiction. 
- This is essential activity before any kind of feasible business development can start.
- As an organization architecture classification logic, taxonomy hierarchy is also essential for software product development management. 
- As it describes the information content location, of deliverables 
- Use the ICL ET as the simple primary source of truth in the organization
- ICL Eneteprise Taxonomy terminology are common crucial vocabulary
  - To share and use company wide
  - Key aid for smooth business/technology communications

![alt text](taxonomy_assets/taxonomy-role-bw.png)

## Structure
<strong>Taxonomy is a hierarchical structure. First level of the hierarchy we call "Categories", second level "Capabilities"</strong>

- Capabilities when added to four Categories are turning the simple list into full taxonomy.
- Taxonomy "category" together with its four "capability" siblings is a complete definition for a single category.
- Taxonomy defined in here is applicable to wide spectra of organization activities and roles performing those activities
  
---

<details markdown="1">
<summary><strong>Conceptual</strong></summary>

*Focuses on foundational aspects of software, emphasizes goals, data, functions, and technologies, serves as a high-level blueprint, ensures alignment with business objectives, organizes information effectively, delivers desired functionality, utilizes appropriate technologies, and establishes shared understanding among stakeholders.*

**Capabilities**

- **Business** — Defines the business goals and objectives that software is intended to support, focusing on aligning software with organizational strategy and desired outcomes.
- **Information** — Focuses on the data that software processes and manages, including its structure and relationships, ensuring data is structured to meet the needs of the organization and its processes.
- **Application** — Describes the specific functions and features of the software, such as user interfaces, data processing, and reporting, defining what the software does and how users interact with it.
- **Technology** — Outlines the underlying technologies used to build and operate the software, such as programming languages, databases, and operating systems, highlighting the technical foundation that supports the software's functionality.

</details>

<details markdown="1">
<summary><strong>Logical</strong></summary>

*Addresses structural and operational aspects of software, provides a detailed view of software functionality, covers data management strategies, includes system integrations, discusses software platform and security measures, bridges the gap between conceptual design and physical implementation, ensures seamless and secure interaction of components, and maintains a robust framework.*

**Capabilities**

- **Data Management** — Addresses how data is stored, accessed, and managed within the software, ensuring efficient handling and organization of data for various operations.
- **Integration** — Focuses on how the software interacts with other systems and applications, facilitating seamless communication between different software systems.
- **Platform** — Describes the software environment and infrastructure on which the software runs, providing a stable foundation to host and execute the software.
- **Security** — Defines the measures taken to protect the software and its data from unauthorized access and threats, safeguarding sensitive information and ensuring compliance with standards.

</details>

<details markdown="1">
<summary><strong>Physical</strong></summary>

*Focuses on tangible and technical resources, encompassing hardware, infrastructure, network communication, and storage systems. It ensures a stable, efficient, and scalable environment, addresses performance needs, and enables reliable data processing and connectivity.*

**Capabilities**

- **Compute** — Addresses the hardware resources used to run the software, such as servers and processors, providing the computational power necessary to execute the software.
- **Infrastructure** — Describes the physical environment in which the software operates, including data centers and network connections, supporting the software with physical and virtual infrastructure.
- **Network** — Focuses on the communication pathways used to connect the software components and users, ensuring connectivity and data exchange between systems and users.
- **Storage** — Defines how data is stored and retrieved, including the types of storage devices used, managing data storage to support both short-term and long-term requirements.

</details>

<details markdown="1">
<summary><strong>Implementation</strong></summary>

*Concerned with processes and practices for delivering, maintaining, and monitoring software, this approach includes deployment, development, monitoring, and operational activities. It ensures effective building and launching of software while sustaining it through continuous improvements. Additionally, it involves performance tracking and routine maintenance to meet evolving requirements.*

**Capabilities**

- **Deployment** — Addresses the process of installing and configuring the software on its target environment, ensuring smooth transition from development to production environments.
- **Development** — Describes the activities involved in designing, coding, and testing the software, transforming ideas and requirements into functional software.
- **Monitoring** — Focuses on tracking the performance and health of the software after deployment, identifying and resolving issues to maintain optimal performance.
- **Operations** — Addresses the ongoing management and maintenance of the software, including updates, backups, and incident response, keeping the software running reliably and efficiently over time.

</details>

---

## ICL Taxonomy Capability is the key KPI of an organization

#### Each Role is played by group of Actors, having the ability to manage various organization Capabilities

*Example: Ability of an organization to deploy Business Roles to communicate the "Business" capability of the "Conceptual" level, in order to architect, develop and maintain it.*


> **Note:** 
> 
> A capability is the ability or capacity of an organization, system, or individual to perform a specific task or achieve a desired outcome effectively and efficiently. It encompasses the resources, skills, processes, and technologies that enable the execution of activities to meet strategic objectives.
{: note}

> **Important:** 
> 
> Capabilities are defined here by the single common ICL Taxonomy of the  organization
{: important}

## Appendix

> Copy paste Taxonomy using ASCII char. For perusal in the documentation or code in the organization

```
├── Conceptual
│   ├── Business
│   ├── Information
│   ├── Application
│   └── Technology
├── Logical
│   ├── Data Management
│   ├── Integration
│   ├── Platform
│   └── Security
├── Physical
│   ├── Compute
│   ├── Infrastructure
│   ├── Network
│   └── Storage
└── Implementation
    ├── Deployment
    ├── Development
    ├── Monitoring
    └── Operations
```
