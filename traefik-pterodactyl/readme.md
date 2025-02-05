## Traefik + Pterodactyl

В данном репозитории находится шаблон docker контейнеров

### Команды

    make in - перейти в контейнер (docker exec)

	make up - обновить контейнеры (docker compose up -d)

    make stop - остановить контейнеры (docker compose stop)

    make down - удаление контейнеров и сетей (docker compose down)

	make start - запуск контейнеров (docker compose start)

    make certs - генерирует самоподписные сертификаты (для тестов)