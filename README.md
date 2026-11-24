# Backend Express + MongoDB (Mongoose)
SENA · ADSO · Guía 7 · Clase 9 — Conexión a Base de Datos

API REST con **10 endpoints** persistidos en MongoDB.

## Estructura (arquitectura en capas)
```
config/db.js          Conexión a MongoDB
models/               Esquemas Mongoose (Producto, Usuario)
controllers/          Lógica de cada endpoint
routes/               Definición de rutas
middlewares/          Manejo de errores y 404
app.js / server.js    Configuración de Express / arranque
postman/              Colección de pruebas exportada
```

## Puesta en marcha
```bash
npm install
cp .env.example .env     # ajusta MONGO_URI y JWT_SECRET
npm start                # o: npm run dev
```
Necesitas MongoDB local (`mongodb://localhost:27017`) o un clúster de MongoDB Atlas (pega su URI en `.env`).

## Endpoints
| # | Método | Ruta | Descripción |
|---|--------|------|-------------|
| 1 | POST | /api/productos | Crear producto |
| 2 | GET | /api/productos | Listar productos |
| 3 | GET | /api/productos/:id | Producto por ID |
| 4 | PUT | /api/productos/:id | Actualización total |
| 5 | DELETE | /api/productos/:id | Eliminar producto |
| 6 | GET | /api/productos/categoria/:cat | Filtrar por categoría |
| 7 | POST | /api/usuarios/registro | Registrar usuario (contraseña con bcrypt) |
| 8 | POST | /api/usuarios/login | Login, devuelve JWT |
| 9 | GET | /api/usuarios | Listar usuarios (sin contraseñas) |
| 10 | GET | /api/reportes/estadisticas | Agregaciones: totales, por categoría, valor de inventario |

## Pruebas
Importa `postman/coleccion-guia7.postman_collection.json` en Postman o Thunder Client y ejecútala en orden (guarda `productoId` y `token` automáticamente).

## Notas técnicas
- `/categoria/:cat` se declara antes de `/:id` para evitar conflicto de rutas.
- Validación de `ObjectId`, errores 400/404/409/500 centralizados.
- `.env` está en `.gitignore`; no subas credenciales al repositorio.
"# clase9-express-mongodb-sena" 
"# Mongo" 
"# Mongo" 
"# Mongo" 
"# Mongo" 
"# Mongo" 
"# Mongo" 
