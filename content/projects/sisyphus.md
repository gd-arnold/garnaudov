---
title: "Sisyphus"
date: "2025-05-03"
summary: "Simple Habit Tracker"
description: "Simple Habit Tracker"
autonumber: false
math: true
hideBackToTop: false
---

[![GitHub Repository](https://img.shields.io/badge/GitHub-sisyphus-blue?style=for-the-badge&logo=github)](https://github.com/gd-arnold/sisyphus)

[![Live Demo](https://img.shields.io/badge/Live-Demo-green?style=for-the-badge&logo=world)](https://sisyphus.garnaudov.com)

# Sisyphus - Simple Habit Tracker

A minimalist habit tracking app for building consistency with daily progress visualization.

![sisyphus in action](images/sisyphus.png)

## Live Demo

🌐 **[Try sisyphus](https://sisyphus.garnaudov.com)** - Start tracking your habits!

## Tech Stack

### Backend (Node.js/Express API)
- **Express.js** - RESTful API server
- **Prisma ORM** - Database management with PostgreSQL
- **JWT Authentication** - Secure user sessions
- **Joi Validation** - Request validation middleware
- **bcrypt** - Password hashing

### Frontend (React SPA)
- **React 18** - Component-based UI
- **Zustand** - State management
- **React Router** - Client-side routing
- **Tailwind CSS** - Styling
- **Lucide React** - Icon library

### DevOps & Infrastructure
- **Docker** - Multi-stage containerized builds
- **GitHub Actions** - Automated CI/CD pipelines with path-based triggers
- **Digital Ocean** - Container registry and hosting
- **Kubernetes** - Production orchestration with GitOps deployment
- **Nginx** - Static file serving and reverse proxy

## Architecture

- **Monorepo Structure** - Separate `/api` and `/client` directories
- **RESTful API Design** - Clean endpoint structure with proper HTTP methods
- **Database Relationships** - User → Habits → HabitLogs (one-to-many cascade)
- **CI/CD Pipelines** - Separate automated workflows for API and client deployments
  - Path-based triggers (`api/**` and `client/**`)
  - Database migration automation in production
  - Automatic Docker image building and registry push
  - GitOps K8s manifest updates with commit SHA tagging
- **Migration System** - Prisma database migrations with deployment pipeline

## Key Features

- **Visual Progress Tracking** - 365-day contribution-style grid
- **Real-time Updates** - Instant habit logging with confetti animations
- **Responsive Design** - Mobile-first approach with desktop optimization
- **User Authentication** - Secure registration and login system
- **CRUD Operations** - Full habit and log management

**🌐 [Try Sisyphus](https://sisyphus.garnaudov.com)** | **🔗 [View the Complete Source Code](https://github.com/gd-arnold/sisyphus)**
