<div align="center">

<img src="frontend/public/logo.png" alt="Noir" width="110" />

# Noir

**Gestor de proyectos e incidencias tipo Jira**

Organiza proyectos, sprints y tareas en un tablero Kanban, trabaja en equipo y sigue el progreso con estadísticas.

![React](https://img.shields.io/badge/React_19-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-0F172A?style=for-the-badge&logo=tailwindcss&logoColor=38BDF8)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

</div>

---

## ✨ Funcionalidades

- 📋 **Tablero Kanban** con arrastrar y soltar. Estados: *Pendiente*, *En progreso*, *En revisión* y *Finalizado*.
- 🏃 **Sprints** para planificar el trabajo de cada proyecto.
- ✅ **Tareas y subtareas** con prioridad (*Baja*, *Media*, *Alta*, *Urgente*), responsable y fecha de vencimiento.
- 💬 **Comentarios y adjuntos** en cada tarea.
- 🏷️ **Etiquetas** para clasificar y filtrar.
- 👥 **Equipos con roles**: cada usuario tiene su rol dentro de cada equipo y existe un administrador global.
- 🔔 **Notificaciones** e **historial de actividad**.
- 📊 **Panel con estadísticas** y gráficas del progreso.
- 🔐 **Registro e inicio de sesión** con JWT y contraseñas cifradas con bcrypt.
- 🛠️ **Panel de administración** (`/admin`) para gestionar todos los datos.

## 🧱 Arquitectura

```
Noir/
├── backend/    API REST · Node.js + Express + Prisma (PostgreSQL) · puerto 3000
└── frontend/   Aplicación web · React + Vite + Tailwind CSS
```

| Capa | Tecnologías |
|------|-------------|
| Frontend | React 19, React Router, Tailwind CSS, dnd-kit (drag & drop), Chart.js, date-fns |
| Backend | Node.js, Express, Prisma ORM, Zod (validación), JWT, bcrypt, Multer (subida de archivos), EJS (panel admin) |
| Base de datos | PostgreSQL |
| Despliegue | Docker (backend en Node, frontend servido con Nginx) |

## 🚀 Puesta en marcha

### Requisitos

- Node.js 20 o superior
- PostgreSQL

### Backend

```bash
cd backend
cp .env.example .env   # rellena DATABASE_URL y JWT_SECRET
npm install
npx prisma migrate deploy
npm run seed           # datos de ejemplo
npm run dev
```

La API queda en `http://localhost:3000/api`.

### Frontend

```bash
cd frontend
npm install
npm run dev
```

El frontend usa la variable `VITE_API_BASE_URL` para saber dónde está la API (por defecto `http://localhost:3000/api`).

### Con Docker

```bash
docker build -t noir-backend ./backend
docker build -t noir-frontend --build-arg VITE_API_BASE_URL=http://localhost:3000/api ./frontend
```

## 👤 Autor

**Nicolau Negre Rodríguez** · [@NicoOmegaPro](https://github.com/NicoOmegaPro) · negrenicolau@gmail.com
