Yesterday 10:02 PM
for my repo why its showing failure 

Yep, the screenshot tells us where it failed, but not yet why.

What your GitHub Actions screenshot actually proves

The workflow got through:

✅ Set up job
✅ Initialize containers
✅ Checkout repository
✅ Set up JDK 21
✅ Grant Maven Wrapper permissions
❌ Run Full Maven Verification Suite

And that step is running:

./mvnw clean verify -B

So this is not a Docker failure and not a GitHub checkout problem. GitHub successfully got your repo and started Maven.

The actual error is below the part visible in your screenshot. The lines shown are just Maven downloading dependencies. The useful part will be near the bottom of that failed step, usually something like:

[ERROR] Tests run: ...
[ERROR] Failures: ...

or

Caused by: ...

or

APPLICATION FAILED TO START
One important thing

Your local report says:

212 tests, 0 failures, 0 errors

So if the exact same commit passes locally but CI fails, I would not start randomly changing code. That is how projects acquire twelve new problems while fixing one imaginary problem. 😭

The likely categories are:

CI environment/configuration difference
Database/service readiness
A test depending on environment variables
A test behaving differently in GitHub's Linux environment
A test timeout
Maven verification invoking something your local test run doesn't

And notice your workflow specifically runs:

clean verify

while your latest local verification report you showed earlier mentioned:

.\mvnw.cmd test

Those aren't identical operations.

Do this right now

Open the failed Run Full Maven Verification Suite section in GitHub Actions and scroll all the way to the bottom.

Copy the last ~50-100 lines, especially everything containing:

[ERROR]
FAILURE
Tests run
Failures
Errors
Caused by

Send me that.

Don't change anything yet.

Once we see the actual Maven error, I'll tell you exactly whether it's a workflow problem, test problem, environment problem, or something else. Your repository isn't "broken" just because GitHub slapped a red X on it. We need the corpse report before performing surgery. 🕵️‍♂️

Pasted markdown(20260906-163458).md
File
check

Yep. I checked the profile URL, but GitHub's page itself isn't exposing the README contents to my web fetch right now, so I can't honestly critique the exact current sections without seeing the file.

But I can give you the direction I'd use, and importantly, yes, you should absolutely include your best projects and live links.

GitHub itself recommends using the profile README to introduce yourself, show skills, and highlight your best projects, and specifically recommends pinning 3–5 strong repositories rather than dumping your entire life history onto the page.

What I want your profile to communicate

A recruiter should understand this within ~20 seconds:

Who is this guy? → What does he build? → What does he know? → Can I actually see his work?

Not:

"Here are 47 technology logos I copied from a README generator in 2022." 💀

Recommended structure
Hero / Introduction
        ↓
What I'm building
        ↓
Tech stack
        ↓
Featured projects
        ↓
Live projects / demos
        ↓
GitHub stats (optional)
        ↓
Currently learning
        ↓
Contact / links
Your projects

Don't list every project.

Use:

⭐ RecallMemoryBot → flagship project
GitHub
Live bot
Admin panel/live deployment if appropriate
2–4 other genuinely good projects
Smaller/unfinished experiments can stay in GitHub without occupying prime real estate.

GitHub specifically recommends showcasing your best work and pinning 3–5 repositories.

Definitely include live links

For a project like RecallMemoryBot, this is much stronger:

RecallMemoryBot
Production-deployed Telegram memory assistant
GitHub · Live Bot · Admin Panel

than:

RecallMemoryBot
Java Spring Boot project 🤓

A working demo is evidence. A paragraph saying "I know Spring Boot" is merely a human making claims, our oldest tradition.

🔥 Give Antigravity this prompt

This is the prompt I'd actually use. It tells it to audit what you already have instead of blindly adding flashy garbage.

You are now responsible for professionally redesigning and optimizing my GitHub Profile README.

Profile repository:
https://github.com/Thanniru-yaswanth03/Thanniru-yaswanth03

IMPORTANT:
Do NOT blindly add sections, badges, animations, statistics, technology logos, or generic developer-template content.

First inspect the CURRENT README and my public GitHub profile/repositories.

The goal is to make the profile look like a strong software-engineering portfolio that would impress:

recruiters
hiring managers
experienced engineers
interviewers reviewing my projects

The profile should feel personal, technically credible, clean, modern, and intentional.

Do NOT make it look like a generic "GitHub README generator" template.

STEP 1 — AUDIT THE CURRENT README

Read the entire existing README.

Identify:

strong sections worth keeping
weak sections
redundant sections
generic/template-like content
unnecessary badges
excessive animations
excessive emoji usage
empty sections
claims that aren't supported by my actual repositories
outdated information
broken links
unnecessary statistics
sections that make the profile harder to scan

Before changing anything, understand what is already there.

STEP 2 — INSPECT MY ACTUAL GITHUB WORK

Inspect my public repositories and identify the strongest projects.

Do NOT invent projects, technologies, achievements, experience, or skills.

Evaluate projects based on:

technical depth
real-world usefulness
completeness
deployment status
documentation
testing
architecture
engineering complexity
originality
relevance to software engineering roles

Prioritize projects that demonstrate actual engineering rather than simple tutorials or beginner exercises.

STEP 3 — FEATURED PROJECT STRATEGY

I want the profile to highlight my BEST projects, not every project I have ever created.

Recommend approximately 3–5 projects for the main profile showcase.

For each featured project, include where appropriate:

project name
one-line explanation
important technologies
what problem it solves
GitHub repository link
live/demo link if genuinely available

If a project has no meaningful demo or live deployment, do NOT fabricate one.

For RecallMemoryBot specifically, inspect the repository and use the actual available links.

Repository:
https://github.com/Thanniru-yaswanth03/RecallMemoryBot

Live deployment:
https://recallmemorybot.onrender.com/

If the live URL is appropriate to expose publicly, include it.

STEP 4 — PROFILE POSITIONING

Rewrite the introduction so it clearly communicates:

who I am
that I am an engineer/developer
what kinds of systems I build
the technologies I am actively working with
that I learn by building real projects

Keep it concise.

Do NOT use generic phrases such as:
"passionate developer"
"coding enthusiast"
"tech geek"
"turning coffee into code"
"building the future"
unless there is an actual reason they fit.

Make the introduction sound like a real engineer, not a motivational poster.

STEP 5 — TECH STACK

Create a clean, useful technology section.

Only include technologies that are genuinely supported by my repositories or that I am actively using.

Group them logically, for example:

Languages
Backend
Databases
AI / ML
DevOps / Infrastructure
Tools

Do not create a wall of 40+ technology icons.

Prioritize technologies that demonstrate actual project experience.

STEP 6 — CURRENTLY BUILDING / LEARNING

Add a short section showing what I am currently learning or building.

Only include things supported by my actual current work.

Keep it concise.

Do not turn this into a roadmap or life story.

STEP 7 — PROJECT PRESENTATION

Make the projects visually easy to scan.

Prefer something like:

RecallMemoryBot

Production-deployed Telegram memory assistant using Spring Boot, PostgreSQL, pgvector and OpenRouter.

GitHub · Live Demo

Then briefly mention the strongest engineering aspects.

Do NOT write huge paragraphs for every project.

STEP 8 — LIVE LINKS

I explicitly WANT useful live links where they exist.

Possible links include:

GitHub repository
live application
live Telegram bot
deployed Admin Panel
portfolio
LinkedIn
other legitimate demos

But do NOT include links merely because they exist.

Every link should have a purpose.

For RecallMemoryBot, consider:

GitHub:
https://github.com/Thanniru-yaswanth03/RecallMemoryBot

Live deployment:
https://recallmemorybot.onrender.com/

If the Telegram bot has a public username/link and it is appropriate, include it as well.

STEP 9 — GITHUB STATS

Evaluate whether GitHub contribution/stat cards actually improve the profile.

If they make the README cluttered, misleading, slow, or visually noisy, REMOVE them.

Do not add statistics simply because other developer profiles have them.

The profile should prioritize actual projects over vanity metrics.

STEP 10 — BADGES AND ANIMATIONS

Audit every badge and animation currently present.

Remove anything that:

adds no useful information
is redundant
makes the page look childish
is broken
depends on unreliable external services
creates visual clutter

A small number of tasteful visual elements are fine.

Do NOT turn the profile into a blinking dashboard from 2019.

STEP 11 — VISUAL DESIGN

Use GitHub-compatible Markdown and HTML where useful.

Aim for:

strong visual hierarchy
clean spacing
concise sections
readable typography
restrained emoji usage
professional project cards/tables where appropriate
good dark/light theme compatibility

You may use:

centered headers
tables
badges where meaningful
GitHub-supported images
collapsible sections when genuinely useful

Do not overdesign it.

STEP 12 — ACCURACY CHECK

Before finalizing:

Verify every claim against my actual repositories.

Do NOT claim:

technologies I haven't used
professional experience I don't have
achievements I haven't earned
users/scale I don't have
production systems that aren't actually deployed
certifications I don't have

If information is uncertain, either inspect further or omit it.

STEP 13 — DECIDE WHAT TO REMOVE

This is important:

If you believe an existing section is unnecessary, weak, repetitive, or actively makes the profile worse:

REMOVE IT.

Do not preserve something merely because it already exists.

Your responsibility is to make the final profile BETTER, not to preserve every piece of the old README.

If you remove something significant, explain why in your final report.

STEP 14 — FINAL PROFILE STRUCTURE

Use your judgment, but a strong final structure will probably resemble:

Header / introduction
What I build
Tech stack
Featured projects
Live projects / demos
Currently learning/building
Contact / social links

Do not force every section if the actual content does not justify it.

STEP 15 — FINAL REVIEW

Before finishing, inspect the rendered README mentally as if you were a recruiter opening my profile for the first time.

Ask:

Do I understand who this person is within 10 seconds?
Can I identify their strongest project immediately?
Can I access working demos?
Do their claimed skills match their actual work?
Does this look like an engineer's portfolio rather than a template?
Is there unnecessary content?
Is anything exaggerated?
Are the links correct?
Is it readable on both desktop and mobile?
Does the profile make me want to open one of the repositories?

If any answer is no, improve it.

IMPORTANT:
Do not push changes automatically.

First provide:

Your audit of the current README.
What you recommend keeping.
What you recommend removing.
What you recommend adding.
The proposed final structure.
Any questionable sections you think I should approve before removal.

Then, after that review, produce the final README.

One more thing I'd do

Don't make the profile README huge. GitHub's own documentation says the profile README is for presenting yourself and your work, while detailed project documentation belongs in the individual repository README.

So your profile should be the movie trailer, not the entire 14-hour director's cut. 🎬

For you specifically, I'd make RecallMemoryBot the centerpiece because it demonstrates substantially more than "I solved 300 LeetCode problems": backend architecture, Spring Boot, PostgreSQL, pgvector, semantic retrieval, AI integration, Telegram, Docker, CI, deployment, testing, security, and an admin interface. That's an actual system.

And yes, put your other strongest projects there, but selectively. Pin around 3–5, with RecallMemoryBot probably occupying the top spot. GitHub itself recommends that range for highlighting your best work.

Pasted markdown(20260907-062128).md
File
check now and generate prompt again

Yep. I checked the current public result I can access, but GitHub is being mildly useless about directly serving that exact profile page to me, so I’m not going to pretend I inspected content I couldn’t actually retrieve. Humanity survives another hallucination avoided. 😌

For your profile, yes, include projects and live links, but do not turn the README into a cemetery of every college project you've ever touched.

What I’d optimize for

Your profile should immediately communicate:

Who you are
What you build
What technologies you actually use
2–5 strongest projects
Live demos where they exist
GitHub/source links
What you're currently learning/building
Contact/LinkedIn

For RecallMemoryBot, definitely feature it prominently because it is much stronger than a generic CRUD/course project. You have an actual deployed system with Telegram integration, PostgreSQL + pgvector, RAG/semantic retrieval, Docker, CI, testing, an admin panel, and production deployment. That's portfolio material, not just "I made an app." 🔥

I'd also avoid stuffing the profile with fake-looking metrics, giant skill grids, 47 animated GIFs, visitor counters, or every technology you've touched once. Recruiters have suffered enough.

Final Anti-Gravity prompt

Give Anti-Gravity this as one prompt:

You are working on my GitHub profile README repository:

https://github.com/Thanniru-yaswanth03/Thanniru-yaswanth03

Your task is to thoroughly review the CURRENT state of my profile README and then improve it into a polished, professional, technically credible GitHub profile that represents me well for internships, software engineering roles, backend roles, and AI/ML-oriented opportunities.

IMPORTANT:
Do NOT blindly preserve everything that currently exists.
If something is unnecessary, repetitive, childish, misleading, outdated, visually noisy, or does not strengthen my profile, REMOVE it.
If something important is missing, ADD it.
Use your judgment as a professional portfolio reviewer.

Before editing:

Inspect the current README completely.
Inspect the repository structure and existing assets.
Inspect my public GitHub repositories where useful.
Identify my strongest projects based on technical depth, completeness, originality, deployment status, and demonstrable engineering work.
Do not invent achievements, technologies, experience, metrics, users, performance numbers, or credentials that are not supported by the repositories or existing profile information.
PROFILE POSITIONING

The README should position me as someone who:

Builds real software rather than only tutorials.
Is interested in backend engineering, AI systems, databases, automation, and deployment.
Learns systems deeply and builds projects from scratch.
Can take a project from implementation → testing → Docker → CI/CD → deployment.
Is actively improving as an engineer.

Keep the wording confident but factual.
Do not use exaggerated claims such as "expert", "10x engineer", "AI visionary", etc.

STRUCTURE

Create a clean hierarchy approximately like:

Hero / Introduction
About Me
Current Focus
Featured Projects
Technical Stack
Engineering Interests / What I Build
GitHub / Development Stats, only if they genuinely improve the profile
Connect With Me

You may change this structure if a better structure improves readability.

HERO SECTION

Create a concise introduction that immediately tells someone:

My name
My engineering focus
What kind of systems I build

Avoid a huge paragraph.

Use a small number of tasteful emojis if appropriate, but keep it professional.

ABOUT ME

Write a short, natural section describing:

My engineering interests
The kinds of systems I like building
My current learning direction
My preference for practical, production-oriented projects

Do not make generic claims such as "I am passionate about technology" unless supported by something more specific.

CURRENT FOCUS

Include a concise section describing what I am currently learning/building.

Prioritize areas such as:

Backend engineering
Java / Spring Boot
AI integrations
RAG / semantic search
PostgreSQL / pgvector
Docker
CI/CD
Cloud deployment
System design
Data structures and algorithms

Only include technologies that are actually relevant to my work.

FEATURED PROJECTS

This is one of the most important sections.

Do NOT list every repository.

Select approximately 3–6 of my strongest projects.

Prioritize projects based on:

Technical depth
Completeness
Real-world usefulness
Deployment/demo availability
Originality
Engineering complexity

For each featured project provide:

Project name
One-line explanation
Why it is interesting/useful
Important technologies
GitHub/source link
Live demo link when available

Use compact cards or a clean table if that produces a better result.

RECALLMEMORYBOT

Make RecallMemoryBot one of the primary featured projects.

Repository:
https://github.com/Thanniru-yaswanth03/RecallMemoryBot

Live deployment:
https://recallmemorybot.onrender.com/

Describe it accurately based on the actual repository.

Highlight its genuinely interesting engineering aspects, including where applicable:

Telegram bot integration
Persistent conversational memory
Semantic retrieval
PostgreSQL
pgvector
Embeddings
OpenRouter/LLM integration
Spring Boot
Docker
CI/CD
Integration and concurrency testing
Admin dashboard
Production deployment
Reliability/resilience testing

Do NOT claim unlimited scale or production traffic.
Do NOT claim hundreds/thousands of users.
Present it honestly as a deployed personal engineering project/demo.

Include both:

Source Code
Live Demo

If the live deployment is primarily a web/admin endpoint rather than a normal public website, label the link appropriately instead of pretending it is a conventional web app.

PROJECT SELECTION

Inspect my repositories and decide which projects deserve to be featured.

Do NOT include weak tutorial projects merely to increase the number of projects.

If a project is incomplete, abandoned, redundant, or substantially weaker than the featured projects, leave it out of the profile README.

The GitHub profile itself already exposes the full repository list, so the README does not need to duplicate every repository.

TECH STACK

Create a visually clean technology section.

Group technologies logically, for example:

Languages
Backend
Databases
AI / ML
DevOps / Infrastructure
Tools

Only include technologies that are supported by my actual projects or that I am genuinely working with.

Avoid listing 40 technologies simply because I have touched them once.

Prefer technologies demonstrated through projects over buzzwords.

LIVE PROJECT LINKS

Where a project actually has a working deployment, include a clearly labeled Live Demo / Live App link.

Where it does not have a live deployment, only include the GitHub repository.

Do not invent URLs.

Verify links before adding them.

GITHUB STATS

Evaluate whether GitHub stats, streaks, contribution graphs, profile views, or language cards actually improve the README.

If they add meaningful value, keep a minimal selection.

If they create visual clutter or make the profile look like a generic generated GitHub README, remove them.

Do not use excessive statistics.

VISUAL DESIGN

Make the README look modern and intentional.

Prefer:

Strong hierarchy
Good whitespace
Short sections
Consistent formatting
Useful badges only
Clean project cards/tables
Minimal tasteful emoji usage

Avoid:

Huge walls of text
Excessive badges
Fake-looking metrics
Giant skill icon collections
Multiple redundant stats widgets
Unnecessary animations
Generic motivational quotes
"Thanks for visiting my profile!!!" filler
Anything that makes the README look AI-generated
LINKS

Verify every external link.

Use:

GitHub repository links
Live deployment links
LinkedIn
Portfolio, if one exists
Email, if appropriate

Do not create fake links.

FINAL QUALITY CHECK

Before finishing, review the README as if you were:

A software engineering recruiter seeing it for 20 seconds.
A senior engineer reviewing the projects.
Someone clicking the featured projects.
Someone evaluating whether the claims are credible.

Fix anything that fails those checks.

The final README should communicate:

"I build real systems, I understand the engineering behind them, and I can take a project from idea to tested and deployed software."

It should NOT communicate:

"I collected every technology badge known to humanity."

IMPORTANT

You are authorized to modify the profile README and its supporting assets where appropriate.

Do not modify unrelated repositories or projects.

Do not invent information.

Do not remove useful existing information merely for cosmetic reasons.

If you believe an existing section is unnecessary, remove it rather than preserving it for the sake of completeness.

After making the changes:

Show me exactly what was changed.
Explain what you removed and why.
Explain which projects you selected and why.
Verify all project and live-demo URLs.
Run any available Markdown/link validation if practical.
Show the final README content.
Do NOT push to GitHub unless I explicitly tell you to push after reviewing the final result.
One important change from your earlier plan

Don't feature all your projects.

Your GitHub already shows the repository list. The profile README should act like a curated portfolio, not an archaeological record of every experiment you've ever committed. 😭

I'd aim for 4-ish strong projects, with RecallMemoryBot as the flagship. The live link makes it especially valuable because someone can actually click it and see that this isn't just a repository containing a heroic README.md and 14 TODOs.

Your GitHub profile
RecallMemoryBot repository
RecallMemoryBot live deployment

Pasted markdown(20260907-062550).md
File
its all good now i guess and give me a prompt for like more coolness and to make it look good best and all try your best to make it best and gimme the prompt

Absolutely. Since you said the current README is already good, the next prompt should tell Antigravity to polish it rather than blindly stuffing it with badges, animations, and the entire human history of your GitHub account. 😭

And yes, include your strongest projects + live links. Your profile README is a portfolio landing page, not a database dump. Put the projects that demonstrate what you can actually build.

🔥 Final "Make My GitHub README Insanely Good" Prompt
You are now doing a FINAL VISUAL + CONTENT POLISH pass on my GitHub profile README.

Repository:
https://github.com/Thanniru-yaswanth03/Thanniru-yaswanth03

IMPORTANT:
Do NOT blindly add more content just because it looks impressive.
The goal is a professional, modern, memorable GitHub profile that looks like it belongs to a serious software engineer.

First inspect the CURRENT README and the repositories/projects that are actually visible in my GitHub account.

Then improve the README based on what is genuinely useful.

==================================================
PRIMARY GOAL
==================================================

Make my GitHub profile README:

- visually impressive
- modern
- clean
- professional
- technically credible
- easy to scan
- recruiter/interviewer friendly
- memorable without being childish
- focused on things I actually built
- consistent with my current skill level
- not bloated

It should immediately communicate:

1. Who I am
2. What I build
3. What technologies I work with
4. My strongest projects
5. Where those projects can actually be seen
6. My GitHub / coding activity
7. How to contact me

==================================================
VERY IMPORTANT: AUDIT BEFORE EDITING
==================================================

Before changing anything:

1. Inspect the current README.
2. Inspect my repositories.
3. Identify my strongest projects.
4. Identify which projects have:
   - live deployments
   - GitHub repositories
   - demos
   - meaningful technical complexity
5. Check whether any existing links are broken.
6. Check whether any technologies listed in the README are not actually used.
7. Check whether any claims are exaggerated.
8. Remove outdated or redundant information.

If something is unnecessary, repetitive, cringe, misleading, or visually harmful:

REMOVE IT.

Do not preserve content merely because it already exists.

==================================================
PROJECT SHOWCASE
==================================================

Create a strong "Featured Projects" section.

Only include my best projects.

Prioritize projects that demonstrate:

- backend engineering
- AI/LLM integration
- databases
- system design
- APIs
- deployment
- Docker
- cloud
- security
- testing
- real-world problem solving

For each featured project, use a compact format containing:

Project Name
Short one-line description
Important technologies
What makes the project technically interesting
GitHub link
Live/demo link if available

Do NOT include every tiny experiment or tutorial project.

If I have a genuinely strong deployed project such as RecallMemoryBot, give it prominent placement.

==================================================
RECALLMEMORYBOT
==================================================

Pay special attention to RecallMemoryBot.

Repository:
https://github.com/Thanniru-yaswanth03/RecallMemoryBot

Live deployment:
https://recallmemorybot.onrender.com/

Present it as a serious real-world project.

Highlight relevant engineering aspects such as:

- Telegram bot
- Spring Boot
- PostgreSQL
- pgvector
- semantic search
- embeddings
- LLM integration
- OpenRouter
- Docker
- CI/CD
- automated testing
- concurrency handling
- resilience/retry behavior
- admin dashboard
- production deployment

Do not turn this into a giant paragraph.

Make it visually attractive and easy to understand.

Include both:

GitHub → source code
Live Demo → deployed application

If the live application has a meaningful public page, link it.

==================================================
TECH STACK
==================================================

Improve the technology section.

Group technologies logically rather than creating one enormous wall of icons.

For example:

Languages
Backend
Databases
AI / ML
DevOps / Cloud
Tools

Only list technologies that are genuinely relevant to my projects or that I can reasonably claim to know.

Do not add technologies just because they are popular.

Use recognizable icons/badges where appropriate, but avoid badge spam.

==================================================
VISUAL DESIGN
==================================================

Make the README visually polished.

Use:

- strong hierarchy
- clean section spacing
- tasteful emojis
- GitHub-compatible Markdown
- technology icons where useful
- project cards/tables only when they improve readability
- GitHub stats if they genuinely add value
- coding activity if useful
- contribution information if useful

Avoid:

- excessive GIFs
- giant animated banners
- dozens of badges
- meaningless visitor counters
- fake-looking statistics
- huge walls of text
- excessive quotes
- generic motivational statements
- "I'm passionate about..." filler
- cringe hacker aesthetics
- unnecessary ASCII art
- visual clutter

The design should feel like:

"serious engineer who knows how to build things"

not:

"person discovered GitHub badges yesterday."

==================================================
PROFILE INTRO
==================================================

Improve the opening section.

It should quickly communicate:

- my engineering identity
- what I enjoy building
- my current technical focus
- the type of problems I work on

Keep it concise.

Avoid generic introductions.

Make it sound like an actual human engineer rather than an AI-generated résumé.

==================================================
ENGINEERING FOCUS
==================================================

If appropriate, add a small section describing the areas I currently work on.

For example:

- Backend Engineering
- AI-powered applications
- Distributed / concurrent systems
- Databases & vector search
- API development
- Cloud deployment
- DevOps / Docker
- Software testing & reliability

Only include areas supported by my actual projects.

==================================================
GITHUB / CODING STATS
==================================================

Evaluate whether GitHub stats, streaks, top languages, contribution graphs, etc. actually improve the profile.

If they make the README better, include a small number of useful ones.

If they create clutter, remove them.

Do NOT add five different statistics widgets that all communicate the same thing.

==================================================
CONTACT / LINKS
==================================================

Create a clean contact section.

Include relevant links such as:

- GitHub
- LinkedIn
- portfolio if available
- email if appropriate
- coding platforms if genuinely useful

Use recognizable icons where possible.

Do not expose unnecessary personal information.

==================================================
LIVE PROJECT LINKS
==================================================

YES, include live links when they exist.

A recruiter/interviewer should be able to go:

GitHub Profile
→ Project
→ Source Code
→ Live Demo
→ README
→ Understand the architecture

within a few clicks.

For deployed projects, clearly distinguish:

[GitHub]
[Live Demo]

Do not include dead, broken, private, or inaccessible links.

Verify URLs before adding them.

==================================================
CONTENT QUALITY
==================================================

Rewrite awkward wording.

Fix grammar.

Remove repetition.

Remove claims that cannot be demonstrated.

Do not say:

"expert"
"master"
"10x engineer"
"future billionaire"
"AI wizard"

unless there is an actual reason to say it.

Let the projects prove the skill.

==================================================
MOBILE + DARK MODE
==================================================

Make sure the README remains readable on:

- desktop
- mobile
- GitHub dark mode
- GitHub light mode

Do not create extremely wide tables that become horrible on mobile.

==================================================
FINAL QUALITY CHECK
==================================================

After editing, inspect the final README as if you were:

1. A recruiter seeing it for 20 seconds.
2. A software engineer reviewing it.
3. An interviewer opening one of my projects.
4. Someone clicking the live demo.

Ask:

- Is the strongest project obvious?
- Are the live projects easy to find?
- Does it look professional?
- Does it show actual engineering ability?
- Is anything unnecessary?
- Is anything exaggerated?
- Are any links broken?
- Is it visually cluttered?
- Does it look better than the previous version?

If something does not improve the profile, remove it.

==================================================
IMPORTANT
==================================================

Do NOT modify my actual project source code.

Only modify the GitHub profile README unless a supporting profile asset is genuinely necessary.

Do not create unnecessary files.

Do not fabricate projects, technologies, statistics, achievements, certifications, deployments, or experience.

Use only information that can be verified from my GitHub repositories or information already present in the profile.

At the end, give me a concise summary of:

1. What you changed
2. What you removed
3. Which projects you featured and why
4. Which live links you added
5. Any questionable content you intentionally left out
6. Any remaining improvement you think would genuinely make the profile better

Then show me the final README content.
One thing I'd specifically keep

Your RecallMemoryBot should be the centerpiece. It's much more valuable to an interviewer to see:

Telegram bot → Spring Boot → PostgreSQL + pgvector → embeddings → semantic retrieval → LLM → Docker → CI/CD → deployed system

than 17 little repositories named JavaPractice, Calculator, HelloWorldFinalFinal2, because apparently humanity has decided GitHub must preserve every experiment forever. 😭

Your profile should communicate "I build systems", not merely "I know technologies."

<div align="center">

<!-- ================= HEADER BANNER ================= -->

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,40:0284c7,100:6366f1&height=220&section=header&text=YASH&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Full-Stack%20Software%20Engineer%20%7C%20System%20Architect&descFontSize=18&descAlignY=62" width="100%" alt="Header Banner" />

<!-- ================= ANIMATED TYPING SVG ================= -->

<a href="https://github.com/Thanniru-yaswanth03"> <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=38BDF8&center=true&vCenter=true&width=740&lines=%E2%9A%A1+Full-Stack+Software+Engineer+%26+System+Architect;%F0%9F%A7%A0+Creator+of+RecallMemoryBot+%26+TMR+Platform;%F0%9F%92%BB+MERN+Stack+%2B+TypeScript+%2B+Next.js+%2B+Python;%F0%9F%9A%80+Engineering+High-Performance+%26+Scalable+Web+Apps;%F0%9F%94%A5+Crafting+Clean+Architecture+%26+Frictionless+UX;%F0%9F%8C%99+Dark+Mode+Purist+%26+Problem-Solving+Artisan" alt="Typing SVG" /> </a>

<br><br>

<!-- ================= SOCIAL & QUICK LINKS BADGES ================= -->

<p align="center"> <a href="https://portfolio-roan-one-50.vercel.app/" target="_blank"> <img src="https://img.shields.io/badge/🌐%20Live%20Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=38bdf8" alt="Portfolio" /> </a> &nbsp; <a href="https://linkedin.com/in/thanniru-yaswanth-0a26b931a" target="_blank"> <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /> </a> &nbsp; <a href="mailto:yash1th2k4@gmail.com"> <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" /> </a> &nbsp; <a href="https://github.com/Thanniru-yaswanth03"> <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /> </a> </p>

<!-- ================= PROFILE VIEWS & STATUS TAGS ================= -->

<p align="center"> <a href="https://github.com/Thanniru-yaswanth03"> <img src="https://komarev.com/ghpvc/?username=Thanniru-yaswanth03&label=PROFILE+VIEWS&color=0ea5e9&style=for-the-badge&logo=eye&logoColor=white" alt="Profile Views" /> </a> &nbsp; <img src="https://img.shields.io/badge/Status-Shipping%20Production%20Code-0ea5e9?style=for-the-badge&logo=visualstudiocode&logoColor=white" alt="Status" /> &nbsp; <img src="https://img.shields.io/badge/Focus-Full--Stack%20%26%20Distributed%20Systems-6366f1?style=for-the-badge&logo=react&logoColor=white" alt="Focus" /> &nbsp; <a href="https://t.me/RecallMemoryBot" target="_blank"> <img src="https://img.shields.io/badge/🔥%20Latest%20Release-RecallMemoryBot-24A1DE?style=for-the-badge&logo=telegram&logoColor=white" alt="Latest Project" /> </a> </p>

</div>

<br>

<!-- ================= ANIMATED CYBER DIVIDER ================= -->

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" alt="divider" />

<br>

<!-- ================= ABOUT ME / TERMINAL SECTION ================= -->

🔮 whoami & Developer Identity
┌──(yash💻dev-core)-[~]
└─$ cat profile.json
{
  "name": "YASH",
  "alias": "Goat",
  "role": "Full-Stack Software Engineer & System Architect",
  "education": "B.Tech in CSE @ Parul University (2022-2026)",
  "domains": [
    "High-Performance Full-Stack Web Architecture (React 18, TypeScript, Node.js, Express, Next.js, Django)",
    "Scalable API Engineering, Microservices & Database Design (MongoDB, PostgreSQL, MySQL)",
    "Autonomous AI Agents, Vector Embeddings & Conversational Memory (Spring Boot 3.3, Java 21, pgvector)",
    "Enterprise Commercial Workspaces & Single-Operator CRM Platforms",
    "Modern Reactive UI/UX Engineering, Design Systems & State Management",
    "Cloud Deployments (Vercel, Render), CI/CD Workflows & Clean Architecture"
  ],
  "languages": ["JavaScript (ES6+)", "TypeScript", "Python", "Java", "C", "C++", "SQL", "Bash"],
  "latestRelease": "RecallMemoryBot (Autonomous Telegram AI Conversational Memory Engine)",
  "philosophy": "Write code so clean it reads like poetry; build architectures so resilient they scale effortlessly.",
  "funFact": "Dark mode isn't just a theme — it's an engineering standard. 🌙⚡"
}
⚡ Software Engineering Highlights
🎓 Education: Computer Science & Engineering at Parul University (2022 – 2026).
💼 Industry Experience: Full-Stack Developer Intern at Paithacs Software Solutions & Web Developer Intern at AICTE Oasis Infobyte.
🚀 Full-Stack Mastery: Specializing in end-to-end web engineering — crafting ultra-responsive frontends powered by modular, performant, and secure backends.
💡 Engineering Standards: Heavy emphasis on reusable component design, RESTful API architecture, type safety, and optimized database indexing.

<br>

<!-- ================= FEATURED LIVE PROJECTS SHOWCASE ================= -->

🚀 Featured Production Projects

<div align="center">

Project & Domain	Architecture & Engineering Highlights	Live Demo & Source

🧠 RecallMemoryBot
<sub>Autonomous Telegram AI Conversational Memory Engine</sub>

<img src="https://img.shields.io/badge/🚀%20NEW%20PROJECT-24A1DE?style=flat-square&logo=telegram&logoColor=white" alt="New Project" />	• Privacy-first intelligent Telegram group memory bot that passively captures chat history and indexes explicit decisions (/remember).
• Asynchronous vector embedding pipeline (text-embedding-3-small, 1536d) with hybrid semantic Q&A (/ask, /recall) powered by OpenRouter (Claude 3 Haiku) and PostgreSQL pgvector HNSW indexing.
• Strict anti-hallucination citation validation against real message IDs ([Msg #ID]), sliding-window rate limiting, and dedicated admin diagnostics web console (/admin/).

Java 21 Spring Boot 3.3 PostgreSQL pgvector OpenRouter Claude 3 Docker Telegram API Render Neon	
<a href="https://t.me/RecallMemoryBot" target="_blank"><img src="https://img.shields.io/badge/Live%20Telegram%20Bot-24A1DE?style=for-the-badge&logo=telegram&logoColor=white" alt="Live Telegram Bot" /></a>
<a href="https://recallmemorybot.onrender.com" target="_blank"><img src="https://img.shields.io/badge/Live%20Service-46E3B7?style=for-the-badge&logo=render&logoColor=white" alt="Live Service" /></a>
<a href="https://github.com/Thanniru-yaswanth03/RecallMemoryBot" target="_blank"><img src="https://img.shields.io/badge/GitHub%20Repo-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Repo" /></a>

🏢 TMR Business Platform
<sub>Enterprise Commercial & Operations Suite</sub>

<img src="https://img.shields.io/badge/⭐%20FLAGSHIP%20PROJECT-10b981?style=flat-square&logo=star&logoColor=white" alt="Flagship Project" />	• Full-stack commercial platform combining Hyderabad real estate brokerage with TS/AP RTO documentation consultancy.
• Dual client & single-operator architecture: smart WhatsApp lead dispatch, Zod-validated enquiries & private administrative operations portal.
• Secure token-based session auth, MongoDB indexing, rate-limiting, and 100% mobile-responsive design.

React 18 Node.js Express MongoDB Atlas TypeScript Tailwind CSS JWT Auth Vercel Render	
<a href="https://tmr-business-platform.vercel.app/" target="_blank"><img src="https://img.shields.io/badge/Live%20Platform-10B981?style=for-the-badge&logo=vercel&logoColor=white" alt="Live Platform" /></a>
<a href="https://github.com/Thanniru-yaswanth03/TMR-Business-Platform" target="_blank"><img src="https://img.shields.io/badge/GitHub%20Repo-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Repo" /></a>

📈 ProgressTracker
<sub>Full-Stack Productivity & Sprint Workspace</sub>	• Full-featured task orchestration, sprint tracking, and analytics dashboards.
• Secure JWT authentication, RESTful APIs, optimized MongoDB schemas & real-time updates.

React Node.js Express MongoDB JWT Auth REST API Vercel	
<a href="https://progress-tracker-three-pied.vercel.app/" target="_blank"><img src="https://img.shields.io/badge/Live%20App-38BDF8?style=for-the-badge&logo=vercel&logoColor=white" alt="Live App" /></a>
<a href="https://github.com/Thanniru-yaswanth03/ProgressTracker" target="_blank"><img src="https://img.shields.io/badge/GitHub%20Repo-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Repo" /></a>

✨ Interactive Portfolio
<sub>Modern Reactive Developer Showcase</sub>	• Blazing-fast portfolio built with modern frontend paradigms.
• Custom animations, mobile-first responsive design & clean modular code.

React Tailwind CSS Vite Framer Motion Vercel	
<a href="https://portfolio-roan-one-50.vercel.app/" target="_blank"><img src="https://img.shields.io/badge/Live%20Site-000000?style=for-the-badge&logo=vercel&logoColor=38bdf8" alt="Live Site" /></a>

🎯 Drag-n-Drop Workflow
<sub>Dynamic Kanban Engine</sub>	• Zero-latency drag-and-drop workspace with instant visual reordering.
• Complex UI state orchestration and fluid HTML5 drag event lifecycles.

JavaScript HTML5 Drag & Drop CSS3 Animations Vercel	
<a href="https://drag-n-drop-lilac.vercel.app/" target="_blank"><img src="https://img.shields.io/badge/Live%20App-6366F1?style=for-the-badge&logo=vercel&logoColor=white" alt="Live App" /></a>

📰 AI News Detection System
<sub>NLP & ML Classification Platform</sub>	• End-to-end machine learning platform predicting credibility in real time.
• Built with a high-throughput Django backend, feature extraction & Scikit-Learn models.

Python Django Scikit-Learn NLP Machine Learning JavaScript	
<a href="https://fakenewsdetectionsystem.pythonanywhere.com/" target="_blank"><img src="https://img.shields.io/badge/Live%20Demo-10B981?style=for-the-badge&logo=python&logoColor=white" alt="Live Demo" /></a>

</div>

<br>

<!-- ================= EXPERIENCE TIMELINE ================= -->

💼 Engineering Experience
┌── [Paithacs Software Solutions Pvt. Ltd.] ──────────────────────────────────────┐
│  💼 Role: Full-Stack Developer Intern                                           │
│  📅 Period: Jan 2026 – Apr 2026                                                 │
│  🛠️ Tech: React, Node.js, Express, MongoDB, RESTful APIs, Tailwind CSS           │
│  📌 Key Contributions:                                                          │
│     • Developed responsive frontend features with React and Tailwind CSS.       │
│     • Built RESTful API endpoints and integrated MongoDB schemas with indexing. │
│     • Optimized state management and reduced API response latency.              │
└─────────────────────────────────────────────────────────────────────────────────┘
┌── [AICTE Oasis Infobyte] ───────────────────────────────────────────────────────┐
│  🌐 Role: Web Developer Intern                                                  │
│  📅 Period: Dec 2024 – Jan 2025                                                 │
│  🛠️ Tech: Modern JavaScript, HTML5, CSS3, Responsive Design, Git/GitHub         │
│  📌 Key Contributions:                                                          │
│     • Engineered accessible, cross-browser interactive frontend interfaces.     │
│     • Implemented modular JavaScript logic and dynamic UI component behaviors.  │
└─────────────────────────────────────────────────────────────────────────────────┘

<br>

<!-- ================= TECH STACK & TOOLBOX ================= -->

🛠️ Tech Stack & Engineering Toolkit

<div align="center">

<!-- Core Languages -->

<p><b>💻 Core Programming Languages</b></p> <a href="https://skillicons.dev"> <img src="https://skillicons.dev/icons?i=ts,js,python,java,cpp,c,html,css" alt="Languages" /> </a> <br><br>

<!-- Frontend Development -->

<p><b>⚛️ Frontend & Reactive UI Frameworks</b></p> <a href="https://skillicons.dev"> <img src="https://skillicons.dev/icons?i=react,nextjs,tailwind,redux,vite,bootstrap,sass,figma" alt="Frontend Tools" /> </a> <br><br>

<!-- Backend & Database -->

<p><b>⚙️ Backend Engineering, Databases & Caching</b></p> <a href="https://skillicons.dev"> <img src="https://skillicons.dev/icons?i=nodejs,express,spring,django,mongodb,postgres,mysql,prisma,firebase" alt="Backend & DB" /> </a> <br><br>

<!-- DevOps & Cloud Tools -->

<p><b>🚀 Cloud Infrastructure, DevOps & Developer Tools</b></p> <a href="https://skillicons.dev"> <img src="https://skillicons.dev/icons?i=docker,git,github,postman,vscode,npm,vercel,bash,linux,ubuntu" alt="DevOps & Tooling" /> </a>

</div>

<br>

<!-- ================= GITHUB STATS & ANALYTICS ================= -->

📊 GitHub Telemetry & Activity Metrics

<div align="center">

<!-- Streak Stats (Demolab API) -->

<a href="https://github.com/Thanniru-yaswanth03"> <img src="https://streak-stats.demolab.com?user=Thanniru-yaswanth03&theme=tokyonight&hide_border=true&card_width=750" alt="GitHub Streak" /> </a>

<br><br>

<!-- Overall Stats & Top Languages Side-by-Side (Fast API) -->

<p align="center"> <a href="https://github.com/Thanniru-yaswanth03"> <img src="https://github-readme-stats-fast.vercel.app/api?username=Thanniru-yaswanth03&show_icons=true&theme=tokyonight&hide_border=true" alt="GitHub Stats" width="49%" /> </a> <a href="https://github.com/Thanniru-yaswanth03"> <img src="https://github-readme-stats-fast.vercel.app/api/top-langs/?username=Thanniru-yaswanth03&layout=compact&theme=tokyonight&hide_border=true" alt="Top Languages" width="49%" /> </a> </p>

</div>

<br>

<!-- ================= CONNECT & COLLABORATE ================= -->

🤝 Let's Connect & Build Together

<div align="center">

<p><b>Interested in full-stack engineering, scalable distributed web architecture, and building exciting products together!</b></p>

<br>

<a href="https://portfolio-roan-one-50.vercel.app/" target="_blank"> <img src="https://img.shields.io/badge/🌐%20Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=38bdf8" alt="Portfolio" /> </a> &nbsp; <a href="https://linkedin.com/in/thanniru-yaswanth-0a26b931a" target="_blank"> <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /> </a> &nbsp; <a href="mailto:yash1th2k4@gmail.com"> <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" /> </a> &nbsp; <a href="https://github.com/Thanniru-yaswanth03"> <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /> </a>

<br><br>

<!-- ================= FOOTER BANNER ================= -->

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,40:0284c7,100:6366f1&height=120&section=footer" width="100%" alt="Footer Banner" />

<sub><b><i>Built with 💙 by YASH • Architect. Build. Scale. 🚀</i></b></sub>

</div>

Close
