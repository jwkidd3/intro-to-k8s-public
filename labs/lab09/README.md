# Lab 09 - Capacity Planning

The goal is to divide your cluster into three environments to run the Pi app: dev, test, and UAT. UAT should be limited to 50% of your node’s total CPU, and dev and test to 25% each. Your Pi Deployment should be set with limits so it can run at least four replicas in every environment, and then you need to verify how much you can scale up to in UAT.

* Start by deploying the namespaces and Services in the lab folder.
* Then work out the CPU capacity of your node, and deploy resource quotas to limit CPU in each namespace (you’ll need to write the quota specs)
* Update the Deployment spec in web.yaml to include a CPU limit that allows four replicas to run in each namespace
* When everything’s running, scale up the UAT Deployment to eight replicas, and try to find out why they don’t all run