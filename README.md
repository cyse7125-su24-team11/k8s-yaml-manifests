# k8s-yaml-manifests


## Steps tp deploy Kubernetes Infrastructure

-   Setup kubernetes secret with docker authentication
    -       kubectl create secret docker-registry regcred --docker-server=[https://index.docker.io/v1/]--docker-username=<your-name> --docker-password=<your-pword> --docker-email=<your-email>
    -       kubectl create secret generic regcred \
    --from-file=.dockerconfigjson=/Users/shabinasingh/.docker/config.json \
    --type=kubernetes.io/dockerconfigjson


-   Deploy Kubernetes infrastructure
    -   kind create cluster
    -   kubectl apply -f pod.yaml
    -   kubectl port-forward pods/caddy-webapp 8080:8080 