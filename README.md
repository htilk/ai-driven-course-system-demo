# AI-Driven Course System (Backend Analytics Demo)

This repository contains a full-stack, team-based AI tutoring platform developed during my undergraduate capstone project at Arizona State University.

The system integrates course content from Canvas LMS and leverages retrieval-augmented generation (RAG) along with OpenAI’s ChatGPT Edu integration to provide an interactive AI tutoring experience. Students can engage with a chatbot interface for guided learning, while the platform uses a FastAPI backend, Next.js frontend, and PostgreSQL (pgvector) to support analytics and reporting on student performance.

---

## 🧠 My Contributions

I designed and implemented the backend analytics and reporting subsystem, focusing on transforming raw student performance data into structured, actionable insights for instructors.

Key contributions include:

- Developed RESTful analytics endpoints to compute:
  - Average scores per module
  - Course completion rates
  - Top and bottom performing students
- Designed and implemented a service-layer architecture to separate API routing from business logic and data aggregation
- Built CSV and PDF export pipelines for instructor-facing reports using structured data formatting and document generation (ReportLab)
- Created a seeded data pipeline to simulate realistic student performance data for testing and demonstration
- Designed database models for students and performance tracking, enabling efficient querying and aggregation
- Integrated PostgreSQL queries with FastAPI endpoints to support efficient and scalable data retrieval

---

## 📂 Key Files (My Work)

These files represent the core of my contributions:

- `backend/app/api/analytics.py` — FastAPI endpoints for analytics queries and report export (CSV/PDF)
- `backend/app/api/add_student_scores.py` — Endpoint for seeding and inserting structured student performance data
- `backend/app/services/analytics_service.py` — Service-layer logic for aggregating scores, computing metrics, and preparing report data
- `backend/app/models/domain_models.py` — SQLAlchemy data models defining students, scores, and relationships for analytics queries

---

## 🚀 Demo Overview

This demo highlights the backend analytics system via Swagger UI.

### 1. Seed Data

`POST /api/seed-data`

Populates the database with realistic student and module performance data.

---

### 2. Analytics Endpoints

`GET /analytics/averages`  
Returns average scores per course module

`GET /analytics/completion`  
Returns completion rates across modules

`GET /analytics/leaders`  
Returns top and bottom performing students

---

### 3. Report Export

`GET /analytics/export/csv`  
Generates a structured CSV report of analytics data

`GET /analytics/export/pdf`  
Generates a formatted PDF report for instructor use

---

## 🏗️ Architecture Overview

The backend follows a layered architecture:

- **API Layer (`api/`)** — FastAPI route definitions and request/response handling
- **Service Layer (`services/`)** — Business logic and data aggregation
- **Data Layer (`models/` + PostgreSQL)** — ORM models and persistent storage

This separation improves maintainability, scalability, and clarity of responsibilities across the system.

---

## 🛠️ Tech Stack

- **Backend:** FastAPI, Python
- **Frontend:** Next.js, React, Tailwind
- **Database:** PostgreSQL + pgvector
- **ORM:** SQLAlchemy
- **DevOps:** Docker, Docker Compose
- **AI Integration:** OpenAI ChatGPT Edu, RAG-based retrieval system

---

## ⚙️ Running the Project

### Prerequisites

- Docker
- Docker Compose

### Run the full stack

```bash
docker compose up --build