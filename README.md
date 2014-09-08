# ENV Settings

- `APP_NAME`
- `DJANGO_SETTINGS_MODULE`
- `NUM_WORKERS`

docker run -d \
-v `pwd`/volumes/logs:/home/app/app/logs \
-v `pwd`/volumes/run:/home/app/run \
test


docker ps -a | awk '{print $1}' | xargs docker stop | xargs docker rm
