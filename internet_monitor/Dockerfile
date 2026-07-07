FROM ghcr.io/home-assistant/base:latest

LABEL \
    org.opencontainers.image.title="Internet Monitor" \
    org.opencontainers.image.description="Monitor internet connectivity and record internet outages." \
    org.opencontainers.image.source="https://github.com/mariorauh/internet-monitor-backend" \
    org.opencontainers.image.licenses="MIT"

COPY run.sh /

RUN chmod a+x /run.sh

CMD ["/run.sh"]