# Prometheus 使用

# 抓去 Istio 指标

为了配置Prometheus从Istio收集指标，我们需要使用Prometheus Operator的自定义资源ServiceMonitor和PodMonitor：

使用 `ServiceMonitor` 资源来从Istio控制平面组件抓取指标，见 [service-monitor-cp.yaml](./service-monitor-cp.yaml)
使用 `PodMonitor` 资源，从包含istio-proxy容器的每个Pod中抓取指标，见[pod-monitor-dp.yaml](./pod-monitor-dp.yaml)