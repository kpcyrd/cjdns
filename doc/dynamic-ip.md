Peering with dynamic IPs with cjdns
===================================

It's possible to use a DNS name in your cjdroute.conf, but the name will be resolved while loading the configuration, so IP changes after that point will be unnoticed.

There's a script in contrib/python to work around that.

Setup
-----

Copy `contrib/python/dynamicEndpoints.conf.example` to `/etc/dynamicEndpoints.conf` and edit it.

    cp contrib/python/dynamicEndpoints.conf.example /etc/dynamicEndpoints.conf

Make sure dynamicEndpoints gets started on boot.

There's a systemd unit in `contrib/systemd`

    cp contrib/systemd/cjdroute-dynep.service /etc/systemd/system/
    systemctl enable cjdroute-dynip
    systemctl start cjdroute-dynip

