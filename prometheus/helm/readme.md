# Helm Prometheus 安装和使用

# 1. 安装

把 Prometheus Community 的 Prometheus chart 下载到本地，修改镜像地址或版本，以便安装。

注意，这里我们使用 `kube-prometheus-stack`，它包含了 Grafana 等组件，适合生产环境使用

```shell
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

helm pull prometheus-community/kube-prometheus-stack --untar
```

修改镜像或版本后，安装kube-prometheus-stack

```shell
helm install -n metrics prom-stack ./kube-prometheus-stack
```

使用该命令查看 `metrics` 空间下安装的 chart
```shell
helm -n metrics list
```