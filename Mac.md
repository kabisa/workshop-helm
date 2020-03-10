
## Homebrew

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```


## Kubectl

```bash
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl"
chmod +x kubectl
mv kubectl /usr/local/bin/
```

## Rest

```bash
brew install minikube
brew install helm
```


## Autocompletion

https://kubernetes.io/docs/tasks/tools/install-kubectl/#optional-kubectl-configurations