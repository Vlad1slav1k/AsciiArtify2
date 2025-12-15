## MVP
1.We fork the application repository from  https://github.com/den-vasyliev/go-demo-app

2. Install K3d 
wget -q -O - https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
 
3. Create a kub cluster  
k3d cluster create argo

4.Create a namespace
kubectl create namespace argocd

5. Do ArgoCD deployment
470  kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

6. Do port forward 
kubectl port-forward svc/argocd-server -n argocd 8080:443&

7. Connect to https://127.0.0.1:8080 and set it up via ArgoCD Web UI
![ArgoCD](https://github.com/user-attachments/assets/d8b9f5dd-764c-4940-92b2-54d1dff862ca)

8.Get the password ( base24 > plain text )

$ k -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}"
                                                                                                      
$ k -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}"|base64 -d;echo


9. In argo CD Web UI do a setup as in Coding Session 
![out of sync](https://github.com/user-attachments/assets/6411498b-3536-46c5-90a8-51d0db46fa63)

Meet few issues here:

1) Pod Ambassador does not start - error "too many opened files"    >>    increased the ulimit on the host
2) Pod with DB does not start due to lack of cpu >> had to increase the cpu limit in the helm/charts/db-sql/templates/deployment.yaml  and add more cpu to the host
![too manu open files](https://github.com/user-attachments/assets/57e2ea61-ccf1-46f9-b403-40cb10ec1d4b)

AutoSync Policy can be enabled here:
![auto sync](https://github.com/user-attachments/assets/65fe3359-247a-4aff-a301-6cad5774382a)


Finally all pods are up and the Application is healthy
![healthy](https://github.com/user-attachments/assets/d23711f3-007c-4384-9125-3d0732ca7164)

10) Tried to change the service port from NodePort to LoadBalancer and sync again
![change the service type](https://github.com/user-attachments/assets/2cec338a-c68d-4562-8a07-146ae17c2038)

my VirtualBox does not have any External Ip, the service will not start,  so I have to change it back and finish 

![final](https://github.com/user-attachments/assets/dd779b00-ceaf-4a31-a436-d4d8fde5cb21)




