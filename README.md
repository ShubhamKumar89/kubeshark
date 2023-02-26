# kubeshark

kubeshark is a Kubernetes packet sniffer and network analyzer that allows you to inspect network traffic between Kubernetes resources.[Official Page](https://docs.kubeshark.co/en/install)

## Install

### Method 1

Choose manually the right binary to download directly from the [latest release](https://github.com/kubeshark/kubeshark/releases/tag/38.5)

### Method 2

Alternatively you can use a shell script to download the right binary for your operating system and CPU architecture:

```
sh <(curl -Ls https://kubeshark.co/install)
```

## Run

1. By default kubeshark is deployed into the `default` namespace. To start capturing taffic in all namespaces:

```
kubeshark tap -A
```

2. To capture traffic in different namespace:

```
kubeshark tap -n <namespace>
```

> Note: Once you run the CLI, a browser window will open at `localhost:8899` by default.

##### To use it in a **remote server**, you can run the kubeshark command with `--proxy-host 0.0.0.0` flag. [Requirements for AWS like Platforms](https://docs.kubeshark.co/en/config#web-ui--ip-and-accessibility)

```
kubeshark tap -A --tls --proxy-host 0.0.0.0
```

The `--tls` flag specifies that TLS encryption should be used for the tap. This ensures that the captured network traffic is secure and cannot be intercepted or tampered with.

