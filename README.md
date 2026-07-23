# Monitoring Kubernetes system service for Wodby

Monitoring collects and forwards Kubernetes cluster telemetry for Wodby
infrastructure observability.

This repository defines the Wodby service manifests and operational
configuration for Monitoring.

- [Wodby Kubernetes platform](https://wodby.com)
- [Wodby service documentation](https://wodby.com/docs/2.0/services/)
- [Service manifest reference](https://wodby.com/docs/2.0/services/template/)

## Wodby system stacks using this service

- [Monitoring system stack](https://github.com/wodby/stack-monitoring)

## Service overview

| Property | Manifest configuration |
| --- | --- |
| Service name | `monitoring` |
| Type | Infrastructure service |
| Workloads | `main` (Deployment), primary |
| Containers | `alloy` |
| Helm | chart `grafana/alloy`; version `1.11.0` |
| Configuration | 1 configuration files |

## Role in Wodby infrastructure

Wodby installs this service through a Kubernetes system stack when it is
required by the cluster provider or selected infrastructure configuration. It
runs as a cluster-owned system app and is not offered as a user-deployable
application service.

## Platform maintenance

Changes to this repository can affect cluster provisioning, upgrades,
networking, or observability. Coordinate manifest and Helm changes with every
dependent system stack and preserve service, workload, endpoint, config, and
volume identifiers.

Wodby platform maintainers can validate the manifests with:

```bash
wodby service validate-manifest service.yml --org <org-id>
```

See the [service manifest reference](https://wodby.com/docs/2.0/services/template/) and the [managed services index](https://github.com/wodby/services).
