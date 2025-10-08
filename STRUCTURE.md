# Estructura del Repositorio Biblioteca

Este documento describe todos los archivos presentes en el repositorio y su propósito.

## Archivos Raíz

- **Biblioteca.sql** - Script SQL con la estructura de la base de datos y datos iniciales para la aplicación de biblioteca

## Directorio `biblioteca/`

### Archivos de Configuración

- **.eslintrc.js** - Configuración de ESLint para análisis estático de código y reglas de estilo
- **.prettierrc** - Configuración de Prettier para formateo automático de código
- **.gitignore** - Lista de archivos y directorios que Git debe ignorar
- **nest-cli.json** - Configuración del CLI de NestJS
- **tsconfig.json** - Configuración principal de TypeScript para el proyecto
- **tsconfig.build.json** - Configuración de TypeScript específica para compilación de producción
- **package.json** - Dependencias del proyecto, scripts de npm y metadatos
- **package-lock.json** - Versiones exactas de todas las dependencias instaladas

### Documentación

- **README.md** - Documentación principal del proyecto con instrucciones de instalación y uso

### Directorio `src/` - Código Fuente

#### Archivos Principales de la Aplicación

- **main.ts** - Punto de entrada de la aplicación NestJS, configura Swagger y arranca el servidor
- **app.module.ts** - Módulo raíz de la aplicación, configura TypeORM y módulos
- **app.controller.ts** - Controlador principal de la aplicación
- **app.controller.spec.ts** - Pruebas unitarias para el controlador principal
- **app.service.ts** - Servicio principal de la aplicación

#### Módulo de Autores (`src/autores/`)

- **autor.entity.ts** - Entidad de TypeORM que define la estructura de la tabla de autores
- **autores.controller.ts** - Controlador REST API para gestión de autores
- **autores.service.ts** - Lógica de negocio para operaciones de autores
- **autores.module.ts** - Módulo NestJS que encapsula la funcionalidad de autores
- **dto/crear-autor.dto.ts** - Data Transfer Object para validación de datos al crear autores

#### Módulo de Editoriales (`src/editoriales/`)

- **editorial.entity.ts** - Entidad de TypeORM para la tabla de editoriales
- **editoriales.controller.ts** - Controlador REST API para gestión de editoriales
- **editoriales.service.ts** - Lógica de negocio para operaciones de editoriales
- **editoriales.module.ts** - Módulo NestJS para la funcionalidad de editoriales
- **dto/crear-editorial.dto.ts** - DTO para validación de datos al crear editoriales

#### Módulo de Libros (`src/libros/`)

- **libro.entity.ts** - Entidad de TypeORM para la tabla de libros con relaciones
- **libros.controller.ts** - Controlador REST API para gestión de libros
- **libros.service.ts** - Lógica de negocio para operaciones de libros, incluyendo relaciones con autores y editoriales
- **libros.module.ts** - Módulo NestJS para la funcionalidad de libros
- **dto/crear-libro.dto.ts** - DTO para validación de datos al crear libros

### Directorio `test/` - Pruebas

- **app.e2e-spec.ts** - Pruebas end-to-end (e2e) para la aplicación
- **jest-e2e.json** - Configuración de Jest para pruebas e2e

## Resumen de la Arquitectura

El proyecto utiliza:
- **Framework**: NestJS (Node.js framework)
- **Lenguaje**: TypeScript
- **Base de Datos**: MySQL con TypeORM
- **Documentación API**: Swagger
- **Testing**: Jest
- **Linting**: ESLint + Prettier

### Estructura de Módulos

```
App Module (raíz)
├── Libros Module
│   ├── Controller (REST endpoints)
│   ├── Service (lógica de negocio)
│   └── Entity (modelo de datos)
├── Autores Module
│   ├── Controller
│   ├── Service
│   └── Entity
└── Editoriales Module
    ├── Controller
    ├── Service
    └── Entity
```

### Total de Archivos

- **Archivos TypeScript (.ts)**: 24
- **Archivos JavaScript (.js)**: 1 (.eslintrc.js)
- **Archivos de configuración JSON**: 6
- **Archivos SQL**: 1
- **Archivos de documentación**: 1 (README.md)
- **Total**: 32 archivos (excluyendo node_modules, dist, .git)
