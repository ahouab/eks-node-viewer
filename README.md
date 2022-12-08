[![GitHub License](https://img.shields.io/badge/License-Apache%202.0-ff69b4.svg)](https://github.com/awslabs/eks-node-viewer/blob/main/LICENSE)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/aws/karpenter/issues)

## Usage

`eks-node-viewer` is a tool for visualizing dynamic node usage within a cluster.  It was originally developed as an internal tool at AWS for demonstrating consolidation with [Karpenter](https://karpenter.sh/).  

![](./.static/screenshot.png)

### Talks Using eks-node-viewer

- [Containers from the Couch: Workload Consolidation with Karpenter](https://www.youtube.com/watch?v=BnksdJ3oOEs)
- [AWS re:Invent 2022 - Kubernetes virtually anywhere, for everyon](https://www.youtube.com/watch?v=OB7IZolZk78)

### Installation
```shell
go install github.com/awslabs/eks-node-viewer/cmd/eks-node-viewer@latest
```
### Standard Usage
```shell
eks-node-viewer
```

### Karpenter Nodes Only
```shell
eks-node-viewer --nodeSelector "karpenter.sh/provisioner-name"
```

### Display CPU and Memory Usage
```shell
eks-node-viewer --resources cpu,memory
```
### Troubleshooting

#### NoCredentialProviders: no valid providers in chain. Deprecated.

This CLI relies on AWS credentials to access pricing data. You must have credentials configured via `~/aws/credentials`, `~/.aws/config`, environment variables, or some other credential provider chain.

See [credential provider documentation](https://docs.aws.amazon.com/sdk-for-go/api/aws/session/) for more.

## Development

### Building
```shell
$ make build
```
