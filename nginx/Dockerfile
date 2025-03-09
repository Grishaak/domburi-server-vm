FROM nginx:alpine

# Создаем папки для кеша и PID-файла с правильными правами
RUN mkdir -p /var/cache/nginx/client_temp && \
    mkdir -p /var/run && \
    chown -R nginx:nginx /var/cache/nginx /var/run && \
    chmod -R 755 /var/cache/nginx /var/run

# Копируем конфиг
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Запускаем от пользователя nginx (не root)
USER nginx
