FROM alpine:3.13

RUN wget https://github.com/SagerNet/v2ray-core/releases/download/v5.0.12/v2ray-linux-64.zip \
    && unzip v2ray-linux-64.zip

RUN mkdir -p /usr/local/etc/v2ray \
    && mkdir -p /usr/local/share/v2ray \
    && cp geoip.dat geosite.dat /usr/local/share/v2ray \
    && cp v2ray /usr/local/bin \
    && chmod 755 /usr/local/bin/v2ray \
    && mkdir -p /etc/v2ray && touch /etc/v2ray/ \
    && mkdir -p /var/log/v2ray

ENV PATH /usr/bin/v2ray:$PATH
CMD ["v2ray", "run", "-c", "/etc/v2ray/config.json"]
