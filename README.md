# Argentina Programa 4.0

## Servidor Express

![Express Nodejs](https://miro.medium.com/v2/resize:fit:1400/1*f7ztMaMM0etsFHpEfkdiwA.png)
Proyecto Final Lenguajes de programación 1 - EPICA SAPEM - Full Stack Tramo 2

Este es el proyecto final del curso "Tramo 2 - Lenguajes de programación 1 - EPICA SAPEM" como "Full Stack Developer", donde se utiliza Node.js con Express y Sequelize para interactuar con una base de datos MySQL y EJS con HTML, CSS y Boostrap para el consumo de la API creada. A continuación, se detallan las dependencias necesarias y las instrucciones para configurar y probar el proyecto.

![Logo](https://qualitapps.com/wp-content/uploads/2023/02/102.png)


## ⚙ Configuración ⚙

1. Crea un archivo `.env` en la raíz del proyecto y configura las variables de entorno necesarias, como la conexión a la base de datos.

```bash
DB_HOST=localhost
DB_USER=root
DB_PASS=contraseña
DB_NAME=nombre_de_la_base_de_datos
```

2. Ejecuta las migraciones de la base de datos (si estás utilizando `sequelize-cli`):

```bash
  npx sequelize-cli db:migrate
```

3. En su defecto, si no deseas usar migraciones, crea una base de datos ejecutando los siguientes scripts en tu gestor SQL:

```bash
CREATE DATABASE epica;

CREATE TABLE publicaciones (
  id INT AUTO_INCREMENT PRIMARY KEY,
  titulo VARCHAR(255) NOT NULL,
  descripcion TEXT NOT NULL,
  fecha DATE NOT NULL,
  url_imagen VARCHAR(255)
);
```

## 💻 Ejecución 💻

Para ejecutar el proyecto en modo de desarrollo con nodemon, utiliza el siguiente comando:

```bash
  npm run dev
```

O en su defecto:

```bash
  node app.js
```

El servidor estará disponible en `http://localhost:5000`.

## 📱 Uso 📲

Este proyecto proporciona una interfaz de usuario basada en EJS para interactuar con las publicaciones. A continuación, se describen las funcionalidades proporcionadas por cada interfaz:

### Lista de Publicaciones 📘 (home.ejs)

- Muestra una lista de todas las publicaciones existentes.
- Permite ver los detalles de cada publicación.
- Enlace para editar cada publicación.

### Editar Publicación 📗 (editar.ejs)

- Permite editar una publicación existente.
- Se pueden modificar el título, la descripción, la fecha y la URL de la imagen de la publicación.
- Al guardar los cambios, se actualiza la publicación en la base de datos.

### Administración de Publicaciones 📖 (admin.ejs)

- Permite crear una nueva publicación.
- Se pueden ingresar el título, la descripción, la fecha y la URL de la imagen de la nueva publicación.
- Al guardar la nueva publicación, se crea en la base de datos.
