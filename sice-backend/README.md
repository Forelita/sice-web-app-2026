# SICE Backend

Backend del sistema SICE desarrollado con Node.js y Express, pensado para servir la lógica de negocio y la integración con una base de datos MySQL.

## Descripción general

Este proyecto proporciona la API REST principal del sistema SICE. Actualmente se encuentra en una base inicial con configuración de Express, conexión a MySQL, manejo de variables de entorno y un endpoint de salud para verificar que la API está disponible.

## Tecnologías utilizadas

- Node.js
- Express.js
- MySQL2
- dotenv
- Nodemon

## Estructura del proyecto

```text
sice-backend/
├── src/
│   ├── config/
│   │   └── database.js
│   ├── modules/
│   │   ├── applications/
│   │   ├── auth/
│   │   ├── users/
│   │   └── vacancies/
│   ├── middlewares/
│   ├── utils/
│   ├── app.js
│   └── server.js
├── .env
├── .env.example
├── .gitignore
├── package.json
├── package-lock.json
└── README.md
```

## Requisitos previos

- Node.js 18 o superior
- MySQL Server en ejecución
- npm o yarn

## Instalación

1. Clona el repositorio y entra a la carpeta del backend:

```bash
cd sice-backend
```

2. Instala las dependencias:

```bash
npm install
```

3. Crea un archivo `.env` a partir del ejemplo:

```bash
cp .env.example .env
```

4. Configura las variables de entorno. Un ejemplo de configuración es:

```env
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=tu_contraseña
DB_NAME=sice
DB_PORT=3306
```

> Importante: la aplicación utiliza `DB_PASSWORD` para la conexión a MySQL, así que debe definirse en el archivo `.env`.

## Ejecución

### Modo de desarrollo

```bash
npm run dev
```

### Modo de producción

```bash
npm start
```

La aplicación queda disponible por defecto en:

```text
http://localhost:3000
```

## Endpoints

### Health check

```http
GET /api/health
```

Respuesta esperada:

```json
{
  "status": "ok",
  "message": "SICE API is running successfully"
}
```

## Scripts disponibles

En el archivo `package.json` se incluyen los siguientes scripts:

```json
"scripts": {
  "start": "node src/server.js",
  "dev": "nodemon src/server.js"
}
```

## Estado del proyecto

El proyecto se encuentra en una etapa inicial de desarrollo. La estructura base ya está preparada para crecer con módulos de autenticación, usuarios, vacantes y solicitudes, además de una conexión a base de datos lista para ser utilizada por los servicios REST.

## Contribución

Si deseas colaborar en el proyecto, puedes seguir estos pasos:

1. Crear una rama nueva
2. Implementar la funcionalidad o corrección
3. Validar la ejecución local
4. Abrir un pull request con una descripción clara

## Licencia

Este proyecto se distribuye bajo la licencia ISC.
