# Добавление роутинга `RoscomVPN` в Marzneshin для пользователей JSON-подписок
- Положите файл subscription.py в `/var/lib/marzneshin`
- Прилинкуйте файл строкой `- /var/lib/marzneshin/subscription.py:/app/app/routes/subscription.py` в начале файла `/etc/opt/marzneshin/docker-compose.yml`, чтобы стало так:
```yaml
...
    volumes:
      - /var/lib/marzneshin:/var/lib/marzneshin
      - /var/lib/marzneshin/subscription.py:/app/app/routes/subscription.py
...
```
- Перезагрузите Marzneshin - `marzneshin restart`
- Готово! Теперь в Happ вместе с подписками поставляется всегда свежие файлы geoip.dat и geosite.dat от `RoscomVPN`
- Теперь в ваш JSON вставляйте любые правила из основного роутинга `RoscomVPN`, посмотреть их можно например в файле RAW.JSON/RAWUNFILTERED.JSON в корне данного репо