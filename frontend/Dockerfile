FROM nginx:alpine

# Create non-root user
RUN adduser -D appuser \
    && mkdir -p /var/cache/nginx /var/run /run \
    && chown -R appuser:appuser /var/cache/nginx /var/run /run /usr/share/nginx/html

# Copy static files
COPY index.html /usr/share/nginx/html/
COPY style.css /usr/share/nginx/html/
COPY app.js /usr/share/nginx/html/

# Switch to non-root user
USER appuser

EXPOSE 80

# Start nginx without daemon mode
CMD ["nginx", "-g", "daemon off;"]
