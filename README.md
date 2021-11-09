Replicated Prometheus Remote Write
==================

This is an example showing how to patch the [Open Source Kubernetes Installer - kURL](https://kurl.sh) Prometheus add-on with a remote-write address via Replicated's Config Screen option.

### Requirements
1. Have a Replicated [Vendor Web](https://vendor.replicated.com) account.

### Deploying
1. Promote a release using the manifests directory in the Replicated Vendor Web.
2. Run the Embedded Cluster one-online install on a supported linux VM. See kURL minimum [system requirements](https://kurl.sh/docs/install-with-kurl/system-requirements) for additional information.
3. Once the kURL Embedded Cluster is running use the App Manager to continue application installation.

### Files Used For Patching
1. `kots-config.yaml` contains the [Config Screen](https://kots.io/vendor/config/config-screen/) example to prompt an end-user to enable Prometheus remote write.
2. `prometheus-patch-configmap.yaml` contains a `ConfigMap` with a `patch.yaml` and `script.sh` file for patching Prometheus.
3. `prometheus-patch-job.yaml` contains the Kubernetes job that will run when enabled based on the Config Screen selection.