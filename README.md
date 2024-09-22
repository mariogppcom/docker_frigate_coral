# docker_frigate_coral
Configuration for Frigate with Coral Edge TPU on Docker
docker run -d   --name frigate   --restart=unless-stopped   --mount type=tmpfs,target=/tmp/cache,tmpfs-size=1000000000   --device /dev/bus/usb:/dev/bus/usb   --device /dev/apex_0:/dev/apex_0   --shm-size=64m   -v /home/docker/frigat/storage:/media/frigate   -v /home/docker/frigate/config:/config   -v /etc/localtime:/etc/localtime:ro   -e FRIGATE_RTSP_PASSWORD='CHANGE YOU PASSWORD'   -p 5000:5000   -p 8971:8971   -p 8554:8554   -p 8555:8555/tcp   -p 8555:8555/udp   ghcr.io/blakeblackshear/frigate:stable

# Ports
5000 -> full access without auth (usefull for integration with Home Assistant)
8971 -> full access WITH auth. User and password is create using port 5000. 
