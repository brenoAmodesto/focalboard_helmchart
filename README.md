# Focalboard Helm Chart

This Helm chart installs [Focalboard](https://www.focalboard.com/), an open source Trello alternative for project management and collaboration.

## Usage

1. **Add the chart repository (if applicable)**
2. **Install the chart:**
   ```sh
   helm install my-focalboard ./focalboard
   ```

## Configuration

Chart values are parsed from the [`values.yaml`](focalboard/values.yaml) file. You can override any value using the `--set` flag or by providing your own custom values file.

Example customization:
```sh
helm install my-focalboard ./focalboard \
  --set service.type=LoadBalancer \
  --set ingress.hosts[0].host=mydomain.com
```

Main configurable values:

- **image.repository**: Focalboard Docker image.
- **image.tag**: Image version.
- **service.type**: Kubernetes service type (ClusterIP, NodePort, LoadBalancer).
- **service.port**: Service port.
- **ingress.enabled**: Enable or disable Ingress.
- **ingress.hosts**: List of hosts for Ingress.
- **persistence.enabled**: Enable data persistence.
- **persistence.storageClass**: Storage class.
- **persistence.size**: Persistent volume size.

See all possible values in [`values.yaml`](focalboard/values.yaml).

## Structure

- [`templates/`](focalboard/templates/): Kubernetes manifests for deployment, service, ingress, and PVC.
- [`values.yaml`](focalboard/values.yaml): Default chart values.

## Requirements

- Kubernetes 1.19+
- Helm 3.x

## License

MIT