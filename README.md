# Letout.IO Helm Charts
A helm repository that has a variety of helm charts for helping people to deploy stack inside Kubernetes cluster with best and security practices. 
One of the main motives of creating these charts is that person can easily deploy the stack or application inside the Kubernetes cluster without getting into the complexity.

[Helm](https://helm.sh/) must be installed to use the charts. Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```shell
helm repo add letout-io https://letout-io.github.io/charts/  
```

You can then run `helm search repo letout-io` to see the charts.

### Helm Charts List

Currently supported helm charts are:-

- [Laravel Helm Chart](./charts/laravel)

### Pre-Requisities

- Kubernetes `>=1.15.X`
- Helm `>=3.0.X`

### Installing Helm

Helm is a tool for managing Kubernetes charts. Charts are packages of pre-configured Kubernetes resources.

To install Helm, refer to the [Helm install guide](https://github.com/helm/helm#install) and ensure that the helm binary is in the PATH of your shell.

### Adding Repo

```shell
helm repo add letout-io https://letout-io.github.io/charts/  
```

Please refer to the [Quick Start guide](https://helm.sh/docs/intro/quickstart/) if you wish to get running in just a few commands, otherwise the [Using Helm Guide](https://helm.sh/docs/intro/using_helm/) provides detailed instructions on how to use the Helm client to manage packages on your Kubernetes cluster.

Useful Helm Client Commands:

- View available charts: `helm search repo`
- Install a chart: `helm install my-release letout-io/<package-name>`
- Upgrade your application: `helm upgrade`

# License
Copyright (c) 2015-2021 Letout.IO

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
