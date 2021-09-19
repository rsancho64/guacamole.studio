De [guacamole oficial](http://guacamole.incubator.apache.org/doc/gug/installing-guacamole.html)

## guacamole server nativo (deb11)

### Dependencies

1. Must

```bash
sudo apt-get install -y libcairo2-dev # cairo
sudo apt-get install -y libjpeg62-turbo-dev # libjpeg: libjpeg-turbo (libjpeg62-dev if not)
sudo apt-get install -y libpng12-dev # libpng (libpng16-16 -rutime- libpng-dev y libpng-tools en deb11)
sudo apt-get install -y libtool-bin # (libtool, libtool-bin en deb11)
sudo apt-get install -y libossp-uuid-dev # OSSP UUID
```

2. Optional

```bash
sudo apt-get install -y libavcodec-dev libavformat-dev libavutil-dev libswscale-dev # FFmpeg: 
sudo apt-get install -y freerdp2-dev # FreeRDP: 
sudo apt-get install -y libpango1.0-dev # Pango: 
sudo apt-get install -y libssh2-1-dev # libssh2: 
sudo apt-get install -y libtelnet-dev # libtelnet: 
sudo apt-get install -y libvncserver-dev # libVNCServer: 
sudo apt-get install -y libwebsockets-dev # libwebsockets: 
sudo apt-get install -y libpulse-dev # PulseAudio: 
sudo apt-get install -y libssl-dev # OpenSSL: 
sudo apt-get install -y libvorbis-dev # libvorbis: 
sudo apt-get install -y libwebp-dev # libwebp: 
```
### Deploy

```bash
sudo git clone git://github.com/apache/guacamole-server.git
cd guacamole-server/
sudo autoreconf -fi 
sudo ./configure --with-init-dir=/etc/init.d # ok:  see /etc/init.d/guacd : POSIX shell scritp, ASCII +x
sudo make && sudo make install # ok. see man guacd
sudo ldconfig
sudo systemctl daemon-reload
sudo systemctl start guacd
sudo service guacd status
```

## guacamole client (deb11)
