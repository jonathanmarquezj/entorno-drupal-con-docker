# Comando a ejecutar para crear la imagen
# docker build -t "nginx:1.19.6.jonathan" .

FROM nginx:1.19.6

WORKDIR /var/www/html
EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]