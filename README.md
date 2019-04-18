# kubernetes

## kubeadm installation - master-node setup (ubuntu 16.04)

### kubeadm and docker installation required in both master and nodes

`sh ./kubeadmin.sh username(ubuntu)`


## on master

`kubeadm init`

To start using your cluster, you need to run the following as a regular user:

   `mkdir -p $HOME/.kube`
   
   `sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config`
   
   `sudo chown $(id -u):$(id -g) $HOME/.kube/config`

## for weave-net pod network 

`kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"`

## Adding nodes to kubernetes master
## on nodes
apply the join command in all the nodes,which is like `kubeadm join --token <token> <master-ip>:<master-port> --discovery-token-ca-cert-hash sha256:<hash>` resulted after kubeadm init in master


  

 recommended docs -  `https://kubernetes.io/docs/setup/independent/install-kubeadm/`

`https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/`
