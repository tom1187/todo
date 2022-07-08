# todo
DevopsExpert - helm exercise
Helm init:
curl -L https://git.io/get_helm.sh | bash
helm init  # setup helm with our cluster
helm repo update # sync all helm charts info

Helm creation:
helm create todochart

Helm deployment:
helm install todochart

Helm museaum:
helm package .
curl https://raw.githubusercontent.com/helm/chartmuseum/main/scripts/get-chartmuseum | bash
chartmuseum --debug --port=8080 --storage="local" --storage-local-rootdir="./chartstorage"
curl --data-binary "@todochart-0.1.0.tgz" http://localhost:8080/api/charts

k port-forward  service/jazzed-wildebeest-todochart 31787:80
