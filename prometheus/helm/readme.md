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

# 2. 安装时增加自定义配置

如提供 [custom-values.yaml](custom-values.yaml) 这样的自定义 values 文件，则可以用如下方式进行自定义配置：

```shell
helm install -n metrics prom-stack ./kube-prometheus-stack -f custom-values.yaml
```

用这种方法，可以为 Prometheus 修改数据持久化卷


# 其他

使用该命令查看 `metrics` 空间下安装的 chart
```shell
helm -n metrics list
```