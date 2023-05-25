# HDF5 Web Viewer -- Deployment at Alba

## Container image

The same usage the icat-plus repository provides is being used. Only a few things changed code-wise for getting the app fully running in our cluster.


### Ingress routing

We like to deploy each component as if it was in a reverse proxy, and for this reason the ingress performs the following routing for each of the components:
- /icat_plus -> ICAT plus API

## Replication and scalling strategies

We are not running yet this configuration in production, so scaling stats TBD.
