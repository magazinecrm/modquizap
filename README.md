# modquizap
modifiedquzapp
ngx setting.
default.conf
sss # cat default.conf
server {
  listen       80;
  listen       443 ssl;
  server_name  localhost;

  ssl_certificate   /etc/cert.pem;
  ssl_certificate_key  /etc/privkey.pem;

location / {
    proxy_pass http://localhost:3010;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;
  }
}
-------------------
/etc/nginx/conf.d
-------------------
systemctl start nginx
----------
service nginx stop
systemctl stop nginx
-----------------

service nginx restart
systemctl restart nginx
-----------
service nginx reload
systemctl reload nginx
---
service nginx status
systemctl status nginx
----------
nginx -t
--------
