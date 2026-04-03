FROM haproxy:2.0.5

RUN sed -i 's|deb.debian.org/debian|archive.debian.org/debian|g' /etc/apt/sources.list \
    && sed -i 's|security.debian.org/debian-security|archive.debian.org/debian-security|g' /etc/apt/sources.list \
    && sed -i '/buster-updates/d' /etc/apt/sources.list \
    && apt-get -o Acquire::Check-Valid-Until=false update \
    && apt-get install -y curl \
    && rm -rf /var/lib/apt/lists/*

COPY haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg
