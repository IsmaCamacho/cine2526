# 🎬 Aplicación Cine - Despliegue con Nginx y Docker

Este proyecto contiene una práctica de despliegue de una aplicación web llamada **Cine**, utilizando **Nginx** como servidor web dentro de un contenedor **Docker**. El objetivo es que la aplicación sea accesible desde el navegador y que el proceso esté documentado paso a paso.

---

## 📁 Estructura del proyecto

CINE2025CURSO0GIT-main/ 

├── src/ # Archivos de la aplicación (HTML, CSS, JS) 

├── nginx/ # Configuración personalizada de Nginx 

├── Dockerfile # Imagen Docker personalizada 

├── README.md # Documentación del proyecto


---

## ⚙️ Requisitos previos

- Tener instalado [Docker](https://www.docker.com/)
- Tener acceso a una terminal (PowerShell, CMD, Bash, etc.)
- Clonar este repositorio en local

---

## 🚀 Pasos para desplegar la aplicación

### 🧬 1. Clonar el repositorio

```
git clone https://github.com/IsmaCamacho/cine2526
cd cine2526
```

### 📝 2. Preparar la configuración de Nginx
Dentro de la carpeta nginx/, crea el archivo default.conf con el siguiente contenido:

```
server {
    listen 80;
    server_name localhost;
    location / {
        root /usr/share/nginx/html;
        index index.html;
        try_files $uri $uri/ =404;
    }
}
```
Asegúrate de que el archivo principal de tu aplicación se llama index.html y está dentro de la carpeta src/.

### 🐳 3. Crear el Dockerfile
En la raíz del proyecto, crea un archivo llamado Dockerfile con el siguiente contenido:

```
FROM nginx:alpine

COPY src/ /usr/share/nginx/html
COPY nginx/default.conf /etc/nginx/conf.d/default.conf
```

### 🧱 4. Construir la imagen Docker

```
docker build -t cine-nginx .
```

### 🚀 5. Ejecutar el contenedor

```
docker run -d -p 8080:80 cine-nginx (o el puerto libre del que dispongas)
```

### 🌐 6. Acceder a la aplicación
Abre tu navegador y visita:

```
http://localhost:8080
```
Deberías ver la aplicación Cine funcionando correctamente.

### 📌 Notas adicionales
Si el puerto 8080 está ocupado, puedes usar otro como 8081, 8082, etc.

Si ves la página por defecto de Nginx o un error 403, asegúrate de que los archivos están correctamente copiados y que el nombre del archivo principal coincide con el configurado en default.conf.

### 🧠 Autor
Ismael 
2º DAM - SGE 
Curso 2025
