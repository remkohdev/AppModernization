# 02 - Get Started

## Get Started Email

In preparation for the workshop, each participant may have received a `Getting Started` email with information to setup and get started for the workshop. This information may have included:

* Your Web Terminal URL,
* Your IKS Cluster Name,
* Your Event Streams Service Name.

In addition, you need your IBM Cloud credentials to be able to login:
* Your email is your IBM ID or username,
* Your password.

# Login to IBM Cloud

To login and configure your connection,
```
$ IBM_USERID=<your IBMCloud ID> IBM_PASSWORD='<IBMCloud Password>' IBM_CFAPI=https://api.us-south.cf.cloud.ibm.com IBM_ORG="<org name>" CLUSTER_NAME=<org name>iksuser<user number>  ES_SVC_NAME=<org name>esuser<user number> REGION=us-south ZONE=dal10 SPACE=dev ACCOUNTID=<account id>
$ ibmcloud login -u $IBM_USERID -p $IBM_PASSWORD -c $ACCOUNTID -r $REGION -o "${IBM_ORG}" -s $SPACE
```

Configure the Resource Group for completion,
```
$ ibmcloud target -g default
```

Set the kubectl config context,
```
$ eval $(ibmcloud ks cluster config --cluster "${CLUSTER_NAME}" --export)
```

## Local Terminal

If you are using a local machine with a terminal and browser follow these instructions. If you are using a web terminal in a browser, jump to the instructions for Web Terminal.

1. Open a Browser and follow the installation instructions for IBM Cloud CLI and Developer Tools at https://cloud.ibm.com/docs/cli?topic=cloud-cli-getting-started,
2. You should now have Git, Docker, Helm, kubectl, curl and several IBM Cloud CLI plugins. Test your installation,

```
$ ibmcloud -v
$ ibmcloud plugin list
```

3. Install the Event Streams plugin, detailed instructins are at https://cloud.ibm.com/docs/services/EventStreams?topic=eventstreams-cli#step5_es_cli

```
$ ibmcloud plugin install event-streams
$ ibmcloud plugin list
```

4. Download the binaries of the Kafka distribution, which includes console tools used in the labs,
5. Install Istio,
6. Some steps in the labs use Node.js or Java and the Spring Framework. You can choose to install these or audit these sections of the labs,

Optional: If you're interested what detailed tools are needed to cover all steps in all the Application Modernization labs, you could review the Web Terminal's Dockerfile at https://github.com/remkohdev/web-terminal/blob/master/bin/web-terminal-clusters-setup/Dockerfile-ttyd-iks-labs.

## Web Terminal 

If you are using a web-terminal for the workshop use these instructions.

1. Open a browser and load your unique `Web Terminal URL` assigned to you,

2. Run setting the environment variables from the web-terminal,

	```
	$ IBM_USERID=<your IBMCloud ID> IBM_PASSWORD='<IBMCloud Password>' IBM_CFAPI=https://api.us-south.cf.cloud.ibm.com IBM_ORG="<org name>" CLUSTER_NAME=<org name>iksuser<user number>  ES_SVC_NAME=<org name>esuser<user number> REGION=us-south ZONE=dal10 SPACE=dev ACCOUNTID=<account id>
	$ ibmcloud login -u $IBM_USERID -p $IBM_PASSWORD -c $ACCOUNTID -r $REGION -o "${IBM_ORG}" -s $SPACE
	```

	for region `us-east`, use:
	IBM_CFAPI=https://api.us-east.cf.cloud.ibm.com
	ZONE=wdc04

	for region `us-south` use:
	IBM_CFAPI=https://api.us-south.cf.cloud.ibm.com
	ZONE=dal10

	ACCOUNTID and other will be provided in webex chat or slack, or other workshop chat channel, if not already distributed via email.
	
	* You should have received the required information in the `Get Started` email,

5. Login to IBM Cloud, 

	```
	$ ibmcloud login -u $IBM_USERID -p $IBM_PASSWORD -c $ACCOUNTID -r $REGION -o "${IBM_ORG}" -s $SPACE
	$ ibmcloud target --cf-api "${IBM_CFAPI}" 
	```

* Download the configuration for your cluster

	```
	$ eval $(ibmcloud ks cluster config --cluster "${CLUSTER_NAME}" --export)
	```

	Which is shorthand for 
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

