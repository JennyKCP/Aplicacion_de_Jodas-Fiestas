# OH! Cañamos

**Una aplicación web moderna para crear, descubrir y gestionar eventos de forma visual e interactiva.**

OH! Cañamos combina la experiencia visual de Instagram y Pinterest con la funcionalidad social de X (Twitter), creando una plataforma única donde organizadores e invitados pueden conectar a través de eventos memorables.

---

## Tabla de Contenidos

- [Características Principales](#características-principales)
- [Tecnologías](#tecnologías)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Instalación](#instalación)
- [Configuración](#configuración)
- [Uso](#uso)
- [Roles de Usuario](#roles-de-usuario)
- [Roadmap](#roadmap)
- [Diseño y Paleta de Colores](#diseño-y-paleta-de-colores)
- [Contribución](#contribución)
- [Licencia](#licencia)

---

## Características Principales

### Para Organizadores (Anfitriones)
- Crear y publicar eventos con imágenes atractivas
- Editar y eliminar eventos propios
- Gestionar lista de asistentes
- Moderar comentarios en sus eventos
- Panel de administración personalizado

### Para Invitados (Usuarios)
- Explorar eventos en un feed visual tipo Instagram/Pinterest
- Buscar eventos por nombre, categoría, fecha o ubicación
- Guardar eventos favoritos
- Confirmar asistencia a eventos
- Comentar y reaccionar a eventos
- Recibir notificaciones personalizadas

### Funcionalidades Generales
- Sistema de autenticación (login/registro)
- Perfiles de usuario personalizables
- Sistema de notificaciones en tiempo real
- Diseño responsive y moderno
- Interfaz minimalista y fácil de usar

---

## Tecnologías

### Frontend
- **React** - Framework principal para la interfaz de usuario
- **TailwindCSS** - Framework CSS para estilos y diseño responsive
- **React Router DOM** - Sistema de navegación y rutas
- **Vite** - Herramienta de desarrollo rápida (recomendado)

### Herramientas de Desarrollo
- **Visual Studio Code** - IDE recomendado
- **Node.js** - Entorno de ejecución
- **npm/yarn** - Gestores de paquetes

### Próximas Integraciones (Backend)
- **Firebase/Supabase** - Base de datos y autenticación
- **Cloudinary/AWS S3** - Almacenamiento de imágenes
- **Socket.io** - Notificaciones en tiempo real

---

## Estructura del Proyecto

```
oh-canamos/
├── public/
│   ├── favicon.ico
│   └── logo.png
├── src/
│   ├── assets/
│   │   ├── images/
│   │   └── icons/
│   ├── components/
│   │   ├── common/
│   │   │   ├── Navbar.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── Button.jsx
│   │   │   └── Modal.jsx
│   │   ├── auth/
│   │   │   ├── LoginForm.jsx
│   │   │   ├── RegisterForm.jsx
│   │   │   └── RecoverPassword.jsx
│   │   ├── events/
│   │   │   ├── EventCard.jsx
│   │   │   ├── EventDetail.jsx
│   │   │   ├── EventForm.jsx
│   │   │   └── EventList.jsx
│   │   ├── profile/
│   │   │   ├── ProfileHeader.jsx
│   │   │   ├── ProfileTabs.jsx
│   │   │   └── EditProfile.jsx
│   │   ├── notifications/
│   │   │   ├── NotificationPanel.jsx
│   │   │   └── NotificationItem.jsx
│   │   └── search/
│   │       ├── SearchBar.jsx
│   │       └── FilterPanel.jsx
│   ├── pages/
│   │   ├── Login.jsx
│   │   ├── Register.jsx
│   │   ├── Home.jsx
│   │   ├── CreateEvent.jsx
│   │   ├── EventDetail.jsx
│   │   ├── Profile.jsx
│   │   ├── Search.jsx
│   │   └── Dashboard.jsx
│   ├── context/
│   │   ├── AuthContext.jsx
│   │   ├── EventContext.jsx
│   │   └── NotificationContext.jsx
│   ├── hooks/
│   │   ├── useAuth.js
│   │   ├── useEvents.js
│   │   └── useNotifications.js
│   ├── utils/
│   │   ├── constants.js
│   │   ├── helpers.js
│   │   └── validators.js
│   ├── styles/
│   │   └── globals.css
│   ├── App.jsx
│   └── main.jsx
├── .gitignore
├── package.json
├── tailwind.config.js
├── vite.config.js
└── README.md
```

---

## Instalación

### Prerequisitos
- Node.js (versión 16 o superior)
- npm o yarn

### Pasos

1. Clonar el repositorio
```bash
git clone https://github.com/JennyKCP/Aplicacion_de_Jodas-Fiestas.git
cd A
```

2. Instalar dependencias
```bash
npm install
# o
yarn install
```

3. Instalar TailwindCSS
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

4. Instalar React Router DOM
```bash
npm install react-router-dom
```

5. Configurar TailwindCSS (tailwind.config.js)
```javascript
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {
      colors: {
        'primary-orange': '#FFA45B',
        'primary-black': '#000000',
        'primary-white': '#FFFFFF',
        'secondary-gray': '#F5F5F5',
      },
    },
  },
  plugins: [],
}
```

6. Iniciar el servidor de desarrollo
```bash
npm run dev
# o
yarn dev
```

La aplicación estará disponible en `http://localhost:3000`

---

## Configuración

### Variables de Entorno

Crear un archivo `.env` en la raíz del proyecto:

```env
VITE_APP_NAME=OH! Cañamos
VITE_API_URL=http://localhost:3000/api
VITE_FIREBASE_API_KEY=tu_api_key
VITE_FIREBASE_AUTH_DOMAIN=tu_auth_domain
VITE_FIREBASE_PROJECT_ID=tu_project_id
```

### Archivo .gitignore

```
# dependencies
node_modules/
.pnp
.pnp.js

# testing
coverage/

# production
build/
dist/

# environment variables
.env
.env.local
.env.development.local
.env.test.local
.env.production.local

# logs
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# IDE
.vscode/
.idea/

# OS
.DS_Store
Thumbs.db
```

---

## Uso

### Flujo de Usuario

1. **Registro/Login**: Los usuarios crean una cuenta seleccionando su rol (Anfitrión o Invitado)
2. **Exploración**: Acceden al feed principal donde pueden ver eventos publicados
3. **Interacción**: Pueden guardar eventos, confirmar asistencia, comentar y reaccionar
4. **Creación (Anfitriones)**: Los anfitriones pueden crear eventos desde el botón "+" en el navbar
5. **Gestión**: Los anfitriones administran sus eventos desde su panel personal

### Comandos Disponibles

```bash
# Desarrollo
npm run dev          # Inicia servidor de desarrollo

# Producción
npm run build        # Crea versión optimizada para producción
npm run preview      # Previsualiza build de producción

# Linting
npm run lint         # Ejecuta ESLint
```

---

## Roles de Usuario

### Anfitrión (Host)
**Permisos:**
- Crear, editar y eliminar eventos propios
- Ver lista completa de asistentes
- Moderar comentarios
- Acceder al panel de administración
- Todas las funciones de Invitado

### Invitado (Guest)
**Permisos:**
- Explorar y buscar eventos
- Guardar eventos favoritos
- Confirmar/cancelar asistencia
- Comentar en eventos
- Recibir notificaciones
- Editar su propio perfil

---

## Roadmap

### Versión 0.1 (V0) - Actual
- [x] Diseño de interfaz y paleta de colores
- [x] Estructura de componentes React
- [x] Sistema de rutas con React Router
- [ ] Navegación funcional completa
- [ ] Formularios de autenticación (UI)
- [x] Feed de eventos (UI)
- [x] Perfil de usuario (UI)

### Versión 0.5 (MVP)
- [ ] Integración con backend (Firebase/Supabase)
- [ ] Autenticación real de usuarios
- [ ] CRUD completo de eventos
- [ ] Sistema de comentarios funcional
- [ ] Guardado de eventos
- [ ] Confirmación de asistencia

### Versión 1.0 (Lanzamiento)
- [ ] Sistema de notificaciones en tiempo real
- [ ] Búsqueda y filtros avanzados
- [ ] Subida de imágenes
- [ ] Panel de administración completo
- [ ] Responsive design optimizado
- [ ] Pruebas unitarias y de integración

### Versión 1.5 (Futuro)
- [ ] Sistema de invitaciones por email
- [ ] Integración con mapas (Google Maps/Mapbox)
- [ ] Chat entre usuarios
- [ ] Sistema de valoraciones
- [ ] Compartir en redes sociales
- [ ] Modo oscuro
- [ ] Aplicación móvil (React Native)

---

## Diseño y Paleta de Colores

### Colores Principales

| Color | Hex | Uso |
|-------|-----|-----|
| Naranja Pastel | `#FFA45B` | Botones principales, acentos, encabezados |
| Negro | `#000000` | Texto principal, bordes, contraste |
| Blanco | `#FFFFFF` | Fondo principal, tarjetas |
| Gris Suave | `#F5F5F5` | Fondo secundario, áreas neutras |

### Principios de Diseño

- **Minimalista**: Interfaces limpias y sin saturación visual
- **Moderno**: Uso de espacios blancos y tipografía clara
- **Intuitivo**: Navegación simple y coherente
- **Visual**: Énfasis en imágenes de alta calidad
- **Responsive**: Adaptable a todos los dispositivos

### Tipografía
- **Principal**: Inter, system-ui, sans-serif
- **Tamaños**: 14px (body), 16px (subtítulos), 24px-32px (títulos)

---

## Contribución

Las contribuciones son bienvenidas. Para contribuir:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/NuevaCaracteristica`)
3. Commit tus cambios (`git commit -m 'Añade nueva característica'`)
4. Push a la rama (`git push origin feature/NuevaCaracteristica`)
5. Abre un Pull Request

### Guía de Estilo
- Usar nombres descriptivos para variables y funciones
- Comentar código complejo
- Seguir las convenciones de React y TailwindCSS
- Mantener componentes pequeños y reutilizables
- Escribir código limpio y legible

---

## Objetivos de Aprendizaje

Este proyecto permite desarrollar habilidades en:

### Técnicas
- Desarrollo frontend con React
- Diseño con TailwindCSS
- Gestión de estado y Context API
- Routing con React Router DOM
- Componentes reutilizables y modularidad
- Hooks personalizados

### Conceptos
- Arquitectura de aplicaciones web
- UX/UI design
- Autenticación y autorización
- CRUD operations
- Responsive design
- Best practices en React

### Soft Skills
- Planificación de proyectos
- Documentación técnica
- Resolución de problemas
- Trabajo con Git y GitHub

---

## Contacto    

Para preguntas, sugerencias o reportar bugs:

- GitHub Issues: [https://github.com/JennyKCP/Aplicacion_de_Jodas-Fiestas](https://github.com/JennyKCP/Aplicacion_de_Jodas-Fiestas/tree/A)

---

**Dedicado a PaoMensa.**
