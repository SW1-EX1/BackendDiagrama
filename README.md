# 📊 Diagrama Backend

Backend API REST para una aplicación de gestión de diagramas colaborativa desarrollada con Node.js, Express y MongoDB.

## 🚀 Características

- **API REST** completa para gestión de proyectos
- **Base de datos MongoDB** con Mongoose ODM
- **Comunicación en tiempo real** con Socket.io
- **Autenticación y seguridad** con bcrypt
- **Subida de archivos** y manejo de ZIP
- **Validación de datos** con express-validator
- **CORS** habilitado para aplicaciones frontend

## 📁 Estructura del Proyecto

```
diagrama-backend/
├── controllers/           # Lógica de negocio
│   └── proyectos.js      # Controladores de proyectos
├── models/               # Esquemas de Mongoose
│   └── proyecto.js       # Modelo de proyecto
├── routes/               # Definición de rutas API
├── app.js               # Archivo principal de la aplicación
├── package.json         # Configuración y dependencias
└── README.md           # Documentación del proyecto
```

## 🛠️ Tecnologías Utilizadas

### Dependencias Principales
- **Express** `^4.18.2` - Framework web para Node.js
- **Mongoose** `^7.8.2` - ODM para MongoDB
- **Socket.io** `^3.0.0` - Comunicación en tiempo real
- **bcryptjs** `^2.4.3` - Encriptación de contraseñas
- **CORS** `^2.8.5` - Manejo de peticiones cross-origin
- **express-validator** `^7.0.1` - Validación de datos
- **express-fileupload** `^1.5.1` - Subida de archivos
- **multer** `^1.4.5-lts.1` - Middleware para archivos
- **jszip** `^3.10.1` - Manejo de archivos ZIP
- **file-saver** `^2.0.5` - Descarga de archivos
- **dotenv** `^16.0.3` - Variables de entorno

### Dependencias de Desarrollo
- **Nodemon** `^3.1.10` - Reinicio automático en desarrollo

## 📋 Prerrequisitos

- Node.js (versión 14 o superior)
- MongoDB (local o Atlas)
- npm o yarn

## ⚙️ Instalación

1. **Clonar el repositorio**
```bash
git clone <url-del-repositorio>
cd diagrama-backend-master
```

2. **Instalar dependencias**
```bash
npm install
```

3. **Configurar variables de entorno**
Crear un archivo `.env` en la raíz del proyecto:
```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/diagrama_db
# Agregar otras variables según sea necesario
```

4. **Iniciar MongoDB**
Asegúrate de que MongoDB esté ejecutándose en tu sistema.

## 🚀 Ejecución

### Modo Desarrollo
```bash
npm run start:dev
```
Utiliza nodemon para reinicio automático al detectar cambios.

### Modo Producción
```bash
npm start
```

El servidor se iniciará en `http://localhost:3000` (o el puerto configurado).

## 📚 API Endpoints

### Proyectos

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/proyectos/:idUser` | Obtener todos los proyectos de un usuario |
| `GET` | `/proyecto/:id` | Obtener un proyecto específico |
| `POST` | `/proyectos` | Crear un nuevo proyecto |
| `PUT` | `/proyectos/:id` | Actualizar un proyecto existente |
| `DELETE` | `/proyectos/:id` | Eliminar un proyecto |

### Estructura de Datos

#### Proyecto
```json
{
  "nombre": "string",
  "diagramObject": "object",
  "idUser": "string"
}
```

## 🔧 Funcionalidades

### Controladores Implementados

#### `proyectos.js`
- **`getProyecto()`** - Obtiene un proyecto por ID
- **`getProyectos()`** - Lista proyectos por usuario
- **`createProyecto()`** - Crea nuevo proyecto
- **`updateProyecto()`** - Actualiza proyecto existente
- **`deleteProyecto()`** - Elimina proyecto físicamente

### Características Especiales
- ✅ Manejo de errores con try-catch
- ✅ Validación de datos de entrada
- ✅ Comunicación en tiempo real
- ✅ Subida y descarga de archivos
- ✅ Compresión de archivos ZIP

## 🤝 Contribución

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📝 Scripts Disponibles

```json
{
  "start": "node app",
  "start:dev": "nodemon app.js",
  "test": "echo \"Error: no test specified\" && exit 1"
}
```

## 🐛 Solución de Problemas

### Error: Missing script "start:dev"
```bash
npm install nodemon --save-dev
```

### Error de conexión a MongoDB
Verificar que MongoDB esté ejecutándose y que la URI de conexión sea correcta.

