# `Run Lite` cluster group capabilites for Tanzu Platform

# Features

- Reduce foot print of cluster group in Tanzu Platform
- Works with `apps.tanzu.vmware.com` profile

Caution, this capability is removing replicas for istiod and may lead to longer downtime.

# How to

Create a clustergroup named `run-lite` then run the following.
Make sure your in the correct project via `tanzu project use`

```
tanzu operations clustergroup use run-lite

git clone https://github.com/mhoshi-vm/tp-run-lite
cd tp-run-lite/clustergroup
tanzu deploy --only .
```

# Run vs Run-Lite


|                                         | run | run-lite | Notes                                           |
| --------------------------------------- | --- | -------- |----------------------------------------------|
| bitnami.services.tanzu.vmware.com       | ○   |          | Removes bitnami `create service` capabilites |
| cert-manager.tanzu.vmware.com           | ○   | ○        |                                              |
| container-apps.tanzu.vmware.com         | ○   | ○        |                                              |
| controller.build.tanzu.vmware.com       |     | ○        | Not included in default `run` but eases deploy     |
| crossplane.tanzu.vmware.com             | ○   |          | Removes bitnami `create service` capabilites |
| egress.tanzu.vmware.com                 | ○   | ○        |                                              |
| health.spaces.tanzu.vmware.com          | ○   | ○        |                                              |
| horizontal-autoscaling.tanzu.vmware.com | ○   | ○        |                                              |
| ingress.tanzu.vmware.com                | ○   | ○        |                                              |
| k8sgateway.tanzu.vmware.com             | ○   | ○        |                                              |
| mtls.tanzu.vmware.com                   | ○   | ○        |                                              |
| observability.tanzu.vmware.com          | ○   | ○        |                                              |
| servicebinding.tanzu.vmware.com         | ○   | ○        |                                              |
| spring-cloud-gateway.tanzu.vmware.com   | ○   |          | Requires large memory so disabled                  |
| tanzu-servicebinding.tanzu.vmware.com   | ○   | ○        |                                              |
| tcs.tanzu.vmware.com                    | ○   | △        | Change the count of replica of istiod and changed resource request values     |
