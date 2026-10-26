# Dashboard Templates

This repository contains dashboard templates for Defakto (formerly SPIRL) components. These templates can be imported into specific telemetry systems to visualize the metrics exposed by Defakto components.

## Available Dashboards
- [Grafana](grafana)

### Grafana

| Dashboard | File | Use it for |
| --- | --- | --- |
| SPIRL Agent | `grafana/spirl-agent.json` | Agents of any version. Shows both `spirl_*` and `defakto_*` metrics, so a mixed fleet appears in one dashboard. |
| SPIRL Trust Domain Server | `grafana/spirl-trust-domain-server.json` | Servers of any version, with the same behavior as the SPIRL Agent dashboard. |
| SPIRL Reflector | `grafana/spirl-reflector.json` | Reflectors of any version, with the same behavior as the SPIRL Agent dashboard. |
| Defakto Agent | `grafana/defakto-agent.json` | Fleets that emit `defakto_*` metrics: `defakto-agent`, or SPIRL builds from spirl-system chart v0.48.1 onwards. |
| Defakto Server | `grafana/defakto-server.json` | Fleets that emit `defakto_*` metrics: `defakto-server`, or SPIRL server v0.41.1 onwards. |
| Defakto Reflector | `grafana/defakto-reflector.json` | Reflectors that emit `defakto_*` metrics (every current reflector does). |
| Service Mesh | `grafana/service-mesh.json` | Istio service mesh traffic, unchanged. It relies on the customer-set `spirl-enabled` pod label. |

Pick a SPIRL dashboard if any component in the fleet still emits only `spirl_*` metrics, or while a fleet is migrating. Pick a Defakto dashboard once every component emits `defakto_*` metrics. A Defakto dashboard does not show builds that emit only `spirl_*` metrics.

Dashboards already imported into Grafana do not update on their own. Import the new JSON again to pick up changes. The dashboard UIDs are unchanged, so importing over an existing SPIRL dashboard replaces it in place.

The SPIRL dashboards keep their `spirl_trust_domain` and `spirl_trust_domain_deployment` variable names so that bookmarked URLs (`var-spirl_trust_domain=...`) keep working. The Defakto dashboards use `defakto_trust_domain` and `defakto_trust_domain_deployment`.
