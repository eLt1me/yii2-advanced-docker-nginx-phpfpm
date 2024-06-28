FROM nginx:alpine

COPY ./hosts /etc/nginx/templates

WORKDIR ${CONTAINER_PROJECT_LOCATION}

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]