# configuration-as-code
oc create configmap oc-casc --from-file=oc/bundle.yaml --from-file=oc/items.yaml --from-file=oc/jenkins.yaml --from-file=oc/plugins.yaml

helm install cloudbees-ci cloudbees/cloudbees-core  --set OperationsCenter.HostName='oc.apps.ocp4.smartek.ae' --set OperationsCenter.Route.tls.Enable=true --values values.yaml
