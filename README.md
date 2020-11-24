# Kops GCE Installer

## Why Kops on GCE? Don't you like GKE?

I **love** GKE. But sometimes need to demo hybrid Kubernetes management with Anthos. And for that I need something that is **not** GKE and is as *(day 0)|(day 1)|(day 2) operations full* as possible but at the same time can be deployed in a convenient GCE environment with no licensing costs.

## What you'll need 

- A GCP project, with billing enabled.
- Project editor or owner permissions.
- An Internet connection.
- Access to a terminal in a machine with Google Cloud SDK installed or Cloud Shell.

## Installing a cluster

Make sure the project you want to deploy the cluster to is active. If so, to install Kops run:

```bash
./kops-gce install
```

The cluster will be named "onprem". If you want a different name, use the `--cluster-name` option.

The installer will ask you to get Application Default Credentials. If you already have them, you can skip this step. by passing the flag `--skip-credentials`:
```bash
./kops-gce install --skip credentials
```

The installation process will create a `workdir` subdirectory to install the `kops` tools and save some additional files.

## Deleting a cluster

To destroy the cluster and reset additional configurations, just do:
```bash
./kops-gce destroy
```

## Additional help

Run `./kops --help`.