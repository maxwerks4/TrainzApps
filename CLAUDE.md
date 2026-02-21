# CLAUDE.md — Trainz Apps

This file guides Claude Code when building apps for the **Trainz Apps** project.

---

## Project Purpose

This repository contains tools and apps that enhance **Trainz Plus** (the latest subscription version of Trainz Railroad Simulator by N3V Games). Apps focus on:

- **Route & session planning** — tools to help design, organize, and manage Trainz routes and driving sessions
- **Asset management** — utilities to work with Trainz assets, KUID lists, content manager exports, and installed content

---

## Who I Am

I am a **vibe-coder** — I describe what I want in plain language and Claude writes all the code. I do not write code myself.

- **Write all code yourself** — never ask me to write or edit code manually
- **Explain what you're building** as you go, in plain English — I want to understand what's being created
- **Define technical terms** the first time you use them
- **Point out any decisions** I should understand (e.g. why a particular approach was chosen)
- **Keep things simple** — prefer straightforward solutions over clever or complex ones
- **Avoid jargon** without explanation
- When a task is complete, tell me exactly what command(s) to run to use the app

---

## Language & Technology Choices

- Let Claude choose the best language for each task (no strong preference)
- Prefer languages with **easy setup on Windows** since I run Windows locally
- **Python** is a good default for scripts and utilities — it's beginner-friendly and widely supported
- For any UI, prefer **simple web-based interfaces** (HTML + a small Python or Node server) or **desktop-friendly tools** over complex frameworks
- Avoid technologies that require heavy configuration or DevOps knowledge to run locally

---

## Trainz-Specific Context

- **Target platform:** Trainz Plus (latest version, N3V Games)
- **Key Trainz concepts to be aware of:**
  - **KUID** — unique identifier for every Trainz asset (format: `<KUID:creator_id:asset_id>` or `<KUID2:...>`)
  - **CDP** — Trainz content package file format
  - **Content Manager (CM)** — the Trainz built-in tool for managing installed assets
  - **Config.txt** — the metadata file inside every Trainz asset
  - **Routes & Sessions** — a Route is the map/layout; a Session is a scenario played on a Route
  - **Surveyor** — the Trainz map editor
  - **Driver** — the Trainz gameplay mode

- When working with Trainz data files, assume they are exported from **Content Manager** or **Surveyor** unless told otherwise
- Trainz file paths on Windows are typically under `C:\Users\<username>\Documents\N3V Games\Trainz Plus\`

---

## Code Style & Standards

- Write **clean, readable code** with comments explaining what each section does
- Use **descriptive variable names** (e.g. `asset_kuid` not `ak`)
- Keep files small and focused — one file per tool or feature where possible
- Include a **README or usage instructions** in every app subfolder
- Prefer **plain text or CSV** for data storage unless a database is clearly needed
- When reading or writing Trainz-exported files, handle encoding carefully (Trainz files may use UTF-8 or Windows-1252)

---

## Repository Structure

Each app lives in its own subfolder:
Trainz-Apps/
├── CLAUDE.md ← this file
├── README.md ← project overview
└── apps/
├── asset-manager/ ← asset management tools
├── route-planner/ ← route & session planning tools
└── ... ← future apps


## How to Run Apps (General)

- Each app folder will have its own `README.md` with setup and run instructions
- For Python apps: `python app.py` (or as directed in the app README)
- Assume the user is running **Windows 11** and has **Python installed**
- Do not assume Docker, WSL, or any advanced tooling is available unless confirmed

---

## Things to Avoid

- Do not use complex build systems (Webpack, CMake, Gradle) unless absolutely necessary
- Do not require a database for simple tasks — use files instead
- Do not generate code without explaining what it does
- Do not skip error handling — if something goes wrong, the app should print a clear, friendly message
- Do not assume familiarity with the command line — provide exact commands to run

---

## Session Startup Checklist

At the start of each coding session, Claude should:

1. Ask what app or feature we are working on today
2. Check if there is an existing subfolder for it, or if we are starting fresh
3. Confirm the goal in plain English before writing any code

