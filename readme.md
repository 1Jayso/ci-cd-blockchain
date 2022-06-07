# Ejara Test Submission
<!-- # DigitalOcean Kubernetes Challenge  -->


- Applications were successfully deployed follwing the instructions given. I used StatefulSet instead of Deployment due to the fact that blockchain nodes are stateful applications and StatefulSet is best suited for that.
- Github actions was used as the CI server and ArgoCd for the continous delivery and deployment. I interfaced the nodes with Kong's API gateway. The ci runs every midnight to pull changes and merged them into my master branch. It then builds and pushes the image to my docker registry on dockerhub. ArgoCD uses gitops to listen for changes in my git repository and reconcile them automatically or manually base on the reconciliation strategy set for the ArgoCD applications. 
- To access the bitcoin, ethereum, and tezos rpc servers you would need to use the gateway's IP and each nodes endpoint respectively as follows: ["35.184.26.103/bitcoin", "35.184.26.103/ethereum", "35.184.26.103/tezos"]


- The ArgoCD dashboard can be accessed via this IP address 35.193.103.196 
- The dasboard credentials are as follows {username:"admin"}, {password:"sudo12345"}. This will help you visualize the cluster and health statuses of the nodes.
- Below is an image of the nodes from the argocd dashboard.
![Nodes in ArgoCd dashboard](images/btc-eth-tezos.png)

## Links to Repos
- https://github.com/1Jayso/bitcoin
- https://github.com/1Jayso/go-ethereum
