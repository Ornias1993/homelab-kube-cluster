# Dan Manners' Homelab

Current status: **BETA** (but is highly stable)

This project aims to utilize industry-standard tooling and practices in order to both perform it's functions and act as a repository for people to reference for their own learning and work.

## 🔍 Features

- [x] Easy to replicate GitOps
- [x] Modularity; make it easy to add/remove components
- [x] Hybrid Multi-Cloud
- [x] External DNS updates
- [x] Automagic cert management
- [x] In-Cluster Container Registry
- [ ] Monitoring and alerting 🚧
- [ ] Multiple environment support 🚧
- [ ] Automated Backups 🚧
- [x] ~~Cluster SSO through GitHub~~ - Removed when switching from K3s to Talos

## 💡 Current Tech Stack

| Name                                                            | Description                                                       |
|-----------------------------------------------------------------|-------------------------------------------------------------------|
| [ArgoCD](https://argoproj.github.io/cd/)                        | GitOps for Kubernetes                                             |
| [AWS](https://aws.amazon.com/)                                  | Cloud Provider                                                    |
| [Buildah](https://github.com/containers/buildah/)               | Container Building                                                |
| [Cert-Manager](https://cert-manager.io/docs/)                   | Certificate Manager                                               |
| [Cilium](https://cilium.io/)                                    | CNI utilizing eBPF for Observability and Security                 |
| [Dex](https://dexidp.io/)                                       | Federated OIDC                                                    |
| [External-DNS](https://github.com/kubernetes-sigs/external-dns) | Configure and manage External DNS servers                         |
| [GitHub](https://github.com/)                                   | Popular Code Management through Git                               |
| [Grafana](https://grafana.com/)                                 | Metrics Visualization                                             |
| [Harbor](https://goharbor.io/)                                  | Open Source Container and Helm Registry                           |
| [Helm](https://helm.sh/)                                        | Kubernetes Package Management                                     |
| [Jenkins](https://www.jenkins.io/)                              | Open-Source Automation Server                                     |
| [Kubernetes](https://kubernetes.io/)                            | Container Orchestration                                           |
| [Let's Encrypt](https://letsencrypt.org/)                       | Free TLS certificates                                             |
| [MetalLB](https://metallb.universe.tf/)                         | Kubernetes bare-metal Load Balancer                               |
| [Microsoft Azure](https://azure.microsoft.com/en-us/)           | Cloud Provider                                                    |
| [Mozilla SOPS](https://github.com/mozilla/sops)                 | Simple/Flexible Tool                                              |
| [NGINX](https://www.nginx.com/)                                 | Open-Source Web Server and Reverse Proxy                          |
| [Podman](https://github.com/containers/podman/)                 | Container and Pod management                                      |
| [Prometheus](https://prometheus.io/)                            | Metrics and Data Collection                                       |
| [Proxmox](https://www.proxmox.com/en/proxmox-ve)                | Virtualization Platform                                           |
| [Python](https://www.python.org/)                               | Python Programming Language                                       |
| [QEMU Guest Agent](https://wiki.qemu.org/Features/GuestAgent)   | Provides access to a system-level agent via standard QMP commands |
| [QNAP](https://www.qnap.com/en-us)                              | Storage Array Hardware and Networking                             |
| [Raspberry Pi](https://www.raspberrypi.org/)                    | Baremetal ARM SoC Hardware!                                       |
| [SonarQube](https://www.sonarqube.org/)                         | Static code analysis                                              |
| [Talos](https://talos.dev/)                                     | Secure, immutable, and minimal Linux OS                           |
| [Tekton](https://tekton.dev/)                                   | Cloud-Native CI/CD                                                |
| [Terraform](https://www.terraform.io/)                          | Open-Source Infrastructure-as-Code                                |
| [Terragrunt](https://terragrunt.gruntwork.io/)                  | Making Terraform DRY                                              |
| [Turing Pi 2](https://turingpi.com/)                            | Raspberry Pi Compute Module Clustering                            |
| [Ubuntu](https://ubuntu.com/)                                   | Operating System                                                  |
| [Uptime Kuma](https://github.com/louislam/uptime-kuma)          | Fancy self-hosted system monitoring                               |
| [WikiJS](https://js.wiki/)                                      | Open-Source Wiki/Documentation Service                            |

### Removed Tech Stack

Several items have previously been in my cluster, but have been removed over time for one reason or another. Those items can be foud below.

| Name                                                     | Removal Reason                                                     | Description                                                 |
|----------------------------------------------------------|--------------------------------------------------------------------|-------------------------------------------------------------|
| [Ansible](https://www.ansible.com/)                      | I don't need host provisioning anymore                             | Ad-hoc system configuration-as-code                         |
| [Amazon Linux 2](https://aws.amazon.com/amazon-linux-2/) | I standardized on Talos OS                                         | Operating System                                            |
| [Flannel CNI](https://github.com/flannel-io/flannel)     | I migrated to Cilium for my CNI                                    | Network Fabric for Containers                               |
| [K3s](https://k3s.io/)                                   | I moved to Talos for Kubernetes                                    | Lightweight Kubernetes                                      |
| [KubeLogin](https://github.com/int128/kubelogin)         | This was more of a hassle than anything, but worked perfectly well | kubectl plugin for Kubernetes OpenID Connect authentication |
| [Rocky Linux](https://rockylinux.org/)                   | I standardized on Talos OS                                         | Open-Source Enterprise Linux; Spiritual successor to CentOS |
| [Turing Pi 1](https://turingpi.com/v1/)                  | I can't run Talos OS on the Turing Pi CM3+ nodes                   | Raspberry Pi Compute Module Clustering                      |

## Services Hosted

| Name                      | Description                                                                             | Path                                                                                                                                                          | Relevant Link                                                                                                                           |
|---------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Excalidraw                | Easy whiteboarding with excellent shortcuts!                                            | [manifests/workloads/excalidraw](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/excalidraw)                                 | [GitHub - excalidraw/excalidraw](https://github.com/excalidraw/excalidraw)                                                              |
| Jenkins OSS               | An older tool sir, but it checks out.                                                   | [manifests/workloads/jenkins-oss](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/jenkins-oss)                               | [Website](https://www.jenkins.io/)                                                                                                      |
| Kube-Prometheus-Stack     | Easy to deploy Grafana, Prometheus rules, and the Prometheus Operator.                  | [manifests/workloads/kube-prometheus-stack-grafana](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/kube-prom-stack-grafana) | [GitHub - prometheus-community/helm-charts](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack) |
| Luzifer - One Time Secret | One-Time-Secret sharing platform with a symmetric 256bit AES encryption in the browser. | [manifests/workloads/luzifer-ots](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/luzifer-ots)                               | [GitHub - Luzifer/ots](https://github.com/Luzifer/ots)                                                                                  |
| Memegen                   | The free and open source API to generate memes.                                         | [manifests/workloads/memegen](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/memegen)                                       | [GitHub - jacebrowning/memegen](https://github.com/jacebrowning/memegen)                                                                |
| Node-Feature-Discovery    | Node feature discovery for Kubernetes                                                   | [manifests/workloads/node-feature-discovery](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/node-feature-discovery)         | [GitHub - kubernetes-sigs/node-feature-discovery](https://github.com/kubernetes-sigs/node-feature-discovery)                            |
| Non-Disclosure-Agreement  | Flask app to obfuscate URL's and strings for obfuscated sharing of information.         | [manifests/workloads/non-disclosure-agreement](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/non-disclosure-agreement)     | [GitHub - danmaners/non-disclosure-agreement](https://github.com/danmanners/non-disclosure-agreement)                                   |
| Open Policy Agent         | Policy-based control for cloud native environments                                      | [manifests/workloads/open-policy-agent](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/open-policy-agent)                   | [Website](https://www.openpolicyagent.org/)                                                                                             |
| OpenFaaS                  | Serverless functions, made simple!                                                      | [manifests/workloads/openfaas-ingress](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/openfaas-ingress)                     | [Website](https://www.openfaas.com/)                                                                                                    |
| SonarQube OSS             | Code quality and code security                                                          | [manifests/workloads/sonarqube-oss](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/sonarqube-oss)                           | [Website](https://www.sonarqube.org/)                                                                                                   |
| Spiderfoot                | Automated OSINT webcrawling                                                             | [manifests/workloads/spiderfoot](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/spiderfoot)                                 | [Website](https://www.spiderfoot.net/)                                                                                                  |
| Traefik                   | Cloud native application proxying; simplifying network complexity                       | [manifests/bootstrapping/traefik](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/traefik-helm)                              | [Website](https://traefik.io/traefik/)                                                                                                  |

## Deprecated Services

The services listed below once existed in the cluster, but have since been removed for one reason or another

| Name                       | Deprecation Reason                                  | Description                          | Path                                                                                                                                                  | Relevant Link                                                                                      |
|----------------------------|-----------------------------------------------------|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| Rancher Upgrade Controller | Removed from the cluster when I moved away from K3s | In ur Kubernetes, upgrading ur nodes | [manifests/workloads/k3s-upgrade-controller](https://github.com/danmanners/homelab-kube-cluster/tree/main/manifests/workloads/k3s-upgrade-controller) | [GitHub - rancher/system-upgrade-controller](https://github.com/rancher/system-upgrade-controller) |

### Proxied Services

| Name        | Description                                                | Link                                              |
|-------------|------------------------------------------------------------|---------------------------------------------------|
| Proxmox     | Compute, network, and storage in a single solution         | [Website](https://www.proxmox.com/en/proxmox-ve)  |
| Uptime Kuma | A fancy self-hosted monitoring tool                        | [GitHub](https://github.com/louislam/uptime-kuma) |
| WikiJS      | The most powerful and extensible open source Wiki software | [Website](https://js.wiki/)                       |

## 🔧 Hardware

Below is a list of the hardware (both physical and virtual) in use on this project

### 🖥 On-Prem Systems

-----

#### Virtualization Hosts

| Count | System Type | CPU Type            | CPU Cores | Memory |
|-------|-------------|---------------------|-----------|--------|
| 1     | Desktop     | Intel Core i7-7700  | 4c8t      | 64GiB  |
| 1     | Desktop     | AMD Ryzen 7 5800X   | 8c16t     | 64GiB  |
| 1     | Desktop     | Intel Celeron J4105 | 4c4t      | 16GiB  |
| 1     | Desktop     | AMD Ryzen 5 3400G   | 4c8t      | 32GiB  |

#### Cluster Boards

| Count | System Type                                                                                                                                         | CPU Type                 | CPU Cores | Memory      |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------|-----------|-------------|
| 1     | [DeskPi Super6C](https://deskpi.com/collections/deskpi-super6c/products/deskpi-super6c-raspberry-pi-cm4-cluster-mini-itx-board-6-rpi-cm4-supported) | 4x Raspberry Pi CM4      | 4c4t      | 4x 8GiB     |
| ~~1~~ | [~~Turing Pi 2~~](https://www.kickstarter.com/projects/turingpi/turing-pi-cluster-board)                                                            | ~~4x Raspberry Pi CM4~~  | ~~4c4t~~  | ~~4x 8GiB~~ |
| ~~1~~ | [~~Turing Pi 1~~](https://turingpi.com/v1/)r                                                                                                        | ~~7x Raspberry Pi CM3+~~ | ~~4c4t~~  | ~~7x 1GiB~~ |
| ~~1~~ | [~~Turing Pi 1~~](https://turingpi.com/v1/)r                                                                                                        | ~~3x Raspberry Pi CM3+~~ | ~~4c4t~~  | ~~3x 1GiB~~ |

#### Additional Compute

| Count | System Type    | CPU Type         | CPU Cores | Memory |
|-------|----------------|------------------|-----------|--------|
| 1     | Raspberry Pi 4 | Raspberry Pi CM4 | 4c4t      | 4GiB   |

#### Storage

| Hardware     | Drive Count             | Memory |
|--------------|-------------------------|--------|
| QNAP TS-332X | 3x M.2, 3x 3.5" 7200RPM | 16GiB  |

#### Networking

| Hardware                    | SFP+ Ports | SFP Ports | 1Gb Eth Ports |
|-----------------------------|------------|-----------|---------------|
| Ubiquiti EdgeSwitch 24 Lite | 0          | 2         | 24            |
| Ubiquiti EdgeSwitch 8 150W  | 0          | 2         | 8             |
| Mikrotik CRS305-1G-4S+      | 4          | 0         | 1 (PoE In)    |

### Cloud Hosted Resources

| Name                   | Provider  | Arch      | Instance Size | CPU       | Memory   |
|------------------------|-----------|-----------|---------------|-----------|----------|
| tpi-k3s-aws-edge       | AWS       | arm64     | t4g.small     | 2vCPU     | 2GiB     |
| ~~tpi-k3s-aws-edge~~   | ~~AWS~~   | ~~amd64~~ | t3.medium     | ~~2vCPU~~ | ~~4GiB~~ |
| ~~tpi-k3s-azure-edge~~ | ~~Azure~~ | ~~amd64~~ | Standard B2s  | ~~2vCPU~~ | ~~4GiB~~ |

## Deployment Order of Operations

While this section is _very much_ a Work-in-Progress, I'd like to provide some relevant information on core services that must be deployed and in which order.

### Quick Start

1. [Talos Linux](talos/)

To bootstrap Talos Linux node 1:

- Load the ISO
- Note the IP address
- Decrypt sops certificate: ``
- Decrypt certificate and talos files: `sops -d --in-place sops.asc && cd talos && sops -d --in-place talosconfig && find -name "*.yaml" | xargs -I % sh -c 'sops -d --in-place %' && cd -`
- Provision Talos Master-01: `talosctl apply-config --insecure --nodes ${IPADDRESS} --file talos/master-01.yaml`
- Load TalosConfig: `mkdir -p ~/.talos && cp talosconfig ~/.talos/config`
- Update the endpoint: `talosctl config endpoint 192.168.10.211`
- Bootstrap Talos Master-01 after 60 seconds: `talosctl bootstrap -n 192.168.10.211`
- (optional) load the config again: `talosctl apply-config  --nodes 192.168.10.211 --file talos/master-01.yaml`
- Update the endpoint: `talosctl config endpoint pantheon.schouten-lebbing.nl`
- Load KubeConfig: talosctl kubeconfig --nodes pantheon.schouten-lebbing.nl ~/.kube/config
- (optional)Provision other Master-02: `talosctl apply-config --insecure --nodes ${IPADDRESS} --file talos/master-02.yaml`
- (optional)Provision other Master-03: `talosctl apply-config --insecure --nodes ${IPADDRESS} --file talos/master-03.yaml`
- (optional)Remove master no-exec taints: `kubectl taint nodes $(kubectl get nodes --selector=node-role.kubernetes.io/master | awk 'FNR==2{print $1}') node-role.kubernetes.io/master:NoSchedule-`
- Load sops secret: `kubectl create secret generic sops-gpg --namespace=argocd --from-file=sops.asc`
- bootstrap argocd: `cd manifests/argocd && kustomize build --enable-alpha-plugins | kubectl apply -f - || true && cd -`
- Wait a few minuts
- Load all other argocd applications: `cd manifests && kustomize build --enable-alpha-plugins | kubectl apply -f - || true && cd -`
- reencrypt the used content: `sops -e --in-place sops.asc && cd talos && sops -e --in-place talosconfig && find -name "*.yaml" | xargs -I % sh -c 'sops -e --in-place %' && cd -`

## Identifying Problems, Troubleshooting Steps, and more

Below are a few things that may be beneficial to you when troubleshooting or getting things up and operational

### Traffic is not getting from the edge (cloud) nodes to the on-prem cluster networking

You can validate that your remote traffic is or isn't making it on site by using `dig` inside of the [netshoot container]()

```bash
kubectl run temp-troubleshooting \
  --rm -it -n default \
  --overrides='{"apiVersion":"v1","spec":{"nodeSelector":{"kubernetes.io/hostname":"talos-aws-grav01"}}}' \
  --pod-running-timeout 3m \
  --image=docker.io/nicolaka/netshoot:latest \
  --command -- /bin/bash
```

Then, you can validate that you can reach CoreDNS or another pod/service IP from your remote node.

If you can prove it is not working, you may want to restart all of Cilium:

```bash
kubectl rollout restart -n kube-system daemonset cilium
```

## To-Do Items

- Ensure that **ALL** services are tagged for the appropriate hardware (`arm64` or `amd64`) to ensure runtime success
  - Alternatively, ensure that all containers are built for multi-architecture.
- Ensure that **ALL** application and service subdirectories have READMEs explaining what they're doing and what someone else may need to modify for their own environment

## Gratitude and Thanks

This README redesign was inspired by several other homelab repos, individuals, and communities.

### Individuals

-----

- [zimmertr/TKS](https://github.com/zimmertr/TKS)
- [onedr0p/home-ops](https://github.com/onedr0p/home-ops/)
- [khuedoan/homelab](https://github.com/khuedoan/homelab)

### Communities

-----

#### The DevOps Lounge

[![Discord](https://img.shields.io/discord/611083841792376843?style=for-the-badge&label=discord&logo=discord&logoColor=white)](https://discord.gg/devopslounge)

#### K8s-at-Home

[![Discord](https://img.shields.io/discord/673534664354430999?style=for-the-badge&label=discord&logo=discord&logoColor=white)](https://discord.gg/k8s-at-home)

Without the inspiration and help of these individuals and communities, I don't think my own project would be nearly as far. Make sure to check out their projects as well!
