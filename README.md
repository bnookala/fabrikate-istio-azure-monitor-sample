# Fabrikate Istio Azure Monitor Sample

A [Fabrikate](github.com/microsoft/fabrikate) component to install a mixer component for [Azure Monitor services](https://github.com/Microsoft/Application-Insights-Istio-Adapter), the Istio Service Mesh, and the Bookinfo sample application.

## Configuration

The default configuration is as follows:

```yaml
config:
subcomponents:
  istio-azure-monitor:
    config:
      instrumentation:
        logLevel: Trace
        applicationInsightsKey: "my-application-insights-key"
        watchingNamespaces: "default,bookinfo,istio-system,kube-system"
```

Where `applicationInsightsKey` must be replaced with an instrumentation key issued from an Azure Application Insights instance.

## Installation

Download the appropriate [Fabrikate](github.com/microsoft/fabrikate/releases) release for your OS, then invoke the following commands:

```
$ fab install
$ fab generate prod
$ kubectl apply -f --recursive ./generated/prod/
```

## License

MIT - See [LICENSE](./LICENSE) file.
