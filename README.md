# Tanzu-Data-Hub-Operations
Installing, configuring and working with TDH


# Installing
## Pre-reqs - as on 7/2/24
* Kubernetes - suggests TKR v1.26.5
* Image Registry
* Storage Class supporting at least RWO
* workstation with access to target cluster (Windows, Mac, Linux)

## The Bits
* Download the TDH Installer CLI
* in terminal, navigate to the folder where the tdh-darwin-amd64 file is
* run ``sudo install tdh-darwin-amd64 /usr/local/bin/tdh-installer```
* check version ```tdh-installer version```
* NOTE - mac will complain about it being downloaded from the internet, you'll have to allow it to run under Settings|Privacy & Security
![Image](./images/tdhinstallerversion.png)
