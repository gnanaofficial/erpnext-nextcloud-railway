FROM frappe/erpnext:latest

# Expose the correct port for ERPNext
EXPOSE 8000

# Set working directory
WORKDIR /home/frappe/frappe-bench

# Copy any custom configurations if needed
# COPY config.json /home/frappe/frappe-bench/sites/common_site_config.json

# Start ERPNext
CMD ["bench", "start"]