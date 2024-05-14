To use this WordPress Cluster stack 

1. create .env file that declare environment variables for docker-compose like
```bash
MYSQL_ROOT_PASSWORD=password
MYSQL_DATABASE=wordpress
MYSQL_USER=wordpress
MYSQL_PASSWORD=password

WORDPRESS_DB_HOST=db
WORDPRESS_DB_USER=wordpress
WORDPRESS_DB_PASSWORD=password
WORDPRESS_DB_NAME=wordpress
```

2. go to conf/kong.yml edit domain name of you website
and configuration certification ssl put cert and key 

```bash
services:
  routes:
  - name: domain
    hosts:
    - www.domain.com 
    protocols:
    - https
    https_redirect_status_code: 302
    preserve_host: true

certificates:
- cert: "-----BEGIN CERTIFICATE----- -----END CERTIFICATE-----"
  key: "-----BEGIN PRIVATE KEY----- -----END PRIVATE KEY-----"
  snis:
  - name: www.domain.com

```

3. after that let's
```bash
docker-compose up -d 

```

4. install nginx-helper plugin on Wordpress
```
Enable Purge

Caching Method
Redis cache
Hostname: redis
Port: 6379
Prefix: nginx-cache:
```

## REF
```
https://www.youtube.com/watch?v=_xBNgg4Ih8I
```
