# Argo CD Manifest Repository for Weather Forecast CLI

## This repository is being updated via a GitHub Actions workflow in [this](https://github.com/ngnrng/NWS-weather-app-code) repo.

This repository contains Kubernetes manifests for deploying the Weather Forecast CLI application using Argo CD. The application fetches and prints current weather data for a list of cities using the National Weather Service API.

## Repository Structure

The repository is organized into the following directories and files:

- `cronjob.yaml`: Defines a Kubernetes CronJob that periodically runs the Low Tide application.
- `namespace.yaml`: Specifies the Kubernetes namespace where the application will be deployed.

