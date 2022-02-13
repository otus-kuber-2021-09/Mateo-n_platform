FROM nginx

WORKDIR /app

COPY nginx.conf /etc/nginx/

COPY app/ /app/

RUN usermod -u 1001  nginx                   && \
    groupmod -g 1001  nginx                  && \
    chown -R nginx:nginx /app                && \
    chmod -R 755 /app                        && \
    chown -R nginx:nginx /var/cache/nginx    && \
    chown -R nginx:nginx /var/log/nginx      && \
    chown -R nginx:nginx /etc/nginx/conf.d   && \
    touch /var/run/nginx.pid                 && \
    chown -R nginx:nginx /var/run/nginx.pid  && \
    chmod 777 /etc/nginx/nginx.conf
	
USER nginx

EXPOSE 8000
