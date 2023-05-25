# Ingester -- Deployment at Alba

## Container image

For running the ActiveMQ broker in Kubernetes we are using [ArtemisCloud.io](https://artemiscloud.io/). This cloud oriented ActiveMQ version provides an specific operator for orchestrating the brokers.
In terms of scalling, its better for running ReplicatSets on the brokers and makes sure that there are no data inconsistencies.

WIP


### Ingress routing

WIP

## Replication and scalling strategies

We are not running yet this configuration in production, so scaling stats TBD.
