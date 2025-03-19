# Dockerfile
FROM frappe/erpnext-worker:v13

# Set environment variables
ARG MARIADB_HOST
ARG DB_PORT
ARG DB_USER
ARG DB_PASSWORD
ARG DB_NAME

ENV MARIADB_HOST=$MARIADB_HOST
ENV DB_PORT=$DB_PORT
ENV DB_USER=$DB_USER
ENV DB_PASSWORD=$DB_PASSWORD
ENV DB_NAME=$DB_NAME

WORKDIR /home/frappe/frappe-bench

# Run the application
CMD ["bench", "start"]
