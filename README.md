# zeebe-gopro-helm
Helm chart to host [zeebe-gopro](https://github.com/livspaceeng/zeebe-gopro) on Kubernetes cluster

### Deployment Steps
- Clone these 2 repo in your home (**~**) directory:
  + [zeebe-gopro helm repo](https://github.com/livspaceeng/zeebe-gopro-helm)
  + [helm-chart repo](https://github.com/livspaceeng/helm-charts)
- Make any required changes to [zeebe-gopro-helm](https://github.com/livspaceeng/zeebe-gopro-helm) repo.
- Update the **appVersion** in [Chart.yaml](./zeebe-gopro/Chart.yaml) to point to the current [zeebe-gopro version](https://github.com/livspaceeng/zeebe-gopro/releases) (*Just to be aware of the current version being used*).
- Upgrade the **version** in [Chart.yaml](./zeebe-gopro/Chart.yaml), and push to this repo.
- Run the below commands from terminal (*inside ~/helm-charts directory*):
  + `> helm package ../zeebe-gopro-helm/zeebe-gopro`
  + `> helm repo index --merge index.yaml --url https://charts.livspace.com .`
  + `> git add .`
  + `> git commit`
  + `> git push origin`
- Use the **version** from [Chart.yaml](./zeebe-gopro/Chart.yaml) and update it in [requirements.yaml](https://bitbucket.org/livspaceeng/environment-jx-dev/src/master/env/requirements.yaml).
