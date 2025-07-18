# VincuSalud – Sistema de Gestión de Vinculación con la Sociedad

Aplicación web para la Facultad de Ciencias de la Salud orientada al control, seguimiento y reporte de las actividades de vinculación de estudiantes con la comunidad.

---

# Prototipado en Figma

Se ha iniciado el proceso de prototipado de la aplicación web para la Facultad de Ciencias de la Salud, y se continúa manteniendo reuniones con la Dra. Gabriela Castillo, coordinadora de proyectos de Vinculación. Durante estas sesiones, se están realizando las modificaciones necesarias para asegurar que el sistema cumpla con todos los requerimientos por los cuales fue solicitado. Una vez definidos con claridad los lineamientos y funcionalidades, se procederá con el desarrollo del software como tal.

<a href="https://www.figma.com/design/hbW2E7wOiCPJzaqRGRTWWi/Prototipado-Proyecto-de-Titulaci%C3%B3n-VincuSalud?node-id=0-1&t=jgqx8KYt8xwNHXAs-1" target="_blank">Enlace a Figma VincuSalud</a>

---

## Descripción General del Proyecto

VincuSalud es una plataforma desarrollada como parte de un proyecto de tesis, cuyo propósito es digitalizar y optimizar el proceso académico de vinculación en carreras como Medicina, Psicología, Fisioterapia, Odontología y Ciencias Biomédicas. El sistema permite a estudiantes, docentes tutores y administrativos registrar, consultar y supervisar las horas de vinculación de forma segura, organizada y trazable.

---

## Tecnologías Seleccionadas

Se eligieron herramientas modernas para garantizar escalabilidad, mantenibilidad y facilidad de desarrollo:

- Frontend:
  - React + TypeScript
  - Tailwind CSS + shadcn/ui
  - Vite (builder moderno)
- Backend:
  - Node.js + Express
  - Prisma ORM + PostgreSQL
  - Autenticación con JWT y bcrypt
- Base de Datos: PostgreSQL
- Control de versiones: Git + GitHub
- Despliegue (futuro): Vercel (frontend), Railway o Render (backend)

---

## Metodología de Desarrollo

Se adoptó la metodología ágil SCRUM, organizada en sprints de 3 semanas, permitiendo mostrar avances continuos y construir el sistema de forma modular. La planificación se realizó con una tabla de sprints por módulo (login, dashboard, reportes, etc.) y tareas definidas por historia de usuario.

---

## Avances realizados hasta el momento

Hasta esta etapa del proyecto se han cumplido los siguientes hitos:

1. Planteamiento del problema y justificación de la solución.
2. Selección y documentación de la metodología ágil (SCRUM).
3. Elaboración del Product Backlog y planificación de sprints.
4. Diseño de prototipos visuales (UI) para todos los módulos:
   - Login
   - Dashboard
   - Gestión de Actividades
   - Reportes
   - Línea de Tiempo
   - Gestión de Tutores/Proyectos
   - Panel administrativo
5. Estructura inicial del proyecto separada en:
   - frontend/ → aplicación cliente (React + Tailwind)
   - backend/ → servidor (Express + Prisma)
6. Generación del código base con carpetas vacías y archivos iniciales:
   - frontend/src/pages (Login.tsx, Dashboard.tsx…)
   - backend/src/controllers, routes, prisma/schema.prisma
7. Organización del repositorio en GitHub para control de versiones y revisión externa.

---

## Estructura del Repositorio

El proyecto se divide en dos carpetas principales:

/
├── frontend/  
│   ├── src/  
│   │   ├── pages/ → Login, Dashboard, Reportes, etc.  
│   │   ├── components/ → Navbar, Sidebar, etc.  
│   ├── vite.config.ts  
│   ├── tailwind.config.js  
│   └── index.html  
├── backend/  
│   ├── src/  
│   │   ├── controllers/  
│   │   ├── routes/  
│   ├── prisma/schema.prisma  
│   ├── .env  
│   └── package.json  
└── README.md

---

## Próximos pasos

- Implementación funcional del login con autenticación JWT.
- Desarrollo de dashboard dinámico por tipo de usuario.
- Conexión base de datos con Prisma + PostgreSQL.
- Subida de datos institucionales extraídos manualmente del sistema “Zona Reportes”.
- Despliegue progresivo en Vercel y Railway.

---

## Arquitectura General

VincuSalud se basa en una arquitectura por capas que separa responsabilidades para un mantenimiento eficiente:
- <strong>Presentación (Frontend):</strong> Interfaz de usuario con React y Tailwind CSS
- <strong>Lógica de negocio (Backend):</strong> API REST con Express y TypeScript
- <strong>Acceso a datos (ORM):</strong> Prisma para comunicarse con la base de datos PostgreSQL
- <strong>Persistencia:</strong> Base de datos PostgreSQL

---

## Configuración del Frontend (React + Tailwind + Vite)

<pre><code># Desde la carpeta raíz
cd frontend
npm create vite@latest
# Selecciona React + TypeScript
cd vincusalud-frontend
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p</code></pre>

<p>Configura <code>tailwind.config.js</code>:</p>
  <pre><code>content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"]</code></pre>

  <p>Agrega Tailwind en <code>src/index.css</code>:</p>
  <pre><code>@tailwind base;
@tailwind components;
@tailwind utilities;</code></pre>

---

## Configuración del Backend (Express + TypeScript + Prisma)

<pre><code>cd backend
npm init -y
npm install express cors dotenv jsonwebtoken bcryptjs prisma
npm install -D typescript ts-node nodemon @types/node @types/express
npx tsc --init
npx prisma init</code></pre>

<p>Archivo <code>src/index.ts</code>:</p>
  <pre><code>import express from "express";
import cors from "cors";
const app = express();
app.use(cors());
app.use(express.json());
app.listen(3000, () => console.log("API corriendo en puerto 3000"));</code></pre>

  <p>Archivo <code>prisma/schema.prisma</code>:</p>
  <pre><code>model Usuario {
  id        Int      @id @default(autoincrement())
  nombre    String
  correo    String   @unique
  password  String
}</code></pre>

  <p>Compila la base de datos:</p>
  <pre><code>npx prisma migrate dev --name init</code></pre>

---

## Conexión Frontend/Backend

Desde el Frontend puedes hacer peticiones usando fetch o Axios:
<pre><code>fetch("http://localhost:3000/api/login", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ email, password })
});</code></pre>

---

## Variables de Entorno

<pre><code>// backend/.env
DATABASE_URL="postgresql://user:password@localhost:5432/vincusalud"
JWT_SECRET="supersecreto"</code></pre>

---

## Scripts Útiles

<pre><code>// backend/package.json
"scripts": {
  "dev": "nodemon src/index.ts",
  "build": "tsc"
}</code></pre>
  <pre><code>// frontend/package.json
"scripts": {
  "dev": "vite",
  "build": "vite build"
}</code></pre>

---

## Autor

Nombre: Christian Mora  
Proyecto: Tesis para la carrera de Ingeniería de Software  
Facultad: Digital School
Materia: Interacción Persona Computador IPC
