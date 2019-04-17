```bash
[root@srvdocker-t system]# tar -C /usr/local -zvxf node_exporter-0.15.2.linux-amd64.tar.gz
[root@srvdocker-t system]# vim /etc/systemd/system/exporter.service
[root@srvdocker-t system]# systemctl enable exporter.service
Created symlink from /etc/systemd/system/multi-user.target.wants/exporter.service to /usr/lib/systemd/system/exporter.service.
[root@srvdocker-t system]# systemctl start exporter.service
[root@srvdocker-t system]# systemctl daemon-reload
```

exporter.service 內容

```sh
[Unit]
Description=node exporter

[Service]
Type=simple
ExecStart=/usr/local/node_exporter-0.15.2.linux-amd64/node_exporter --web.listen-address=:9111

[Install]
WantedBy=multi-user.target
```
