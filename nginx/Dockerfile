# Comando a ejecutar para crear la imagen
# docker build -t "jonathan-nginx" .

# Arrancar
# docker run -d --name nginx -p 80:80 jonathan-nginx


FROM nginx:1.19.6

# NECESARIO PARA LAS VARIABLES 
COPY --from=hairyhenderson/gomplate:v3.8.0-slim /gomplate /bin/gomplate

# CARPETA NECESARIA CON LOS ARCHIVOS DE CONFIGURACION
COPY assets/ /assets

# DIRECTORIO EN EL CUAL NOS REDIGIREMOS AL CONECTARNOS EN EL CONTENEDOR
WORKDIR /var/www/html

# PUERTOS DEL CONTENEDOR
EXPOSE 80 443

# PARA CARGAR LAS VARIABLES
ENTRYPOINT ["/bin/bash","/assets/bin/docker-entrypoint.sh"]


CMD ["nginx", "-g", "daemon off;"]