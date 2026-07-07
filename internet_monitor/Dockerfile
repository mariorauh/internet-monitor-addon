FROM ghcr.io/mariorauh/internet-monitor-backend:latest

LABEL \
    org.opencontainers.image.title="Internet Monitor" \
    org.opencontainers.image.description="Monitor internet connectivity and record outages." \
    org.opencontainers.image.source="https://github.com/mariorauh/internet-monitor-backend" \
    org.opencontainers.image.licenses="MIT"

COPY run.sh /

RUN chmod a+x /run.sh

CMD ["/run.sh"]