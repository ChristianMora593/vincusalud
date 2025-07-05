# VincuSalud – Sistema de Gestión de Vinculación con la Sociedad

Aplicación web para la Facultad de Ciencias de la Salud orientada al control, seguimiento y reporte de las actividades de vinculación de estudiantes con la comunidad.

---

# Prototipado en Figma

Se ha iniciado el proceso de prototipado de la aplicación web para la Facultad de Ciencias de la Salud, y se continúa manteniendo reuniones con la Dra. Gabriela Castillo, coordinadora de proyectos de Vinculación. Durante estas sesiones, se están realizando las modificaciones necesarias para asegurar que el sistema cumpla con todos los requerimientos por los cuales fue solicitado. Una vez definidos con claridad los lineamientos y funcionalidades, se procederá con el desarrollo del software como tal.

<a href="[https://www.ejemplo.com"](https://www.figma.com/design/hbW2E7wOiCPJzaqRGRTWWi/Prototipado-Proyecto-de-Titulaci%C3%B3n-VincuSalud?node-id=0-1&t=jgqx8KYt8xwNHXAs-1) target="_blank">Enlace a Figma</a>

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

Se adoptó la metodología ágil SCRUM, organizada en sprints de 2 semanas, permitiendo mostrar avances continuos y construir el sistema de forma modular. La planificación se realizó con una tabla de sprints por módulo (login, dashboard, reportes, etc.) y tareas definidas por historia de usuario.

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

## Autor

Nombre: Christian Mora  
Proyecto: Tesis para la carrera de Ingeniería de Software  
Facultad: Digital School
Materia: Interacción Persona Computador IPC
