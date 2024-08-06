# Proyecto de Docker con Usuario No Root

Este proyecto tiene como objetivo crear contenedores Docker para una aplicación llamada "todo-app" que se ejecuta con un usuario no root. Ejecutar aplicaciones dentro de contenedores Docker con un usuario no root es una práctica importante para mejorar la seguridad, evitando que el contenedor tenga permisos excesivos que podrían ser explotados por atacantes en caso de vulnerabilidades.

## Configuración

1. **Modificar el archivo `.env`:**
   - Cambia la variable `MY_user` por el nombre de usuario que deseas utilizar en el contenedor, por ejemplo, `myuser`.

2. **Ajustar la configuración en `src/persistence/sqlite.js`:**
   - Asegúrate de que la configuración refleje el nombre del usuario definido en el archivo `.env`.
   - Esta en la linea 3 del archivo, el apartado de /home/myuser/app/todos/todo.db
   - Verifica que la ruta del archivo SQLite incluya el nombre de usuario correcto.
   - Ejemplo: /home/newuser/app/todos/todo.db

   
3. **Construir y levantar los contenedores:**
   - Ejecuta el siguiente comando para construir la imagen Docker y levantar los contenedores:
     ```sh
     docker-compose up --build
     ```

4. **Acceder a la aplicación:**
   - Una vez que los contenedores estén en funcionamiento, abre tu navegador y visita la URL:
     ```
     http://localhost:3000
     ```

