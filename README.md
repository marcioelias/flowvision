# FlowVision

NetFlow/IPFIX collector and analytics platform with ML anomaly detection.

## Quick install

```bash
curl -fsSL https://raw.githubusercontent.com/marcioelias/flowvision/main/install.sh | sudo bash
```

Requires Docker. Tested on Ubuntu 22.04+, Debian 12, RHEL 9.

### Specific version

```bash
VERSION=1.1.0-beta.1 curl -fsSL https://raw.githubusercontent.com/marcioelias/flowvision/main/install.sh | sudo bash
```

### With LLM explainability (Ollama)

```bash
curl -fsSL https://raw.githubusercontent.com/marcioelias/flowvision/main/install.sh | sudo bash -s -- --with-llm
```

## Update

```bash
sudo flowvision-update 1.2.0
```

## What gets installed

| Service | Image | Port |
|---|---|---|
| Collector (Rust) | `ghcr.io/marcioelias/flowvision-collector` | 2055/udp, 3000/tcp |
| Dashboard (Vue) | `ghcr.io/marcioelias/flowvision-dashboard` | 8080/tcp |
| ClickHouse | `clickhouse/clickhouse-server:23.8` | internal |
| ExaBGP (optional) | `pierky/exabgp:4.2.11` | host network |
| Ollama (optional) | `ollama/ollama` | 11434/tcp |

## Ports to open

- `2055/udp` — NetFlow v5/v9, IPFIX
- `8080/tcp` — Web dashboard

## Default credentials

User: `admin` / Password: `admin123`

**Change immediately after first login.**

## License

FlowVision is commercial software. A valid license is required for production use.
Contact: [marcioelias@gmail.com](mailto:marcioelias@gmail.com)
