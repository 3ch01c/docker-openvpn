# docker-openvpn

# Quick Start
Configure time zone in `docker-compose.yml`.

```
TZ=America/Denver
```

Add SSL key to`config/etc/web-ssl`. (If you don't have one, why not try [certbot](https://certbot.eff.org/)?)

``
cp /srv/certbot/etc/live/SERVERNAME/cert.pem /srv/openvpn-as/config/etc/web-ssl/server.crt
cp /srv/certbot/etc/live/SERVERNAME/chain.pem /srv/openvpn-as/config/etc/web-ssl/ca.crt
cp /srv/certbot/etc/live/SERVERNAME/privkey.pem /srv/openvpn-as/config/etc/web-ssl/server.key
```

Start up server.

```
docker-compose up
```

Log in to the admin interface at https://HOSTNAME:943 with the default credentials `admin:password`. Create a new user with admin rights and delete the admin user. In `config/as.conf`, replace `boot_pam_users.0=admin` to a nonexistent user name.

More details can be found at https://github.com/linuxserver/docker-openvpn-as.
