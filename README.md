![motioneye logo](https://raw.githubusercontent.com/motioneye-project/motioneye/502614c699133b93f78d67492a6d2a502d366825/extra/motioneye.svg)
# Motioneye installation instruction for docker
Source repo: https://github.com/motioneye-project/motioneye

## What is Motioneye?
>Motion is a free software CCTV software application developed for Linux. It uses video4linux and its output can be jpeg, netpbm files, or mpeg video sequences. It is strictly command line driven and can run as a daemon with a rather small footprint and low CPU usage. - Wikipedia

## To run motioneye in docker comtainer using docker-compose file:
1. Run the following command: $ `docker-compose up -d`
2. Open web browser and go to http://localhost:8065/
3. Log in with username "admin" and no password
4. To add a camera:
   - Click the menu icon (upper left corner)
   - Click the "empty dropdown"
   - Select "add camera..."
5. On the "Add Camera..." popup
   - Select "Network Camera" from the "Camera Type" dropdown
   - Enter "rtsp://192.168.7.38/live" as the "URL" (do not include username/passowrd here)
   - Enter username and password
   - Select "RTSP/TCP" from the "Camera" dropdown

## To run motioneye in docker container using docker cli command:
   - $ `docker run --name="motioneye" -p 8065:8765 --hostname="motioneye" -v /etc/localtime:/etc/localtime:ro -v /etc/motioneye:/etc/motioneye -v /var/lib/motioneye:/var/lib/motioneye --restart="always"  --detach=true ccrisan/motioneye:master-amd64`
