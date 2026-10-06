<!--
  GitHub Profile • Vo Thanh Nhan (@NhanVT24)
  Style: Cloud-native editorial / midnight + cyan + amber
  Original SVG artwork lives in ./assets/ and is included with this README.
-->

<div align="center">
  <img src="./assets/banner.svg" alt="Vo Thanh Nhan — Fullstack Engineering, AWS Serverless and Event-driven Systems" width="100%" />

  <p>
    <a href="https://github.com/NhanVT24?tab=repositories"><img src="https://img.shields.io/badge/PROJECTS-View%20my%20work-087E8B?style=for-the-badge&logo=github&logoColor=white" alt="Browse GitHub projects" /></a>
    <a href="https://github.com/NhanVT24/dynamoDB"><img src="https://img.shields.io/badge/FEATURED-AWS%20Supermarket-D99B35?style=for-the-badge&logo=amazonaws&logoColor=white" alt="Featured AWS project" /></a>
  </p>

  <p><strong>Software Engineering Intern · Fullstack Developer · AWS Serverless Enthusiast</strong></p>
  <p><em>From UI interactions to database writes, event delivery, and production operations.</em></p>
</div>

---

## 👋 A little about me

I'm **Võ Thành Nhân**, a software engineering student at the **University of Information Technology (VNU-HCM)**, based in Vietnam. I enjoy building end-to-end applications while going deeper into the backend decisions that make software reliable.

I am especially interested in **AWS serverless architectures**, **DynamoDB data modeling**, **event-driven workflows**, and the trade-offs around **consistency, cost, scalability, and observability**.

```typescript
const nhan = {
  role: "Software Engineering Intern",
  focus: ["Fullstack Engineering", "AWS Serverless", "Event-driven Systems"],
  currentlyBuilding: "Positive Social Network",
  learning: ["System Design", "Reliable Messaging", "Cloud Operations"],
  mindset: "Build → Validate → Observe → Improve",
} as const;
```

> **What I care about:** understandable architecture, dependable data flows, and systems that are practical to maintain — not just features that work in a demo.

## 🧰 Engineering toolkit

### Languages & frontend

<p>
  <img src="https://skillicons.dev/icons?i=ts,js,react,nextjs,html,css,tailwind&theme=dark" alt="TypeScript, JavaScript, React, Next.js, HTML, CSS, Tailwind" />
</p>

### Backend & data

<p>
  <img src="https://skillicons.dev/icons?i=nodejs,nestjs,express,mongodb,mysql,dynamodb&theme=dark" alt="Node.js, NestJS, Express, MongoDB, MySQL, DynamoDB" />
</p>

### Infrastructure & developer tools

<p>
  <img src="https://skillicons.dev/icons?i=aws,docker,git,github,postman,figma,vscode&theme=dark" alt="AWS, Docker, Git, GitHub, Postman, Figma, VS Code" />
</p>

**AWS services I've worked with / explored in projects**

![Lambda](https://img.shields.io/badge/Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white)
![API Gateway](https://img.shields.io/badge/API%20Gateway-8247E5?style=flat-square)
![DynamoDB](https://img.shields.io/badge/DynamoDB-4053D6?style=flat-square&logo=amazondynamodb&logoColor=white)
![SQS](https://img.shields.io/badge/SQS-FF4F8B?style=flat-square)
![EventBridge](https://img.shields.io/badge/EventBridge-8C4FFF?style=flat-square)
![Cognito](https://img.shields.io/badge/Cognito-D63AFF?style=flat-square)
![S3](https://img.shields.io/badge/S3-569A31?style=flat-square&logo=amazons3&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-C77700?style=flat-square)
![AWS CDK](https://img.shields.io/badge/AWS%20CDK-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![CloudWatch](https://img.shields.io/badge/CloudWatch-9D3AE3?style=flat-square)

<details>
<summary><strong>More about my technical interests</strong></summary>

| Area | Topics |
|:--|:--|
| API & backend | NestJS / Fastify, request validation, authentication, REST design |
| Data integrity | DynamoDB access patterns, GSIs, atomic updates, optimistic locking |
| Messaging | EventBridge, SQS, DynamoDB Streams, retries, idempotency, DLQs |
| Cloud delivery | AWS CDK, CloudFormation, S3 / CloudFront, IAM, monitoring |
| Product engineering | Responsive UI, reusable components, accessibility, maintainability |

</details>

---

## 🚀 Featured projects

### 01 — 🛒 Supermarket Shopping Platform

**A fullstack commerce system with an AWS serverless backend and real operational workflows.**

This is my main architecture-focused project. It covers much more than products and checkout: the repository includes a customer storefront, admin console, authorization, payment processing, background workers, audit trails, and infrastructure code.

- Built a **Next.js 15 / React 19** customer storefront and admin experience with **TypeScript** and **Tailwind CSS**.
- Organized a **NestJS 11 + Fastify** backend into business modules, with **API Gateway and Lambda** entrypoints.
- Used **DynamoDB** for core business entities, including access-pattern-oriented keys and conditional operations.
- Integrated **Amazon Cognito**, **VNPAY** payment/return/IPN flows, **SES**, and **S3** storage.
- Implemented asynchronous flows with **EventBridge, SQS FIFO, workers, retries, and DLQs**.
- Built an audit pipeline from **DynamoDB Streams → EventBridge Pipes → SQS → Lambda → audit table**, including conditional writes for duplicate-event protection.
- Defined infrastructure in **AWS CDK** and documented the deployment path across **API, CloudFront, S3, Route 53, and ACM**.

`Next.js` `NestJS` `TypeScript` `DynamoDB` `AWS Lambda` `EventBridge` `SQS` `Cognito` `VNPAY` `CDK`

[**📁 Source code**](https://github.com/NhanVT24/dynamoDB) · [**🧾 Audit pipeline details**](https://github.com/NhanVT24/dynamoDB/blob/main/docs/audit-log-stream.md) · [**☁️ Deployment notes**](https://github.com/NhanVT24/dynamoDB/blob/main/docs/deploy-stacks.md)

<details>
<summary><strong>Architecture spotlight — audit events and at-least-once delivery</strong></summary>

<img src="./assets/event-pipeline.svg" width="100%" alt="DynamoDB Streams through EventBridge Pipes and SQS FIFO to a Lambda audit worker" />

The worker uses conditional writes to avoid storing a duplicate audit record when an event is retried. The system documents failure queues, replay behavior, source metadata, and deployment ordering.

</details>

---

### 02 — 📈 GO Assignment · Exam Score Explorer

**A searchable exam-results dashboard with statistics, visualizations, and containerized development.**

- Developed a **React + Vite** interface and a **Node.js / Express** backend connected to **MongoDB**.
- Added exam-number lookup, score distributions, subject-level charts, and top-performing students for a selected subject group.
- Implemented CSV import/sync workflows and documented REST endpoints.
- Added **Docker Compose** configurations for development and production-style local runs.
- Built a responsive interface for desktop and mobile.

`React` `Vite` `Express` `MongoDB` `Chart.js` `Tailwind CSS` `Docker`

[**📁 Source code**](https://github.com/NhanVT24/GO-assignment) · [**🌐 Frontend demo**](https://go-ass.vercel.app/)

---

### 03 — 📱 iPhone 17 Pro Max · Product Experience

**A product storytelling interface focused on polished frontend interactions.**

- Developed the landing page with **React, Vite, and Tailwind CSS**.
- Added **English / Vietnamese** language switching and responsive light/dark themes.
- Created scroll-reveal interactions and lazy-loaded media.
- Integrated an interactive **Sketchfab 3D comparison** experience.

`React` `Vite` `Tailwind CSS` `Responsive Design` `3D Interaction`

[**📁 Source code**](https://github.com/NhanVT24/HELICORP-SanPham)

---

### 04 — ✅ ToList · React Task Manager

**A small project with deliberate attention to state handling and testability.**

- Implemented CRUD, completion state, search, filters, sorting, and pagination.
- Separated data/state logic into a custom **React hook** and reusable UI components.
- Validated inputs and handled malformed or blocked **localStorage** safely.
- Wrote unit tests for validation, filtering, sorting, and stored-data handling.

`React` `Vite` `Tailwind CSS` `Node.js Test Runner` `localStorage`

[**📁 Source code**](https://github.com/NhanVT24/SRT-Group-Test)

---

### 05 — 🌱 Positive Social Network · In Development

**A personal social platform centered on meaningful interactions and positive content.**

The evolving project scope includes a feed, profiles, friendships, messaging, notifications, short-form content, and user-focused discovery features. I am using it to practice **feature-oriented frontend structure, API boundaries, social data modeling, and cloud architecture**.

`React` `TypeScript` `Social Features` `API Design` `AWS Exploration`

> **Status:** Work in progress. A public repository/demo link will be added when available.

<details>
<summary><strong>More repositories</strong></summary>

- [**Personal Portfolio**](https://github.com/NhanVT24/personal-portfolio) — responsive portfolio UI and animations.
- [**Web Systems Development Labs**](https://github.com/NhanVT24/23521092-VoThanhNhan-IE213.Q21) — MongoDB, Express, React, fullstack exercises.
- [**Frontend Bookstore Exercise**](https://github.com/NhanVT24/Test-FE-EZ) — reusable vanilla JavaScript components and responsive multi-page UI.

</details>

---

## 🧩 How I think about backend systems

I like reasoning about the failure path, not only the happy path. The Supermarket project has helped me explore questions such as:

| Engineering question | Approach explored |
|:--|:--|
| **Can two checkout requests oversell stock?** | DynamoDB conditional updates and optimistic concurrency controls |
| **What if a webhook arrives twice?** | Signature verification, persisted payment state, and idempotent processing paths |
| **What if a worker fails midway?** | SQS retry behavior, DLQs, and replay / recovery considerations |
| **How do you trace a data change?** | DynamoDB Streams, audit-event metadata, whitelisted changes, actor context |
| **Does a CDK deployment update the website?** | Separating stack deployment from static asset upload and CloudFront invalidation |
| **What is the cost of this design?** | Reviewing serverless request, duration, storage, and event-delivery trade-offs |

```text
                        THE WAY I BUILD

  Requirements ──► Access patterns ──► API & data model
       │                 │                    │
       ▼                 ▼                    ▼
  Edge cases ───► Consistency rules ───► Async workflows
       │                 │                    │
       ▼                 ▼                    ▼
  Testing ──────► Observability ────────► Cost & operations
```

---

## 💼 Experience & education

**Software Engineering Intern — INNOMIZE** · *2026*

- Gaining hands-on experience with real-world software development practices and backend/cloud engineering concepts.
- Strengthening my approach to code organization, API design, AWS services, and reliable systems.

**University of Information Technology (VNU-HCM)** · *Information Technology*

- Academic projects and independent practice in web development, software engineering, and backend fundamentals.

---

## 📊 GitHub activity

<div align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=NhanVT24&theme=github_dark" alt="GitHub contribution overview" width="98%" />
  <br />
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=NhanVT24&theme=github_dark" alt="Repository language distribution" height="165" />
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=NhanVT24&theme=github_dark" alt="Most committed languages" height="165" />
  <br />
  <img src="https://streak-stats.demolab.com/?user=NhanVT24&theme=github-dark-blue&hide_border=true" alt="GitHub contribution streak" />
</div>

<sub>Statistics are generated by external services. They may be temporarily unavailable and do not necessarily represent private or work-related contributions.</sub>

---

<div align="center">
  <h3>Build it. Understand it. Keep it reliable.</h3>
  <p>Thanks for stopping by — explore the code and the engineering decisions behind it.</p>
  <a href="https://github.com/NhanVT24?tab=repositories">Repositories</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/NhanVT24/dynamoDB">Featured system</a>
  <br /><br />
  <img src="https://komarev.com/ghpvc/?username=NhanVT24&style=flat-square&color=087E8B&label=Profile+views" alt="GitHub profile views" />
</div>
