# Internet Monitor

The Internet Monitor is a Home Assistant Add-on that continuously monitors your Internet connection and detects outages in real time.

The add-on performs regular

- HTTP connectivity checks
- DNS availability checks
- ICMP ping measurements
- Packet loss measurements

and provides the current monitoring status via a built-in REST API.

---

# Features

- Continuous Internet monitoring
- HTTP availability check
- DNS availability check
- ICMP ping monitoring
- Packet loss monitoring
- Automatic outage detection
- REST API
- Configurable monitoring parameters
- Lightweight and resource-efficient

---

# Installation

1. Open the **Home Assistant Add-on Store**.
2. Add the Internet Monitor repository:

```
https://github.com/mariorauh/internet-monitor-addon
```

3. Install the **Internet Monitor** add-on.
4. Configure the monitoring settings if required.
5. Start the add-on.

---

# Configuration

The following options can be configured directly from the Home Assistant UI.

| Option | Description | Default |
|---------|-------------|---------|
| HTTP Target | URL used for the HTTP availability check | https://www.google.com |
| HTTP Timeout | HTTP request timeout in seconds | 5 |
| DNS Target | DNS server used for DNS availability checks | 8.8.8.8 |
| Ping Target | Host used for ICMP ping | 1.1.1.1 |
| Ping Count | Number of ICMP packets per measurement | 4 |
| Ping Timeout | Timeout per ICMP packet in seconds | 2 |
| Check Interval | Monitoring interval in seconds | 5 |

All configured values are logged during application startup.

---

# REST API

The add-on exposes the current monitoring status via HTTP.

## Endpoint

```
GET /status
```

Example response

```json
{
    "internet": true,
    "dns": true,
    "ping": 21.84,
    "packet_loss": 0.0,
    "timestamp": "2026-07-10T10:15:30Z",
    "version": "0.3.1"
}
```

If the add-on is running on Home Assistant, the API is available at

```
http://<HOME_ASSISTANT_IP>:8080/status
```

---

# Logging

During startup the add-on logs

- application version
- monitoring configuration
- monitoring interval

During operation every measurement is logged including

- Internet status
- DNS status
- Ping latency
- Packet loss

The log buffer is automatically limited to the latest **10,000 log entries**.

---

# Troubleshooting

If the add-on does not start correctly:

1. Open the add-on.
2. Navigate to **Log**.
3. Verify the configured monitoring parameters.
4. Ensure the configured HTTP, DNS and Ping targets are reachable.

---

# Support

Backend Repository

https://github.com/mariorauh/internet-monitor-backend

Issue Tracker

https://github.com/mariorauh/internet-monitor-backend/issues

---

# License

MIT License