FROM nginx:latest


COPY nginx/nginx.conf /etc/nginx/nginx.conf
COPY index.html /usr/share/nginx/html
COPY main.js /usr/share/nginx/html
COPY style.css /usr/share/nginx/html


EXPOSE 80


CMD ["nginx", "-g", "daemon off;"]
