FROM nginx:1.17.9-alpine
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]