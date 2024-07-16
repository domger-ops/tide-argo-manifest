# Argo CD Manifest Repository for Tide and Temp API CLI

## This repository is being updated via a GitHub Actions workflow in [this](https://github.com/domger-ops/tide-app-workflow.git) repo.

This repository contains Kubernetes manifests for deploying the Tide and Temp API CLI application using Argo CD.

## Repository Structure

The repository is organized into the following files:

- `cronjob.yaml`: Defines a Kubernetes CronJob named `tide-app-cron` that schedules a job to run at 7:15 AM UTC (which is 12:15 AM PST, accounting for the typical 7-hour difference) daily. This job utilizes a Docker image, the tag for which is provided by a GitHub Actions workflow. It is configured to restart on failure and uses Docker secrets for pulling the image securely.
- `namespace.yaml`:  Creates a Kubernetes Namespace named `tide-app-ns`, labeled with name: `tide-app`, to isolate resources within a Kubernetes cluster.
- `argo-app.yaml`: This YAML file defines an Argo CD Application named `tide-app`, specifying its source in a Git repository and its deployment target within a Kubernetes cluster. It configures automatic synchronization, including resource pruning and self-healing, to ensure the cluster's state matches the defined state in the repository.