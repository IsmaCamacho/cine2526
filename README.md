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

### 1. Clonar el repositorio

```bash
git clone https://github.com/IsmaCamacho/cine2526
cd cine2526
```

2. Preparar la configuración de Nginx
Dentro de la carpeta nginx/, crea el archivo default.conf con el siguiente contenido:

nginx
server {
    listen 80;
    server_name localhost;

    location / {
        root /usr/share/nginx/html;
        index cine.html;
        try_files $uri $uri/ =404;
    }
}
Asegúrate de que el archivo principal de tu aplicación se llama cine.html y está dentro de la carpeta src/.

