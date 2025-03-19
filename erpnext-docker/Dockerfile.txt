# ERPNext Dockerfile
FROM frappe/erpnext:latest

# Copy Docker Compose file
COPY docker-compose.yml /app/docker-compose.yml

# Start ERPNext
CMD ["bench", "start"]
