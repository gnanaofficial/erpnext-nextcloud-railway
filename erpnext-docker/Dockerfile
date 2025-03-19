# Dockerfile
FROM frappe/erpnext-worker:v13

WORKDIR /home/frappe/frappe-bench

# Create the sites directory and add required files
RUN mkdir -p sites && \
    echo "frappe" > sites/apps.txt && \
    echo "erpnext" >> sites/apps.txt && \
    cat <<EOF > sites/common_site_config.json
{
  "db_host": "mariadb",
  "db_port": "3306",
  "db_name": "erpnext",
  "db_user": "erpuser",
  "db_password": "erpnextpass",
  "redis_cache": "redis://redis-cache:6379",
  "redis_queue": "redis://redis-queue:6379",
  "redis_socketio": "redis://redis-socketio:6379"
}
EOF

# Copy local sites to container
COPY sites /home/frappe/frappe-bench/sites/

# Set ownership and permissions
RUN chown -R frappe:frappe /home/frappe/frappe-bench/sites && \
    chmod -R 755 /home/frappe/frappe-bench/sites

# Expose required ports
EXPOSE 8000 9000 6787

# Run ERPNext
CMD ["bench", "start"]
