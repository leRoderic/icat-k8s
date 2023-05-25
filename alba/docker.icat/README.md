# docker.icat -- Deployment at Alba

## Container image

We are using RKrahl's [docker.icat](https://github.com/RKrahl/docker.icat) and [docker.glassfish](https://github.com/RKrahl/docker.glassfish) images. We have forked it and slightly modified for two reasons:
- Running Filebeat (log forwarding to Logstash -- Elastic Search) and Payara at the same time using supervisord.
- Changing the UID of the user that runs the container (for mounting NFS storage).

## Ingress and ICAT Manager

Due to some restrictions (mainly due to ICAT Manager being a bit outdated) we've had to deploy the Ingress that makes the Payara server available outside the cluster in both HTTP and HTTPS.
The HTTP endpoint is only used for returning the XSD document at the beginning of the server connection. Reason behind this is that Java 7 does not natively follow redirects to urls with different protocols (that is HTTP-> HTTPS).

### Ingress routing

We like to deploy each component as if it was in a reverse proxy, and for this reason the ingress performs the following routing for each of the components:
- /icat_server -> ICAT server
- /ids -> IDS server

## Replication and scalling strategies

We are not running yet this configuration in production, so scaling stats TBD.
