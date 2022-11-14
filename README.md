# KubeSplunk
Setup Splunk trial on Kubenetes Cluster

Steps for bring up trail Splunk service

1, deploy and start svc and pod

- kubectl apply -f splunk-pvc.yaml
- kubectl apply -f splunkmaster-svc.yaml
- kubectl apply -f splunkmaster-deploy.yaml


2, setup kong/elb on for web access from outside of cluster

- kubectl apply -f splunkmaster-svc-kong.yaml
- kubectl splunk.rnctech.com-kong.yaml


3, you may need to enable webserver automatically start with pod restart

- 3.1 exec into pod and su to user splunk, then run cmd as below

- 3.2 cd /opt/splunk/bin

./splunk enable webserver

./splunk restart


4, log on to web ui using admin user configure in splunkmaster-deploy.yaml file
then you can load data and creat index for search


5, next steps may setup db search and add plugins
