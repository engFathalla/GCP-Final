## Terraform code to build infrastucture on GCP [ Google Cloud Platform ] including the following:
* 1- Network [ VPC ] 
* 2- Firewalls
* 3- NAT and Router
* 4- Private GKE [ Google kubernetes Cluster ] 
* 5- Private Compute Engine [ VM ]

## Setup :
* 1- Initialize terraform code 

![home_Page Image](../images/init.jpg)
* 2- Apply terraform code 

![home_Page Image](../images/apply.jpg)
* 3- SSh into VM and install [ gcloud , kubectl , activate Service account ] using  [ Script.sh ]

![home_Page Image](../images/script.jpg)
* 4- Connect to kubernetes cluster 

![home_Page Image](../images/connect.jpg)

* 5- if you will pull your image from private container registry , user this secret resource on kubernates 

kubectl create secret docker-registry countly-registry --docker-server=http://gcr.io --docker-username=_json_key --docker-password="$(cat key.json)"

where key.json is the key for service accout that have permission to access private container registry

![home_Page Image](../images/role.jpg)

and use :
imagePullSecrets:
  - name: countly-registry
in Spec Section 

![home_Page Image](../images/secret.jpg)
