* Launch with
```
helm install --test dev-env --set ssh.authorized_key=$(cat ~/.ssh/id_rsa.pub)
```
* SSH is your friend
```
ssh -A root@$(minikube service --format "{{.IP}}" test-dev-env) -p $(minikube service --format "{{.Port}}" test-dev-env)
```
