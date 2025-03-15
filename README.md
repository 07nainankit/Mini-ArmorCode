# Mini ArmorCode-Style Application

A multi-tenant security findings management platform featuring dashboards, scanning, ticketing, and runbook automation. This project is inspired by ArmorCode's approach, showcasing how to unify scanning, triage, and ticket creation under a single system.

## Table of Contents

- [Features](#features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Setup & Installation](#setup--installation)
- [Usage](#usage)
- [Screenshots / Demo](#screenshots--demo)
- [License](#license)

## Features

1. **Google Auth** – Single sign-on using OAuth.
2. **Tenant Management** – Switch across multiple tenants from the profile page.
3. **Dashboard** – Real-time charts using Recharts. Drill down on metrics to see relevant findings.
4. **Findings Page**:
   - Filter by severity, status, or tool.
   - Trigger scans & remove old scans.
   - Create tickets from findings & update statuses (dismiss, fix, confirm).
5. **Tickets Page** – Lists all tickets, with a link to GitHub/Jira integration, plus direct navigation to relevant findings.
6. **Runbook**:
   - Graphical builder using React Flow to define triggers (like “New Scan”), filters (severity, state), and actions (create ticket, update state).
   - Allows for automated flows.

## Architecture

- **Frontend**:
  - **React.js** with **Ant Design** for UI components.
  - **Recharts** for interactive data visualizations (Pie, Bar, Line charts).
  - **React Flow** for runbook node-based automation builder.
  - **Google OAuth** integration for user login.
- **Backend**:
  - **Spring Boot** microservices for authentication, scanning, ticketing logic.
  - **MySQL** for relational data (tenants, user info, tickets).
  - **Elasticsearch** for large scale searching & indexing findings.
  - **Kafka** as the messaging layer for asynchronous job flow (scanning, parsing, etc.).
- **Separate Modules**:
  - `auth-server` for user authentication and Google SSO handshake.
  - `job-flow-control` to manage runbooks & job triggers.
  - `background-job-handler` to process scanning or updates in the background.
  - `parser` to parse scan results & store them in Elasticsearch.

A simplified diagram might be:

<img width="1486" alt="Mini armorcode" src="https://github.com/user-attachments/assets/11aeab48-7879-4281-b852-0a2b67538c85" />


## Tech Stack

- **Frontend**: 
  - React, Ant Design, Recharts, React Flow, JavaScript/TypeScript (if used).
- **Backend**: 
  - Spring Boot (JPA, Security), MySQL, Kafka, Elasticsearch.
- **Deployment**: 
  - Optionally Docker, or local environment with Node / Java / Kafka / MySQL / ES.

## Setup & Installation



**Explanation**:

- Summaries of the **Features** and **Architecture** help new contributors or interviewers quickly see the scope of the project.
- The **Setup & Installation** section clarifies prerequisites and steps to run.
- The **Usage** doc helps them navigate the key pages.
- A **Screenshots / Demo** section is perfect for a short video or images to highlight the UI.

---

### Summary

- **On your Resume**: Provide key bullet points emphasizing multi-tenant scanning, real-time dashboards, runbook automation, plus highlight the tech stack.
- **In an Interview**: Focus on the architecture, design decisions, event-driven approach with Kafka, usage of Elasticsearch for search, and the UI flow with React-based integrations.
- **README**: Provide a user-friendly overview, instructions, a quick architecture diagram, and a place to embed or link to a demo video.

These steps ensure anyone reading your resume, hearing you in an interview, or checking your GitHub can fully grasp your mini “ArmorCode” platform’s capabilities.

