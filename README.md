# TuPeli - Plataforma de Peliculas

Proyecto desarrollado para la materia **Plataformas Empresariales**. TuPeli es una aplicacion web que permite explorar, buscar, calificar y gestionar un catalogo de peliculas. La interfaz esta completamente en espanol y orientada a una experiencia moderna y atractiva.

---

## Descripcion General

TuPeli ofrece dos vistas principales:

- **Landing page (usuario no autenticado):** Presenta la plataforma con una seccion hero, caracteristicas destacadas, un flujo de "como funciona" y un formulario de suscripcion por correo.
- **Dashboard (usuario autenticado):** Permite buscar peliculas por titulo o genero, ver detalles de cada pelicula, y realizar operaciones CRUD (crear, editar y eliminar peliculas).

---

## Tecnologias Utilizadas

| Tecnologia | Uso |
|---|---|
| [React 19](https://react.dev/) | Biblioteca principal para la construccion de la interfaz de usuario |
| [Vite](https://vite.dev/) | Herramienta de desarrollo y empaquetado rapido |
| [Supabase](https://supabase.com/) | Backend como servicio: autenticacion de usuarios y base de datos PostgreSQL |
| [Lucide React](https://lucide.dev/) | Iconos SVG utilizados en toda la interfaz |
| [ESLint](https://eslint.org/) | Herramienta de analisis estatico para mantener la calidad del codigo |

---

## Estructura del Proyecto

```
tupeli_plataformas_empresariales/
├── public/
│   ├── hero_bg.png          # Imagen de fondo del hero
│   └── vite.svg             # Icono de Vite
├── src/
│   ├── assets/
│   │   └── react.svg        # Icono de React
│   ├── App.jsx              # Componente principal con toda la logica de la aplicacion
│   ├── App.css              # (Estilos redirigidos a index.css)
│   ├── auth.css             # Estilos del modal de autenticacion y formularios
│   ├── index.css            # Estilos globales de la aplicacion
│   ├── main.jsx             # Punto de entrada de React
│   └── supabaseClient.js    # Configuracion del cliente de Supabase
├── index.html               # HTML principal
├── package.json             # Dependencias y scripts del proyecto
├── vite.config.js           # Configuracion de Vite
└── eslint.config.js         # Configuracion de ESLint
```

---

## Funcionalidades

### Autenticacion
- Registro e inicio de sesion mediante correo electronico y contrasena.
- Gestion de sesiones con Supabase Auth.
- Modal de autenticacion con pestanas para alternar entre registro e inicio de sesion.

### Catalogo de Peliculas
- Busqueda de peliculas por titulo con debounce (retraso inteligente para evitar peticiones excesivas).
- Filtrado por genero mediante botones de seleccion rapida.
- Visualizacion en tarjetas con poster, genero, calificacion y descripcion.

### Operaciones CRUD (usuarios autenticados)
- **Crear:** Anadir nuevas peliculas con titulo, genero, calificacion, imagen y descripcion.
- **Leer:** Consultar el catalogo completo o filtrado.
- **Actualizar:** Editar los datos de una pelicula existente.
- **Eliminar:** Borrar peliculas del catalogo.

### Interfaz
- Diseno oscuro moderno con efectos glassmorphism.
- Totalmente responsive.
- Animaciones sutiles (orbs flotantes, transiciones suaves).
- Barra de navegacion fija con cambio de estilo al hacer scroll.

---

## Requisitos Previos

- [Node.js](https://nodejs.org/) (version 18 o superior recomendada)
- [npm](https://www.npmjs.com/) (incluido con Node.js)

---

## Instalacion y Ejecucion

1. Clonar el repositorio:

```bash
git clone https://github.com/JuanesVasco19/tupeli_plataformas_empresariales.git
cd tupeli_plataformas_empresariales
```

2. Instalar las dependencias:

```bash
npm install
```

3. Iniciar el servidor de desarrollo:

```bash
npm run dev
```

4. Abrir en el navegador la URL que aparece en la terminal (por defecto `http://localhost:5173`).

---

## Scripts Disponibles

| Comando | Descripcion |
|---|---|
| `npm run dev` | Inicia el servidor de desarrollo con recarga en caliente |
| `npm run build` | Genera la version de produccion en la carpeta `dist/` |
| `npm run preview` | Sirve la version de produccion localmente para previsualizacion |
| `npm run lint` | Ejecuta ESLint para verificar la calidad del codigo |

---

## Base de Datos

La aplicacion utiliza **Supabase** como backend. La tabla principal es `movies`, que contiene los siguientes campos:

| Campo | Tipo | Descripcion |
|---|---|---|
| `id` | UUID | Identificador unico de la pelicula |
| `title` | texto | Titulo de la pelicula |
| `description` | texto | Descripcion o sinopsis |
| `genre` | texto | Genero (Accion, Drama, Comedia, etc.) |
| `rating` | numerico | Calificacion de 1 a 10 |
| `image_url` | texto | URL del poster de la pelicula (opcional) |

---

## Generos Disponibles

Accion, Drama, Ciencia Ficcion, Crimen, Comedia, Fantasia, Suspense, Terror, Animacion, Romance, Guerra, Misterio, Aventura, Historia, Western, Biografia.

---

## Componentes Principales

| Componente | Descripcion |
|---|---|
| `App` | Componente raiz que gestiona el estado de autenticacion y decide que vista mostrar |
| `AuthModal` | Modal con formulario de inicio de sesion y registro |
| `MovieFormModal` | Modal para crear o editar peliculas |
| `Navbar` | Barra de navegacion superior fija |
| `Hero` | Seccion principal de la landing page |
| `Features` | Tarjetas con las caracteristicas de la plataforma |
| `HowItWorks` | Seccion de pasos que explica el flujo de uso |
| `MovieSearch` | Buscador y listado de peliculas con modal de detalle |
| `CTA` | Seccion de llamada a la accion con formulario de correo |
| `Footer` | Pie de pagina |

---

## Autor

Proyecto desarrollado por **Juan Esteban Vasco** para la materia de Plataformas Empresariales.
