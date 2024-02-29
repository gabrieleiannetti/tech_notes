# Docker

## Service Disable and Startup as Required

Disable the service:  

`systemctl disable docker`

 > The service starts as soon as a container is launched

## exec

`docker exec [OPTIONS] CONTAINER COMMAND [ARG...]`

### Bash in Container

```bash
# Connect to docker image and open bash
sudo docker exec -ti CONTAINER bash
```
