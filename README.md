# Noir

Aplicación tipo Jira para gestionar proyectos, tareas e incidencias.

## Estructura

| Carpeta     | Qué es                                                        |
|-------------|---------------------------------------------------------------|
| `backend/`  | API en Node.js + Express + Prisma (PostgreSQL). Puerto 3000.  |
| `frontend/` | Interfaz en React + Vite + Tailwind.                          |

El historial de commits de los repos originales (`Backend` y `Frontend`) se ha conservado.

## Arrancar en local

### Backend

```bash
cd backend
cp .env.example .env   # y rellena DATABASE_URL y JWT_SECRET
npm install
npx prisma migrate deploy
npm run seed
npm run dev
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

El frontend usa `VITE_API_BASE_URL` para saber dónde está la API (por defecto `http://localhost:3000/api`).

## Docker

Cada carpeta tiene su propio `Dockerfile`:

```bash
docker build -t noir-backend ./backend
docker build -t noir-frontend --build-arg VITE_API_BASE_URL=http://localhost:3000/api ./frontend
```
