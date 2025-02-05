# Installation

- [Mac OSX](#mac)
- [Linux](#linux)
- [Windows](#windows)
- [Docker](#docker)

<em>NOTE:</em> `kconnect` requires [kubectl >= 1.17.0](https://kubernetes.io/docs/tasks/tools/install-kubectl)

<em>NOTE:</em> `kconnect` requires [aws-iam-authenticator >= 0.5.5](https://github.com/kubernetes-sigs/aws-iam-authenticator) to authenticate to the AWS EKS cluster provider.

<em>NOTE:</em> `kconnect` requires [kubelogin](https://github.com/Azure/kubelogin) to authenticate to Azure AKS clusters.


## kubectl plugin

To install as a kubectl plugin:

```bash
kubectl krew index add fidelity https://github.com/fidelity/krew-index.git
kubectl krew install fidelity/connect
```

You can then run like so:
```bash
kubectl connect use eks
```

## Mac

To install on OSX you can use homebrew:

```bash
brew install fidelity/tap/kconnect
```

Alternatively you can download a binary from the latest [release](https://github.com/fidelity/kconnect/releases).

## Linux

To install on Linux you can use homebrew:

```bash
brew install fidelity/tap/kconnect
```

Alternatively, the latest [release](https://github.com/fidelity/kconnect/releases) contains **.deb**, **.rpm** and binaries for Linux.

We are working on publishing as a snap.

## Windows

The latest [release](https://github.com/fidelity/kconnect/releases) contains a binary for Windows.

We have an open issue to support chocolatey in the future/

## Docker

You can also use kconnect via Docker by using the images we publish to Docker Hub:

```bash
docker pull docker.io/kconnectcli/kconnect:latest
docker run -it --rm -v ~/.kconnect:/.kconnect kconnect:latest use eks --idp-protocol saml
```
## Install script

You can install kconnect, along with kubectl, helm and aws-iam-authenticator by running:

```bash
curl -fsSL -o install-kconnect.sh https://raw.githubusercontent.com/fidelity/kconnect/main/scripts/install-kconnect.sh
chmod 700 install-kconnect.sh
./install-kconnect.sh
```

This works on Linux, Macos and Windows (using GitBash terminal)
