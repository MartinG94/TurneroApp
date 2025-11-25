# TurneroApp 🩺📅

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=fff)
![FastAPI](https://img.shields.io/badge/FastAPI-async-009688?logo=fastapi&logoColor=fff)
![SQLModel](https://img.shields.io/badge/SQLModel-ORM-336791)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-DB-4169E1?logo=postgresql&logoColor=fff)
![React](https://img.shields.io/badge/React-Vite-61DAFB?logo=react&logoColor=000)
![TailwindCSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4?logo=tailwindcss&logoColor=fff)
![Docker](https://img.shields.io/badge/Docker-ready-2496ED?logo=docker&logoColor=fff)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Estado](https://img.shields.io/badge/Estado-en%20desarrollo-orange)

> Sistema integral de gestión de turnos médicos para administradores, médicos y recepcionistas.

---

## 🌟 Qué es TurneroApp
Plataforma web que organiza pacientes, turnos, especialidades, usuarios y roles con flujos claros para frontdesk y médicos. Pensada para clínicas que necesitan control granular de agendas y permisos.

## 🎯 Principales funcionalidades
- Gestión de pacientes, médicos y especialidades.
- Agenda de turnos con disponibilidad por médico y especialidad.
- Control de roles y permisos (admin, médico, recepcionista) con JWT.
- Panel para recepción (check-in, reprogramación, cancelaciones).
- Panel médico (lista de turnos, historial de pacientes).
- Auditoría básica y trazabilidad de acciones.
- API REST bien tipada con FastAPI + Pydantic/SQLModel.

## 🧑‍🤝‍🧑 ¿Para quién?
- **Administradores:** configuración de usuarios, roles, especialidades.
- **Médicos:** administración de agenda y atención de turnos.
- **Recepcionistas:** asignación y gestión diaria de turnos y pacientes.

## 🏗️ Arquitectura general
- **Frontend:** React + Vite + TailwindCSS.
- **Backend:** FastAPI con SQLModel/SQLAlchemy y Pydantic.
- **DB:** PostgreSQL.
- **Autenticación:** JWT con roles.
- **Contenedores:** Docker + docker-compose (WSL2 en desarrollo).

```mermaid
flowchart LR
    subgraph Client [Frontend (React/Vite/Tailwind)]
        UI[SPA]
    end

    subgraph API [Backend (FastAPI)]
        Auth[JWT Auth]
        Services[Servicios / Casos de uso]
        ORM[SQLModel/SQLAlchemy]
    end

    subgraph DB [PostgreSQL]
        Pac[pacientes]
        Med[medicos]
        Esp[especialidades]
        ME[medico_especialidad]
        Tur[turnos]
        Usu[usuarios]
        Rol[roles]
        UR[usuario_roles]
    end

    UI -->|HTTPS| API
    API -->|Consultas/Mutaciones| ORM
    ORM --> DB
    Auth --> UI
```

## 🧰 Tecnologías
- Backend: Python 3, FastAPI, SQLModel/SQLAlchemy, Pydantic.
- Frontend: React + Vite + TailwindCSS.
- Base de datos: PostgreSQL.
- Autenticación: JWT (roles admin/médico/recepcionista).
- Contenedores: Docker + docker-compose.
- Infra: WSL2 (Windows dev), Git + GitHub.

## 📂 Estructura del proyecto
- `frontend/`: app React (Vite, TailwindCSS).
- `backend/`: API FastAPI, modelos y servicios.
- `infrastructure/`: definición de docker-compose, envs y scripts de despliegue.

## ✅ Requisitos previos
- Python 3.10+
- Node.js 18+ y pnpm/npm
- Docker y docker-compose
- WSL2 (Windows) habilitado
- Git

## 🚀 Puesta en marcha (cuando Docker esté listo)
```bash
# Clonar
git clone https://github.com/<org>/TurneroApp.git
cd TurneroApp

# Variables de entorno
cp .env.example .env

# Levantar stack
docker-compose up --build

# Frontend: http://localhost:5173
# Backend docs: http://localhost:8000/docs
```

## 🧱 Roadmap
- [ ] CRUD completo de pacientes, médicos, especialidades.
- [ ] Agenda dinámica por médico/especialidad.
- [ ] Panel recepcionista con check-in y reprogramación.
- [ ] Panel médico con historial y notas clínicas.
- [ ] Notificaciones (email/SMS) para recordatorios de turnos.
- [ ] Auditoría y logs de acciones.
- [ ] Despliegue continuo (CI/CD) y monitoreo.

## 🖼️ Screenshots
- Dashboard (placeholder)
- Agenda médica (placeholder)
- Perfil de paciente (placeholder)

## 🤝 Cómo contribuir
1. Haz fork y crea una rama: `feature/lo-que-sea`.
2. Sigue el estilo de código y linting del proyecto.
3. Agrega pruebas cuando apliquen.
4. Haz PR con descripción clara y screenshots si corresponden.

## 🐞 Reportar errores
- Crear un issue en GitHub con:
  - Descripción breve
  - Pasos para reproducir
  - Comportamiento esperado vs actual
  - Capturas o logs relevantes

## 📜 Licencia
MIT. Ver `LICENSE`.
