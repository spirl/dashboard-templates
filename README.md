# Dashboard Templates

This repository contains dashboard templates for SPIRL and Defakto components. These templates can be imported into specific telemetry systems to visualize the metrics exposed by those components.

## Available Dashboards
- [Grafana](grafana)

### Grafana

| Dashboard | File | Metrics | Supported releases |
| --- | --- | --- | --- |
| SPIRL Trust Domain Agents | `grafana/spirl-agent.json` | `spirl_*` | All `spirl-agent` releases. |
| SPIRL Trust Domain Server | `grafana/spirl-trust-domain-server.json` | `spirl_*` | All `spirl-server` releases. |
| SPIRL Trust Domain Reflector | `grafana/spirl-reflector.json` | `spirl_*` | All reflector releases. |
| Defakto Agent | `grafana/defakto-agent.json` | `defakto_*` | `spirl-agent` from `spirl-system` v0.48.1, and all `defakto-agent` releases. |
| Defakto Server | `grafana/defakto-server.json` | `defakto_*` | `spirl-server` from v0.41.1, and all `defakto-server` releases. |
| Defakto Reflector | `grafana/defakto-reflector.json` | `defakto_*` | Reflector from `spirl-system` v0.48.1. |
| Service Mesh | `grafana/service-mesh.json` | Istio | All releases. Shows traffic for pods with the `spirl-enabled` label. |

SPIRL releases that support both dashboards expose `spirl_*` and `defakto_*` metrics side by side. `defakto-agent` and `defakto-server` expose only `defakto_*` metrics.

Each dashboard shows only its own metric family. While a fleet is migrating, use both dashboards side by side, or build a combined dashboard from the two templates.

The Defakto dashboards use the `defakto_trust_domain` and `defakto_trust_domain_deployment` variable names, so URLs bookmarked from a SPIRL dashboard (`var-spirl_trust_domain=...`) do not carry over.
