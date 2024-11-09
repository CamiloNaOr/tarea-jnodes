FROM node:alpine

WORKDIR /app

# Configura npm para usar un mirror alternativo si es necesario (opcional)
RUN npm config set registry https://registry.npmmirror.com

# Copia solo los archivos de package primero
COPY ../package*.json ./

# Instala solo las dependencias necesarias con npm ci
RUN npm ci --no-optional --verbose

# Copia el resto del código fuente
COPY . .

# Construye la aplicación para producción
RUN npm run build

EXPOSE 3000
CMD ["npm", "start"]