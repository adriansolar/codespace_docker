# Guía completa para comenzar con Docker 🐳

Docker es una plataforma diseñada para facilitar la creación, despliegue y ejecución de aplicaciones utilizando contenedores. Esta tecnología te permite empaquetar tu aplicación con todas sus dependencias en una unidad estandarizada, asegurando que funcione de la misma manera sin importar dónde se ejecute.

---

## 📦 ¿Qué es Docker?

Docker es una herramienta que permite que los desarrolladores, equipos de DevOps y operadores empaqueten aplicaciones en contenedores: entornos aislados que contienen todo lo necesario para ejecutar una app.

Al usar Docker, se evita el clásico problema de "en mi máquina funciona" al garantizar que la aplicación se ejecuta con la misma configuración en cualquier entorno: local, pruebas, producción o nube.

---

## 🧱 Imágenes vs Contenedores: ¿Cuál es la diferencia?

### 🖼️ Imágenes Docker

Una imagen Docker es una plantilla inmutable que define el entorno de ejecución. Contiene el sistema base (como Ubuntu, Alpine, etc.), dependencias, archivos fuente de la app y comandos para su ejecución. Es el punto de partida para crear contenedores.

### 📦 Contenedores Docker

Un contenedor es una instancia activa de una imagen. Puedes tener múltiples contenedores corriendo desde la misma imagen, cada uno aislado de los demás y del sistema anfitrión. Los contenedores son livianos, portables y rápidos de iniciar.

# Comandos Docker 

## Verifica la versión instalada de Docker
docker --version

## Descarga una imagen desde el Docker Hub
docker pull nginx

## Ejecuta un contenedor y mapea el puerto 8080 de tu máquina al 80 del contenedor
docker run -d -p 8080:80 nginx

## Lista los contenedores activos
docker ps

## Muestra todos los contenedores (activos e inactivos)
docker ps -a

## Detiene un contenedor (reemplaza [ID] por el real)
docker stop [ID]

## Elimina un contenedor detenido
docker rm [ID]

## Borra una imagen de tu sistema
docker rmi nginx

# 🐳 Crear tu propia imagen con un Dockerfile

## Usa una imagen base oficial
FROM node:18

## Crea un directorio de trabajo
WORKDIR /app

## Copia los archivos de tu app al contenedor
COPY package*.json ./
RUN npm install
COPY . .

## Define el puerto que expondrás
EXPOSE 3000

## Comando para iniciar la app
CMD ["node", "index.js"]

 
