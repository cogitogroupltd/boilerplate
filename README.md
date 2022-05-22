# Environment agnostic Kubernetes Helm charts

Colelction of DevOps tooling to help businesses scale with minimal overheads. 

Source repository https://github.com/cogitogroupltd/boilerplate

Contents: 

- `common` Kubernetes Generic Helm Chart - for all of your organisation's applications

- `ingress-nginx` Kubernetes Nginx ingress controller using pure Nginx for use with all your environments, local, on-premise and/or cloud


## Ingress-nginx 

Features:
- Uses pure native Nginx configuration 
- WebSocket, SSL and TCP streaming backend support
- Healthcheck endpoint for Kubernetes lifecycle management
- Custom [40x.html](charts/ingress-nginx/templates/configmap-conf.yaml) and [50x](charts/ingress-nginx/templates/configmap-conf.yaml) error pages 
- Basic username/password authentication for each proxied application
- IP Whitelisting for each proxied application
- Zero-downtime upgrades using prestop hook `SIGQUIT` signal
- Cloud agnostic deployment exposing `HostPort` or `NodePort`

Successfully tested on:
 - AWS EKS using NLB and ALB
 - Kind [download](https://kind.sigs.k8s.io/)
 - Rancher K3s 
 - Google Kubernetes Engine (GKE)

Examples:

- [ingress-nginx-hostport]](./examples/ingress-nginx-hostport/README.md) using HostPort 80/443
- [ingress-nginx-ssl-selfsigned](./examples/ingress-nginx-ssl-selfsigned/README.md) using SSL certificates and NodePort 30080/300443
- [ingress-nginx-tcp](./examples/ingress-nginx-tcp/README.md) using mysql TCP backend
- [ingress-nginx-tcp](./examples/ingress-nginx-whitelisting/README.md) using AWS NLB and IP whitelisting


## Common


Examples:

- SSH bastion host running on K8s
    [README.md](./examples/sshd/README.md) for more information
- Autoscaling backend service
    [README.md](./examples/backend-autoscaling/README.md) for more information
- Simple NodeJS express server with rawYaml injection
    [README.md](./examples/node-express/README.md) for more information
- ZeroTier connected K8s pods
    TBC
- Orleans ready containers
    [README.md](./examples/orleans/README.md) for more information
- Nexus Docker registry
    TBC
- Tekton environment agnostic pipelines
    TBC
