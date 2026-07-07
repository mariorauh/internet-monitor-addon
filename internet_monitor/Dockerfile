FROM ghcr.io/home-assistant/base:latest

LABEL \
    org.opencontainers.image.title="Internet Monitor" \
    org.opencontainers.image.description="Monitor internet availability and record outages." \
    org.opencontainers.image.licenses="MIT"

WORKDIR /app

RUN \
    apk add --no-cache \
        python3 \
        py3-pip

COPY requirements.txt /tmp/

RUN pip3 install --no-cache-dir --break-system-packages -r /tmp/requirements.txt

COPY app/ /app/

COPY addon/internet_monitor/run.sh /run.sh

RUN chmod a+x /run.sh

CMD ["/run.sh"]