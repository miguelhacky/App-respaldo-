Markdown
# Taller de Contenedorización con Docker - Gestor de Tareas

Aplicación web full-stack compuesta por un frontend en Nginx, una API backend en Python (Flask) y una base de datos relacional (MySQL), totalmente contenedorizada y orquestada mediante Docker Compose.

---

## 🛠️ Arquitectura del Proyecto

El sistema se divide en tres servicios principales aislados en una red interna de Docker:
1. **Frontend (`nginx`)**: Servidor web que sirve la interfaz estática y actúa como proxy inverso redirigiendo las peticiones `/api/` hacia el backend.
2. **API (`python/flask`)**: Backend encargado de gestionar la lógica de negocio y la persistencia de tareas conectándose a la base de datos.
3. **Base de Datos (`mysql`)**: Almacena las tareas de forma persistente utilizando volúmenes de Docker para evitar la pérdida de información ante reinicios.

---

## 📋 Requisitos Previos

* [Docker Desktop](https://www.docker.com/) instalado y en ejecución.
* Git (opcional para control de versiones).

---

## ⚙️ Configuración del Entorno

1. En la raíz del proyecto, asegúrate de tener configurado tu archivo de variables de entorno `.env` basándote en la plantilla `.env.example`:
env
DB_ROOT_PASSWORD=toclavefacil123
DB_NAME=tareas_db
DB_USER=adso
DB_PASSWORD=tuclaveusuario123


---

## 🚀 Ejecución del Proyecto

Para encender toda la infraestructura en segundo plano y construir las imágenes, ejecuta el siguiente comando en la raíz del proyecto:

powershell
docker compose up -d --build


### Comprobación de Estado
Verifica que los tres contenedores se encuentren activos (*Up*):
powershell
docker compose ps


---

## 🌐 Acceso a la Aplicación

Una vez iniciados los servicios, abre tu navegador web de preferencia y accede a:
👉 **`http://localhost:8080`**

---

## 🛑 Detener los Servicios

Para apagar y limpiar los contenedores del proyecto de forma segura:
powershell
docker compose down

*(Nota: Los datos de la base de datos se mantendrán seguros gracias al volumen persistente).*

---

## 👨‍💻 Autor
**Miguel Fajardo**  
Tecnólogo en Análisis y Desarrollo de Software (ADSO) - SENA
Cómo verificar: El archivo se guardará correctamente y se visualizará formateado en la pestaña del editor.