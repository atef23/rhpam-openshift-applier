# RHPAM Openshift Applier
This project runs the Openshift Applier ( https://github.com/redhat-cop/openshift-applier ) ansible role with Red Hat Process Automation Manager (RHPAM) installation tasks

## Prerequisites
- Ansible Installed
- Openshift Cluster with namespace created to install RHPAM in

## Steps to Run RHPAM Openshift Install
`oc login <openshift_cluster_endpoint>`

`oc project <openshift_namespace>`

`git clone https://github.com/atef23/rhpam-openshift-applier.git`

`cd rhpam-openshift-applier/`

`ansible-galaxy install -r requirements.yml -p roles`

`ansible-playbook -i inventory/ apply.yml -e include_tags=deploy-authoring-template -e namespace=<openshift_namespace>`

Use include_tags to run various installation configurations (deploy-authoring-template, deploy-trial-ephemeral-template, etc)
