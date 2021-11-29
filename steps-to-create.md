oc new-project nexus

oc create -f https://raw.githubusercontent.com/bbalakriz/nexus/master/nexus3-persistent-template.yaml

oc create secret docker-registry \
   --docker-server=docker.io \
   --docker-username=bbalasub \
   --docker-password=******** \
   dockerhub
   
oc secrets link default dockerhub --for=pull

oc new-app nexus3-persistent
