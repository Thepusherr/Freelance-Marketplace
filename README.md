# Freelance Marketplace API

Backend for a freelance service marketplace platform. Implements a full order lifecycle with state machine, role‑based access, reviews & ratings, email/in‑app notifications, and background jobs.

## Features

- **Authentication** — JWT (access/refresh), signup, login, logout
- **Roles** — client, freelancer, admin (Pundit policies)
- **Service catalog** — CRUD, full‑text search (pg_search), filters, pagination, image uploads (ActiveStorage)
- **Orders** — state machine (AASM: pending → accepted → in_progress → completed / cancelled / disputed), auto‑cancel after 48h (Sidekiq)
- **Notifications** — Noticed (in‑app) + ActionMailer, delivered via background jobs
- **Reviews & ratings** — allowed only after completed order, auto‑recalculation of service average rating
- **Freelancer profiles** — public profile with stats (total earnings, completed orders, avg response time)
- **Admin panel** — ActiveAdmin (manage users, services, disputes)
- **Audit log** — PaperTrail (order change history)
- **API documentation** — Swagger (rswag)

## Tech stack

- **Ruby on Rails 7.2** (API mode)
- **PostgreSQL** / **Redis**
- **Devise + JWT** / **Pundit**
- **Sidekiq** + **sidekiq‑cron**
- **AASM** / **Noticed** / **PaperTrail**
- **pg_search** / **Kaminari** / **ActiveStorage**
- **RSpec** / **FactoryBot** / **Shoulda Matchers**
- **Docker** + **docker‑compose**
- **GitHub Actions** (CI)
- **Render / Railway** (deployment)

## Quick start

```bash
git clone https://github.com/your-username/freelance-marketplace-api.git
cd freelance-marketplace-api
docker-compose up
