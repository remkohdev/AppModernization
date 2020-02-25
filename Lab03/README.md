# 02 - Get Started

## Get Started Email

In preparation for the workshop, each participant also received a `Getting Started` email with information needed to run this workshop and unique for each participant including:

* Your Web Terminal URL,
* Your IKS Cluster Name,
* Your Event Streams Service Name.

In addition, you need your IBM Cloud credentials to be able to login:
* Your email is your IBM ID or username,
* Your password.

# Login to IBM Cloud

1. Open a browser and load your unique `Web Terminal URL` assigned to you,
2. Define the following environment variables used in this workshop. Set the actual values assigned to you.

	* IBM_RG=<your-workshop-id> 
	* IBM_USERID=<your-ibm-id> 
	* IBM_PASSWORD='<your-ibm-password>' 
	* IBM_CFAPI=https://api.ng.bluemix.net 
	* IBM_ORG=<your-ibm-org> 
	* CLUSTER_NAME=<your-iks-cluster-name> 
	* ES_SVC_NAME=<your-eventstreams-service-name> 
	* REGION=<your-region> 
	* ZONE=<your-zone> 
	* ACCOUNTID=<your-account-id>


3. I recommend to open a 'notes.txt' or 'notes.md' file on your Desktop or working directory, to track the settings. You might loose connection to the web terminal or the web terminal, being a stateless container, might restart or session timeout and your will loose the settings. This will help you simply copy-paste to reset your environment.

4. Run setting the environment variables from the web-terminal,

	```console
	$ IBM_RG=<your-workshop-id> IBM_USERID=<your-ibm-id> IBM_PASSWORD='<your-ibm-password>' IBM_CFAPI=https://api.us-east.cf.cloud.ibm.com IBM_ORG=<your-ibm-org> CLUSTER_NAME=<your-iks-cluster-name> ES_SVC_NAME=<your-eventstreams-service-name> REGION=us-east ZONE=wdc04 ACCOUNTID=<your-account-id>
	```

	for region `us-east`, use:
	IBM_CFAPI=https://api.us-east.cf.cloud.ibm.com
	ZONE=wdc04

	for region `us-south` use:
	IBM_CFAPI=https://api.ng.bluemix.net
	ZONE=dal10

	ACCOUNTID and other will be provided in webex chat or slack, or other workshop chat channel, if not already distributed via email.
	
	* You should have received the required information in the `Get Started` email,

5. Login to IBM Cloud, 

	```
	$ ibmcloud login -a cloud.ibm.com -r $REGION -g $IBM_RG -u $IBM_USERID -p "${IBM_PASSWORD}" -c $ACCOUNTID
	$ ibmcloud target --cf-api "${IBM_CFAPI}" 
	```

* Download the configuration for your cluster

	```
	$ ibmcloud ks cluster config --cluster "${CLUSTER_NAME}"
	OK
	Export environment variables to start using Kubernetes.

	export KUBECONFIG=/<your-home-dir>/.bluemix/plugins/container-service/clusters/<your-clustername>/kube-config-<zone>-<your-clustername>.yml
	```

* Set the KUBECONFIG to configure your current-context for kubectl, by copy-paste and running the export command returned in the previous step,

	```console
	$ export KUBECONFIG="/${HOME}/.bluemix/plugins/container-service/clusters/${CLUSTER_NAME}/kube-config-${ZONE}-${CLUSTER_NAME}.yml"
	```

* Test your connection,

	```console
	$ kubectl version --short
	Client Version: v1.14.8
	Server Version: v1.14.8+IKS

	$ kubectl config current-context
	<your-cluster-name>
	```

* Congratulations, you are connected to IBM Cloud and your managed Kubernetes cluster on IBM Cloud. 

