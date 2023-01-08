# caddy-xray-vless-grpc-tls

```
apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | gpg --dearmor -o /usr/share/keyrings/caddy-stable-archive-keyring.gpg
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | tee /etc/apt/sources.list.d/caddy-stable.list
apt update
apt install caddy
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install -u root

# copy xray.json to /usr/local/etc/xray/config.json and replace the serviceName and uuid
vim /usr/local/etc/xray/config.json
systemctl restart xray

# copy Caddyfile to /etc/caddy/Caddyfile and replace the domain and serviceName
vim /etc/caddy/Caddyfile
systemctl restart caddy

# make a fake website
```
