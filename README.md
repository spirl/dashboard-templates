# Dashboard Templates

This repository contains dashboard templates for Defakto (formerly SPIRL) components. These templates can be imported into specific telemetry systems to visualize the metrics exposed by Defakto components.

## Available Dashboards
- [Grafana](grafana)

### Grafana

| Dashboard | File | Use it for |
| --- | --- | --- |
| SPIRL Trust Domain Agents | `grafana/spirl-agent.json` | Agents that emit `spirl_*` metrics. |
| SPIRL Trust Domain Server | `grafana/spirl-trust-domain-server.json` | Servers that emit `spirl_*` metrics. |
| SPIRL Trust Domain Reflector | `grafana/spirl-reflector.json` | Reflectors that emit `spirl_*` metrics. |
| Defakto Agent | `grafana/defakto-agent.json` | Fleets that emit `defakto_*` metrics: `defakto-agent`, or SPIRL builds from spirl-system chart v0.48.1 onwards. |
| Defakto Server | `grafana/defakto-server.json` | Fleets that emit `defakto_*` metrics: `defakto-server`, or SPIRL server v0.41.1 onwards. |
| Defakto Reflector | `grafana/defakto-reflector.json` | Reflectors that emit `defakto_*` metrics (every current reflector does). |
| Service Mesh | `grafana/service-mesh.json` | Istio service mesh traffic, unchanged. It relies on the customer-set `spirl-enabled` pod label. |

Each dashboard shows only its own metric family: a SPIRL dashboard does not show `defakto_*` metrics, and a Defakto dashboard does not show `spirl_*` metrics. While a fleet is migrating, use both dashboards side by side, or build a combined dashboard from the two templates.

The Defakto dashboards use the `defakto_trust_domain` and `defakto_trust_domain_deployment` variable names, so URLs bookmarked from a SPIRL dashboard (`var-spirl_trust_domain=...`) do not carry over.
