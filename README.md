# Tanzu-Data-Hub-Operations
Installing, configuring and working with TDH


# Installing on TKGS
## Pre-reqs - as on 7/2/24
* Kubernetes - suggests TKR v1.26.5
  * **make sure the cluster can provide ~40 CPU and ~50+GB RAM**
  * 50GB+ available in /etc/containerd per worker node
  * example v1beta1 cluster [here](./data1.yaml)
* Image Registry
* Storage Class supporting at least RWO
* workstation with access to target cluster (Windows, Mac, Linux)

## The Bits
* Download the TDH Installer CLI
* in terminal, navigate to the folder where the tdh-darwin-amd64 file is
* run ```sudo install tdh-darwin-amd64 /usr/local/bin/tdh-installer```
* check version ```tdh-installer version```
* NOTE - mac will complain about it being downloaded from the internet, you'll have to allow it to run under Settings|Privacy & Security

![Image](./images/tdhinstaller-version.png)

## Installer
1. Run ```tdh-installer install --ui``` to start installer in UI mode

![Image](./images/installer1.png)

2. We'll be installing on an existing TKGS cluster, so under Cluster Credentials, select **Tanzu Kubernetes Grid** as the Provider and for ease of install, select and provide the vCenter Credentials, then click **Validate** & **Next**:

![Image](./images/installer2.png)

3. Under Cluster Details, select the vSphere Namespace where the target cluster resides, then select the cluster.  Provide the FQDN of the Supervisor ClusterAPI and the storage class name to use.  (Not sure why this isn't detectable and the default SC isn't used)

![Image](./images/installer3.png)

4. Under **Control Plane Size**, notice how huge even *Tiny* is.  Select the appropriate size - I'm going with **Tiny**

![Image](./images/installer4.png)
