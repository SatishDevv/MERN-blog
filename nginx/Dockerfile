# Base image
FROM nginx:alpine

# Copy Nginx configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Health check
# HEALTHCHECK --interval=30s --timeout=5s --start-period=10s --retries=3 \
#  CMD curl --fail http://localhost:80 || exit 1

CMD [ "nginx","-g","daemon off;" ]

