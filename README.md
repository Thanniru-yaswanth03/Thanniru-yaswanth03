<div align="center">

  <!-- ================= HEADER BANNER ================= -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,40:0284c7,100:6366f1&height=220&section=header&text=YASH&fontSize=52&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Software%20Engineer%20%7C%20Full-Stack%20%26%20Backend%20Systems&descFontSize=18&descAlignY=62" width="100%" alt="Header Banner" />

  <!-- ================= ANIMATED TYPING SVG ================= -->
  <a href="https://github.com/Thanniru-yaswanth03">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1000&color=38BDF8&center=true&vCenter=true&width=740&lines=%E2%9A%A1+Software+Engineer+%7C+Backend+%26+Full-Stack+Systems;%F0%9F%A7%A0+Creator+of+RecallMemoryBot+%28Java+21+%2B+Spring+Boot+%2B+pgvector%29;%F0%9F%8F%A2+Creator+of+TMR+Business+Platform+%28MERN+%2B+TypeScript%29;%F0%9F%9A%80+Engineering+Resilient+APIs%2C+Vector+Search+%26+Cloud+Deployments;%F0%9F%90%B3+Dockerized+Microservices+%7C+PostgreSQL+%7C+MongoDB+Atlas" alt="Typing SVG" />
  </a>

  <br><br>

  <!-- ================= SOCIAL & QUICK LINKS BADGES ================= -->
  <p align="center">
    <a href="https://portfolio-roan-one-50.vercel.app/" target="_blank">
      <img src="https://img.shields.io/badge/🌐%20Live%20Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=38bdf8" alt="Portfolio" />
    </a>
    &nbsp;
    <a href="https://linkedin.com/in/thanniru-yaswanth-0a26b931a" target="_blank">
      <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
    </a>
    &nbsp;
    <a href="mailto:yash1th2k4@gmail.com">
      <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" />
    </a>
    &nbsp;
    <a href="https://github.com/Thanniru-yaswanth03">
      <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
    </a>
  </p>

  <!-- ================= STATUS TAGS ================= -->
  <p align="center">
    <img src="https://img.shields.io/badge/Focus-Backend%20Engineering%20%26%20Vector%20Search-6366f1?style=flat-square&logo=target&logoColor=white" alt="Focus" />
    &nbsp;
    <a href="https://t.me/RecallMemoryBot" target="_blank">
      <img src="https://img.shields.io/badge/🔥%20Latest%20Project-RecallMemoryBot-24A1DE?style=flat-square&logo=telegram&logoColor=white" alt="Latest Project" />
    </a>
  </p>

</div>

<br>

---

## 👋 About Me

I am a **Software Engineer** focused on **backend services, full-stack web architecture, and AI-assisted data retrieval**. I enjoy designing robust, maintainable systems with clean data modeling, strong type guarantees, transactional reliability, and automated containerized deployments.

Currently pursuing a **B.Tech in Computer Science & Engineering** at **Parul University** (2022–2026), backed by professional internship experience engineering RESTful APIs, optimizing database queries, and shipping responsive web platforms.

### 🎯 Core Engineering Focus
- **Backend & API Engineering**: Architecting modular Spring Boot and Node.js/Express backends with strict validation, clean separation of concerns, and comprehensive test coverage.
- **AI Integration & Vector Search**: Building real-time semantic retrieval pipelines using `pgvector` with HNSW indexing, LLM grounding via OpenRouter, and programmatic citation verification.
- **Data Modeling & Storage**: Designing indexed, relational (PostgreSQL) and document (MongoDB Atlas) schemas optimized for query performance and data consistency.
- **DevOps & Cloud Deployment**: Packaging production microservices into lightweight multi-stage Docker images (<250 MB) and deploying on Render, Vercel, and Neon.

---

## 💼 Experience & Education

- **Full-Stack Developer Intern** · *Paithacs Software Solutions Pvt. Ltd.* *(Jan 2026 – Apr 2026)*
  - Engineered responsive, production-ready user interfaces using React and Tailwind CSS.
  - Implemented RESTful API endpoints and optimized MongoDB collection schemas with targeted indexing.
  - Streamlined client-side state handling to reduce redundant network round-trips and response latency.

- **Web Developer Intern** · *AICTE Oasis Infobyte* *(Dec 2024 – Jan 2025)*
  - Developed cross-browser interactive UI components leveraging modern ECMAScript standards and CSS3.
  - Collaborated via Git/GitHub version control workflows for issue tracking and code reviews.

- **B.Tech in Computer Science & Engineering** · *Parul University* *(2022 – 2026)*

---

## 🚀 Featured Production Projects

### 🧠 [RecallMemoryBot](https://github.com/Thanniru-yaswanth03/RecallMemoryBot) · Flagship AI & Backend Project
> **Autonomous, privacy-first Telegram conversational memory bot that indexes group chat streams, performs grounded semantic Q&A, and eliminates hallucinated citations.**

- **Architecture & Engineering Highlights**:
  - **Asynchronous Vector Pipeline**: Decouples message ingestion from vectorization via Spring Events, asynchronously computing 1536-dimensional embeddings with OpenAI's `text-embedding-3-small`.
  - **Grounded Semantic Retrieval**: Uses PostgreSQL 16 + `pgvector` HNSW cosine distance indexing (`m=16, ef_construction=64`) to retrieve contextual chat chunks for grounded synthesis through OpenRouter (Claude 3 Haiku).
  - **Anti-Hallucination Citation Verification**: Generated claims are strictly validated against real retrieved Telegram message IDs (`[Msg #ID]`); fabricated citations are programmatically scrubbed before delivery.
  - **Operational Reliability & Rate Limiting**: In-memory sliding-window token bucket rate limiter (per-user/per-group), atomic webhook deduplication (`telegram_updates` table, <50ms ack), and an authenticated admin operations web console (`/admin/`).
  - **Production Deployment**: Packaged into a non-root Alpine JRE Docker container (<250 MB) and deployed on Render with Neon Serverless PostgreSQL and Actuator health probes.
- **Tech Stack**: `Java 21` · `Spring Boot 3.3` · `PostgreSQL 16` · `pgvector` · `OpenRouter (Claude 3)` · `Docker` · `Telegram API` · `Render` · `Neon`
- **Links**:
  [![Source Code](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Thanniru-yaswanth03/RecallMemoryBot)
  [![Live Telegram Bot](https://img.shields.io/badge/Telegram-Live_Bot-24A1DE?style=flat-square&logo=telegram&logoColor=white)](https://t.me/RecallMemoryBot)
  [![Live Service Health](https://img.shields.io/badge/Render-Actuator_Health_UP-10B981?style=flat-square&logo=render&logoColor=white)](https://recallmemorybot.onrender.com/actuator/health)

<br>

### 🏢 [TMR Business Platform](https://github.com/Thanniru-yaswanth03/TMR-Business-Platform) · Enterprise Commercial Suite
> **Full-stack commercial platform combining real estate brokerage operations with official documentation consultancy.**

- **Architecture & Engineering Highlights**:
  - Dual-interface architecture serving public enquiry workflows and a private single-operator operations portal.
  - Automated WhatsApp lead dispatch with Zod-validated multi-step enquiry parsing.
  - Secure token-based session authentication and optimized MongoDB Atlas indexing for instant lead lookups.
- **Tech Stack**: `React 18` · `TypeScript` · `Node.js` · `Express` · `MongoDB Atlas` · `Tailwind CSS` · `JWT Auth` · `Vercel` · `Render`
- **Links**:
  [![Source Code](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Thanniru-yaswanth03/TMR-Business-Platform)
  [![Live Platform](https://img.shields.io/badge/Vercel-Live_Platform-10B981?style=flat-square&logo=vercel&logoColor=white)](https://tmr-business-platform.vercel.app/)

<br>

### 📈 [ProgressTracker](https://github.com/Thanniru-yaswanth03/ProgressTracker) · Sprint & Productivity Workspace
> **Task orchestration and sprint analytics platform engineered for workflow tracking and performance visibility.**

- **Architecture & Engineering Highlights**:
  - Full-featured sprint lifecycle management with task dependency tracking and velocity analytics.
  - Secure JWT authentication, structured RESTful API layers, and indexed MongoDB document schemas.
- **Tech Stack**: `React` · `Node.js` · `Express` · `MongoDB` · `JWT Auth` · `RESTful APIs` · `Tailwind CSS` · `Vercel`
- **Links**:
  [![Source Code](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Thanniru-yaswanth03/ProgressTracker)
  [![Live Application](https://img.shields.io/badge/Vercel-Live_App-38BDF8?style=flat-square&logo=vercel&logoColor=white)](https://progress-tracker-three-pied.vercel.app/)

<br>

### 🎯 [Drag-N-Drop Workflow](https://github.com/Thanniru-yaswanth03/Drag-N-Drop) · Dynamic Kanban Engine
> **High-performance Kanban workspace featuring zero-latency drag-and-drop state management and collision handling.**

- **Architecture & Engineering Highlights**:
  - Built with Next.js and `@dnd-kit` primitives, delivering accessible keyboard navigation and fluid animations.
  - Implements optimistic UI state updates and precise collision detection algorithms for frictionless task reordering.
- **Tech Stack**: `Next.js` · `React` · `TypeScript` · `dnd-kit` · `Tailwind CSS` · `Vercel`
- **Links**:
  [![Source Code](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Thanniru-yaswanth03/Drag-N-Drop)
  [![Live Application](https://img.shields.io/badge/Vercel-Live_App-6366F1?style=flat-square&logo=vercel&logoColor=white)](https://drag-n-drop-lilac.vercel.app/)

---

## 🛠️ Technical Skills & Arsenal

<div align="center">
  <img src="https://skillicons.dev/icons?i=java,spring,postgres,mongodb,ts,js,react,nextjs,nodejs,express,docker,git,bash,tailwind,py" alt="Core Tech Stack Icons" />
</div>

<br>

| Category | Technologies & Tools |
| :--- | :--- |
| **Languages** | `Java (21)` · `TypeScript` · `JavaScript (ES6+)` · `Python` · `SQL` · `C / C++` |
| **Backend & APIs** | `Spring Boot 3.3` · `Node.js` · `Express.js` · `RESTful APIs` · `JWT Auth` · `Hibernate / JPA` |
| **Databases & Vector** | `PostgreSQL` · `pgvector (HNSW Indexing)` · `MongoDB Atlas` · `MySQL` · `Index Optimization` |
| **AI & Search** | `OpenRouter` · `Claude 3 Haiku` · `text-embedding-3-small` · `Semantic Retrieval` · `Prompt Engineering` |
| **DevOps & Cloud** | `Docker` · `Render` · `Vercel` · `Neon (Serverless Postgres)` · `Git` · `GitHub Actions` · `Linux / Bash` |
| **Frontend & UI** | `React 18` · `Next.js` · `Tailwind CSS` · `Vite` · `Framer Motion` · `dnd-kit` · `HTML5 / CSS3` |
| **Testing & Tooling** | `JUnit 5` · `Spring Boot Test` · `Postman` · `VS Code` · `IntelliJ IDEA` · `Maven` |

---

## 📊 GitHub Analytics & Telemetry

<div align="center">
  <p align="center">
    <a href="https://github.com/Thanniru-yaswanth03">
      <img src="https://github-readme-stats-fast.vercel.app/api?username=Thanniru-yaswanth03&show_icons=true&theme=tokyonight&hide_border=true" alt="GitHub Stats" width="49%" />
    </a>
    <a href="https://github.com/Thanniru-yaswanth03">
      <img src="https://github-readme-stats-fast.vercel.app/api/top-langs/?username=Thanniru-yaswanth03&layout=compact&theme=tokyonight&hide_border=true" alt="Top Languages" width="49%" />
    </a>
  </p>
  <a href="https://github.com/Thanniru-yaswanth03">
    <img src="https://streak-stats.demolab.com?user=Thanniru-yaswanth03&theme=tokyonight&hide_border=true&card_width=750" alt="GitHub Streak" />
  </a>
</div>

---

## 🤝 Let's Connect

<div align="center">

  <p><b>Interested in backend engineering, scalable full-stack web architecture, or AI systems? Let's connect!</b></p>

  <br>

  <a href="https://portfolio-roan-one-50.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/🌐%20Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=38bdf8" alt="Portfolio" />
  </a>
  &nbsp;
  <a href="https://linkedin.com/in/thanniru-yaswanth-0a26b931a" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  &nbsp;
  <a href="mailto:yash1th2k4@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" />
  </a>
  &nbsp;
  <a href="https://github.com/Thanniru-yaswanth03">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  </a>

  <br><br>

  <!-- ================= FOOTER BANNER ================= -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,40:0284c7,100:6366f1&height=100&section=footer" width="100%" alt="Footer Banner" />

  <sub><b><i>Built with 💙 by YASH • Clean Architecture. Resilient Systems. Scale. 🚀</i></b></sub>

</div>
