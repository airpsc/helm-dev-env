* Launch with
```
helm install --name=test dev-env --set ssh.authorized_key=$(cat ~/.ssh/id_rsa.pub)
```
* SSH and its friends are your friends
```
alias test-ssh='ssh -A root@$(minikube service --format "{{.IP}}" test-dev-env) -p $(minikube service --format "{{.Port}}" test-dev-env)'
alias test-sftp='sftp -P $(minikube service --format "{{.Port}}" test-dev-env) root@$(minikube service --format "{{.IP}}" test-dev-env)'
```
