# 1.- CONSTRUIR LA IMAGEN DOCKER EN UN CONTENEDOR LIMPIO PARA ASEGURAR QUE EL AMBIENTE SE PUEDE RECREAR SIN PROBLEMAS
FROM node:18.15-alpine as build-stage 
LABEL version="1.0"
LABEL maintainer="Israel Arellano"

# CONSTRUIR LA APLICACION
WORKDIR /app
COPY . .
RUN yarn install --only=production
RUN addgroup -S demo && adduser -S demo -G demo
RUN chown demo:demo /app
USER demo:demo

EXPOSE 8000
# Comando para iniciar la aplicación
CMD [ "npm", "start" ]
