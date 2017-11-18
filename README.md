# docker_compose

## filesahre

## docker-zabbix

### Zabbix Server Full
_zabbix-server-full.yml_ file runs:
- Zabbix Server
- Zabbix Web Interface
- Zabbix SQLite3 Proxy
- Zabbix Java Gateway
- Zabbix Snmptraps
- Postgres Server

### Zabbix Server Middle
_zabbix-server.yml_ runs:
- Zabbix Server
- Zabbix Web Interface
- Postgres Server
- Zabbix SQLite3 Proxy

### Zabbix Server
_zabbix-server.yml_ runs:
- Zabbix Server
- Zabbix Web Interface
- Postgres Server

### Generate NGINX SSL Certificates:
```bash
$ cd ${VOLUME_DIR}/etc/ssl/nginx
$ sudo openssl req -x509 -nodes -days 365 \
    -newkey rsa:2048 \
    -keyout ssl.key \
    -out ssl.crt
$ sudo openssl dhparam -out dhparam.pem 4096
```

### Zabbix Agent installation

### Manage firewall with _firewall-cmd_
```bash
$ sudo firewall-cmd --permanent --new-service=zabbix
$ sudo firewall-cmd --permanent --service=zabbix --add-port=10051/tcp
$ sudo firewall-cmd --permanent --service=zabbix --add-port=10052/tcp
$ sudo firewall-cmd --permanent --service=zabbix --add-port=10041/tcp
$ sudo firewall-cmd --permanent --zone=public --add-service=zabbix
$ sudo firewall-cmd --reload
```
