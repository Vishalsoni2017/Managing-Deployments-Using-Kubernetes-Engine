kubectl explain deployment
    6  kubectl explain deployment --recursive
    7  kubectl explain deployment.metadata.name
    8  vi deployments/auth.yaml
    9  cat deployments/auth.yaml
   10  kubectl create -f deployments/auth.yaml
   11  kubectl get deployments
   12  kubectl get replicasets
   13  kubectl get pods
   14  kubectl create -f services/auth.yaml
   15  kubectl create -f deployments/hello.yaml
   16  kubectl create -f services/hello.yaml
   17  kubectl create secret generic tls-certs --from-file tls/
   18  kubectl create configmap nginx-frontend-conf --from-file=nginx/frontend.conf
   19  kubectl create -f deployments/frontend.yaml
   20  kubectl create -f services/frontend.yaml
   21  kubectl get services frontend
   22  curl -ks https://34.83.212.86 
   23  curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`
   24  kubectl explain deployment.spec.replicas
   25  kubectl scale deployment hello --replicas=5
   26  kubectl get pods | grep hello- | wc -l
   27  kubectl scale deployment hello --replicas=3
   28  kubectl get pods | grep hello- | wc -l
   29  kubectl edit deployment hello
   30  kubectl get replicaset
   31  kubectl rollout history deployment/hello
   32  kubectl rollout pause deployment/hello
   33  kubectl rollout status deployment/hello
   34  kubectl get pods -o jsonpath --template='{range .items[*]}{.metadata.name}{"\t"}{"\t"}{.spec.containers[0].image}{"\n"}{end}'
   35  kubectl rollout resume deployment/hello
   36  kubectl rollout status deployment/hello
   37  kubectl rollout undo deployment/hello
   38  kubectl rollout history deployment/hello
   39  cat deployments/hello-canary.yaml
   40  kubectl create -f deployments/hello-canary.yaml
   41  kubectl get deployments
   42  curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`/version
   43  kubectl apply -f services/hello-blue.yaml
   44  kubectl create -f deployments/hello-green.yaml
   45  curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`/version
   46  kubectl apply -f services/hello-blue.yaml
   47  curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`/version
   48  history 
