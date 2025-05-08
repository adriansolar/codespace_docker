# Introducción a Dockerfile 🐳

Un **Dockerfile** es un archivo de texto que contiene una serie de instrucciones para construir una imagen Docker. Piensa en él como la receta que Docker sigue para crear la imagen que luego se usará para ejecutar contenedores.

---

## 📄 Estructura básica de un Dockerfile

A continuación, se presenta un ejemplo de Dockerfile para una aplicación Node.js:

```dockerfile
# Usamos una imagen base oficial de Node.js
FROM node:14

# Establecemos el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copiamos los archivos de la aplicación al contenedor
COPY package*.json ./
RUN npm install
COPY . .

# Exponemos el puerto en el que la aplicación correrá
EXPOSE 3000

# Comando para ejecutar la aplicación
CMD ["node", "index.js"]