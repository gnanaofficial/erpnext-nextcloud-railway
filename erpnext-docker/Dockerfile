# Dockerfile
FROM frappe/erpnext-worker:v13

WORKDIR /home/frappe/frappe-bench

# Create frappe user and group explicitly to avoid permission errors
RUN addgroup --system frappe && adduser --system --home /home/frappe --ingroup frappe frappe

# Copy sites directory with required files
COPY sites /home/frappe/frappe-bench/sites/

# Set ownership and permissions correctly
RUN chown -R frappe:frappe /home/frappe/frappe-bench/sites && \
    chmod -R 755 /home/frappe/frappe-bench/sites

# Expose necessary ports for ERPNext
EXPOSE 8000 9000 6787

# Run ERPNext
CMD ["bench", "start"]
