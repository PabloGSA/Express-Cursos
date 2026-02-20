# API REST de Cursos

API REST desarrollada con Node.js y Express.js para gestionar cursos de programación y matemáticas. Este proyecto implementa operaciones CRUD (Create, Read, Update, Delete) y demuestra el uso de routers en Express.

## 📋 Descripción

Este servidor proporciona endpoints para consultar, crear, actualizar y eliminar cursos de programación y matemáticas. Los datos se almacenan en memoria (archivo `datos/cursos.js`).

## 🚀 Características

- **Routers modulares**: Separación de rutas por categoría (programación y matemáticas)
- **Operaciones CRUD completas** para cursos de programación:
  - GET: Obtener todos los cursos o filtrar por lenguaje/nivel
  - POST: Crear nuevos cursos
  - PUT: Actualizar cursos completos
  - PATCH: Actualizar cursos parcialmente
  - DELETE: Eliminar cursos
- **Filtros y ordenamiento**: Búsqueda por lenguaje, nivel y ordenamiento por vistas
- **Middleware JSON**: Procesamiento automático de datos JSON

## 📁 Estructura del Proyecto

```
CRUD/
├── app.js                    # Archivo principal del servidor
├── package.json              # Dependencias y configuración
├── datos/
│   └── cursos.js            # Base de datos en memoria
└── routers/
    ├── programacion.js      # Rutas para cursos de programación
    └── matematicas.js       # Rutas para cursos de matemáticas
```

## 🛠️ Tecnologías Utilizadas

- **Node.js**: Entorno de ejecución
- **Express.js**: Framework web para Node.js
- **Nodemon**: Herramienta para desarrollo con recarga automática

## 📦 Instalación

1. Clona o descarga este repositorio
2. Instala las dependencias:
```bash
npm install
```

## ▶️ Uso

### Iniciar el servidor

```bash
node app.js
```

O con nodemon para desarrollo (recarga automática):

```bash
npx nodemon app.js
```

El servidor estará disponible en: `http://localhost:3000`

## 📡 Endpoints Disponibles

### Cursos Generales

- **GET** `/api/cursos` - Obtiene todos los cursos (programación y matemáticas)

### Cursos de Programación

- **GET** `/api/cursos/programacion` - Obtiene todos los cursos de programación
- **GET** `/api/cursos/programacion/:lenguaje` - Filtra cursos por lenguaje (ej: `python`, `javascript`)
  - Query param `?ordenar=vistas` - Ordena por número de vistas descendente
- **GET** `/api/cursos/programacion/:lenguaje/:nivel` - Filtra por lenguaje y nivel (ej: `basico`, `intermedio`)
- **POST** `/api/cursos/programacion` - Crea un nuevo curso
- **PUT** `/api/cursos/programacion/:id` - Actualiza un curso completo por ID
- **PATCH** `/api/cursos/programacion/:id` - Actualiza parcialmente un curso por ID
- **DELETE** `/api/cursos/programacion/:id` - Elimina un curso por ID

### Cursos de Matemáticas

- **GET** `/api/cursos/matematicas` - Obtiene todos los cursos de matemáticas
- **GET** `/api/cursos/matematicas/:tema` - Filtra cursos por tema (ej: `calculo`, `algebra`)
- **POST** `/api/cursos/matematicas` - Crea un nuevo curso de matemáticas

## 📝 Ejemplos de Uso

### Obtener todos los cursos de programación
```bash
GET http://localhost:3000/api/cursos/programacion
```

### Filtrar cursos de Python
```bash
GET http://localhost:3000/api/cursos/programacion/python
```

### Ordenar por vistas
```bash
GET http://localhost:3000/api/cursos/programacion/javascript?ordenar=vistas
```

### Crear un nuevo curso
```bash
POST http://localhost:3000/api/cursos/programacion
Content-Type: application/json

{
  "id": 4,
  "titulo": "Aprende Node.js",
  "lenguaje": "javascript",
  "vistas": 5000,
  "nivel": "intermedio"
}
```

### Actualizar un curso (PUT)
```bash
PUT http://localhost:3000/api/cursos/programacion/1
Content-Type: application/json

{
  "id": 1,
  "titulo": "Python Avanzado",
  "lenguaje": "python",
  "vistas": 20000,
  "nivel": "avanzado"
}
```

### Actualizar parcialmente un curso (PATCH)
```bash
PATCH http://localhost:3000/api/cursos/programacion/1
Content-Type: application/json

{
  "vistas": 25000
}
```

### Eliminar un curso
```bash
DELETE http://localhost:3000/api/cursos/programacion/1
```

## 🔧 Configuración

El puerto del servidor está configurado en `app.js` (línea 22). Por defecto es el puerto **3000**. Puedes modificarlo cambiando la constante `PUERTO`.

## 📚 Notas

- Los datos se almacenan en memoria, por lo que se perderán al reiniciar el servidor
- Este proyecto es educativo y demuestra conceptos básicos de APIs REST con Express.js
- Para producción, considera usar una base de datos real (MongoDB, PostgreSQL, etc.)

## 👤 Autor

pabloSanchez

## 📄 Licencia

ISC
