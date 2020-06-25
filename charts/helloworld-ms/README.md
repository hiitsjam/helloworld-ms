# Croc Hunter Helm Chart

Inspired be the groundbreaking game feature at OpenStack Tokyo Summit

## Chart Details
This chart will do the following by default:

* 3 x helloworld-ms instances with port 8080 exposed on an external LoadBalancer
* All using Kubernetes Deployments


## Get this chart

Download the latest release of the chart from the [releases](../../../releases) page.

Alternatively, clone the repo if you wish to use the development snapshot:

```bash
$ git clone https://github.com/hiitsjam/helloworld-ms/charts
```

## Chart signing

The chart is signed using Helm provenance and integrity.
   * https://github.com/kubernetes/helm/blob/master/docs/provenance.md

## Installing the Chart

To install the chart with the release name `my-release`:

```bash
$ helm repo add levo-charts https://storage.googleapis.com/levo-charts
$ helm install --verify levo-charts/helloworld-ms-0.2.0.tgz
```

## Configuration

The following tables lists the configurable parameters of the Spark chart and their default values.

### helloworld-ms

|       Parameter       |           Description            |                         Default                          |
|-----------------------|----------------------------------|----------------------------------------------------------|
| `Name`            | app name                         | `helloworld-ms`                                                |
| `Image`           | Container image name             | `quay.io/lachie83/helloworld-ms`                               |
| `ImageTag`        | Container image tag              | `latest`                                                     |
| `ImagePullPolicy` | Container pull policy            | `Always`                                                     |
| `Replicas`        | k8s deployment replicas          | `3`                                                          |
| `Component`       | k8s selector key                 | `helloworld-ms`                                                |
| `Cpu`             | container requested cpu          | `10m`                                                        |
| `Memory`          | container requested memory       | `128Mi`                                                      |
| `ServiceType`     | k8s service type                 | `LoadBalancer`                                               |
| `ServicePort`     | k8s service port                 | `80`                                                         |
| `ContainerPort`   | Container listening port         | `8080`                                                       |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart. For example,

```bash
$ helm install --name my-release -f values.yaml --verify levo-charts/helloworld-ms-0.2.0.tgz
```

> **Tip**: You can use the default [values.yaml](values.yaml)
