FROM ubuntu

# Install Nginx and utilities
RUN apt-get -y update           && \
    apt-get install -y             \
        nginx                      \
        curl                       \
        iproute2                && \
    rm -rf /var/lib/apt/lists/*

# Redirect logs to stdout/sderr for Docker logging
RUN ln -sf /dev/stdout /var/log/nginx/access.log && \
    ln -sf /dev/stderr /var/log/nginx/error.log

# Expose port for HTTP traffic
EXPOSE 80

# Redefine Signal for stopping container
STOPSIGNAL SIGTERM

# Define health check parameters
HEALTHCHECK --interval=3s CMD curl --fail -m 2 http://localhost:80/ || exit 1

# Define what gets executed
ENTRYPOINT ["/usr/sbin/nginx", "-g", "daemon off;"]