# Mini ArmorCode 🚀

A multi-tenant security findings management platform featuring dashboards, scanning, ticketing, and runbook automation. This project is inspired by ArmorCode's approach, showcasing how to unify scanning, triage, and ticket creation under a single system.

## Table of Contents 🗒️

- [Features](#features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Screenshots / Demo](#screenshots--demo)

## Features 🌟

1. **Google Auth** – Single sign-on using OAuth.
2. **Tenant Management** – Switch across multiple tenants from the profile page or user dropdown.
3. **Role Base Access** - Specified roles for users and controlled views, access to various features based on the role.
4. **Dashboard** – Real-time charts using Recharts to show useful insights. Drill down on metrics to see relevant findings.
5. **Findings Page**:
   - Filter by severity, status, or tool.
   - Trigger scans or remove old scans.
   - Create tickets from findings & update statuses (open, closed etc).
6. **Tickets Page** – Lists all tickets, with a link to GitHub/Jira integration, plus direct navigation to relevant findings.
7. **Runbook**:
   - Allows for automated flows.
   - Graphical builder using React Flow to define triggers (like “New Scan”), filters (severity, state), and actions (create ticket, update state).
   

## Architecture 🛠️

- **Separate Modules**:
  - `auth-server` for user authentication and authorization of requests. It is first point of contact for any request from frontend.
  - `job-flow-control` to manage all the jobs  like - Scan Job, Ticket Job, Update Job or Rubook Job etc, produced in the application based on the concurrency rules.
  - `background-job-handler` to process ticketing, updates and runbook jobs in the background.
  - `parser` to parse scan results to armorcode schema, also apply de-duplication algo & store them in Elasticsearch.

A simplified diagram might be:

<img width="1486" alt="Mini armorcode" src="https://github.com/user-attachments/assets/11aeab48-7879-4281-b852-0a2b67538c85" />


## Tech Stack 👨🏻‍💻

- **Frontend**:
  - **React.js** with **Ant Design** for UI components.
  - **Recharts** for interactive data visualizations (Pie, Bar, Line charts).
  - **React Flow** for runbook node-based automation builder.
  - **Google OAuth** integration for user login.
- **Backend**:
  - **Spring Boot** microservices for authentication, scanning, runbook, ticketing logic.
  - **MySQL** for relational data (tenants, user info, jobs, jira-config).
  - **Elasticsearch** for large scale searching & indexing findings.
  - **Kafka** as the messaging layer for asynchronous job flow (jfc, auth, parser, bg-jobs etc.).
- **Deployment**: 
  - Docker, and local environment with Node / Java / Kafka / MySQL / ES.


## Demo 🎥
<a href="https://drive.google.com/drive/folders/1Qt5lxD4JF53tgJD454I_h1Qe_Pi-5xsl?usp=sharing" target="_blank">
    <img width="20px" height="20px" src="https://github.com/user-attachments/assets/3b575ae3-a6cc-4f96-863c-05b8a8b6af6e" alt="logo">
     All demos !!!
</a>

   <a href="https://drive.google.com/file/d/1-vDj1tAgq67sBu_u_VhGzWMgLOWZ0um-/view?usp=sharing" target="_blank">
       <img width="20px" height="20px" src="https://github.com/user-attachments/assets/3b575ae3-a6cc-4f96-863c-05b8a8b6af6e" alt="logo">
        Login and Dashboard
   </a>
   
   <a href="https://drive.google.com/file/d/1oTQs0fbTNZEV1Aq9Or-NH60ioalmrciC/view?usp=drive_link" target="_blank">
       <img width="20px" height="20px" src="https://github.com/user-attachments/assets/3b575ae3-a6cc-4f96-863c-05b8a8b6af6e" alt="logo">
        Findings and RBAC
   </a>
   
   <a href="https://drive.google.com/file/d/12uRNtmzKv_vR4Ed-DfD3bxZKygYi162A/view?usp=drive_link" target="_blank">
       <img width="20px" height="20px" src="https://github.com/user-attachments/assets/3b575ae3-a6cc-4f96-863c-05b8a8b6af6e" alt="logo">
        Ticketing
   </a>
   
   <a href="https://drive.google.com/file/d/1HbR_0pss1sfx2QLfwjWF_3sKBeH0hVgU/view?usp=drive_link" target="_blank">
       <img width="20px" height="20px" src="https://github.com/user-attachments/assets/3b575ae3-a6cc-4f96-863c-05b8a8b6af6e" alt="logo">
         Runbooks
   </a>
   
   <a href="https://drive.google.com/file/d/1XYGdC9fqmBmmnVTa8CdWyd3pf2vMcZ3b/view?usp=drive_link" target="_blank">
       <img width="20px" height="20px" src="https://github.com/user-attachments/assets/3b575ae3-a6cc-4f96-863c-05b8a8b6af6e" alt="logo">
         JFC demo
   </a>




