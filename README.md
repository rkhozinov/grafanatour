# grafanatour

Start your image binding the external port 3000.

`docker run -i -p 3000:3000 grafana/grafana`

Try it out, default admin user is admin/admin.

Configuring your Grafana container
All options defined in conf/grafana.ini can be overriden using environment variables, for example:

```
docker run -i -p 3000:3000 \
  -e "GF_SERVER_ROOT_URL=http://grafana.server.name"  \
  -e "GF_SECURITY_ADMIN_PASSWORD=secret  \
  grafana/grafana
```

Simple persistance storage for Grafana
```
docker run -d -v /var/lib/grafana --name storage busybox:latest
docker run -d -p 3000:3000 --name=grafana --volumes-from storage grafana/grafana
```
##Links to sources:
- [Grafana on Docker Hub] (https://hub.docker.com/r/grafana/grafana/)
- [Grafana Configuration] (http://docs.grafana.org/installation/configuration/)
- [Grafana Dockerfile] (http://docs.grafana.org/installation/configuration/)


