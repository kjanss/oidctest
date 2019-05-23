# oidctest

Quick test for an oidconnect app

##Usage:
Pull the docker image or build your own (simple apache web server with mod_auth_oidc and mod_ssl installed):

```
docker pull koenj/centos-oidc:v1.2
```

Create the container and use named volumes for the certificate files, the webroot, the server configuration and the logs:

```
docker create -d -p 8002:80 -p 4443:443 -v htpki:/etc/pki -v htdocs2:/var/www/ -v htetc2:/etc/httpd -v htlogs:/var/log/httpd koenj/centos-oidc:v1.2
```
The named volumes will be created in your docker partition.

Copy the files from the repo to the named volumes.
Start the container.
