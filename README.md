High level getting started
http://heidloff.net/article/kubernetes-helm-ibm-cloud

Helm as package manager
https://github.com/kubernetes/helm

helm install --name my-jenkins -f jenkins-helm-config.yaml stable/jenkins
helm delete --purge my-jenkins

How volumes working
https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/


Workarounds due to bluemix free account issues:
- No persistent volues supported out of the box see -> https://console.bluemix.net/docs/containers/cs_planning.html#cs_planning_apps_storage
- Using disk space on worker nodes via "hostPath" on persisten volume
- create a persistent volume claim to gain access to 



Access jenkins in the cluster:
https://console.bluemix.net/docs/containers/cs_apps.html#cs_apps_public_nodeport
Figure out public IP:
bx cs workers mycluster

get internal port
kubectl describe service my-jenkins-jenkins

access via <external cluster worker ip>:NodePort


