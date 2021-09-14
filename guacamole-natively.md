## guacamole server nativo

[installing guacamole](http://guacamole.incubator.apache.org/doc/gug/installing-guacamole.html)
```bash
git clone git://github.com/apache/guacamole-server.git
cd guacamole-server/
# must autoconf : apt install autoconf
# must libtool : apt install libtool
autoreconf -fi 
./configure --with-init-dir=/etc/init.d
ls /etc/init.d # /etc/init.d/guacd
make
make install
ldconfig
systemctl daemon-reload
systemctl start guacd
service guacd status
history
```