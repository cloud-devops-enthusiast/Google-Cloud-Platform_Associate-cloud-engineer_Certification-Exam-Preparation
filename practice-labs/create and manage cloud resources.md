**A Tour of Google Cloud Hands-on Labs**

**Lab Name: Creating a Virtual Machine (GSP001)**

Lab Link: https://www.cloudskillsboost.google/catalog_lab/1427

*Task 1: Create a new instance from the Cloud Console*

Creating a VM with the given configurations.

Zone: us-east4-b

<!---lab1.1.png--->
![lab1.1](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/6f1d1ad98e743e815289c2c3d6e111d698bcee0c/practice-labs/lab-screenshot/lab%201.1.png "Image1")

*Task 2: Install an NGINX web server*

Update the OS

    sudo apt-get update

Install Nginx

    sudo apt-get install -y nginx

Checking whether nginx is running or not

    ps auwx | grep nginx

<!---lab1.2.png--->
![lab1.2](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/6f1d1ad98e743e815289c2c3d6e111d698bcee0c/practice-labs/lab-screenshot/lab%201.2.png "Image2")

*Task 3: Create a new instance with gcloud*

Using gcloud to create a new VM's from command line

     gcloud compute instances create gcelab2 --machine-type e2-medium --zone us-east4-b

To see all defaults of the gcloud command, use the following command:

    gcloud compute instances create --help

Using google cloud shell to ssh into the created VM

    gcloud compute ssh gcelab2 --zone

<!---lab1.3.png--->
![lab1.3](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/6f1d1ad98e743e815289c2c3d6e111d698bcee0c/practice-labs/lab-screenshot/lab%201.3.png "Image3")

*Task 4: Test your knowledge*

You can create a VM instance in compute engine using The cloud console and the gcloud command line tool.



###########################################################################################################



**Lab Name: Getting Started with Cloud Shell and gcloud (GSP002)**

Lab Link: https://www.cloudskillsboost.google/catalog_lab/320

*Task 1. Configure your environment

Set the region to us-east1
        
    gcloud config set compute/region us-east1 

To recheck the region, use the following command:
        
    gcloud config get-value compute/region

Set the zone to us-east1-d
        
    gcloud config set compute/zone us-east1-d

To recheck the zone, use the following command:
        
    gcloud config get-value compute/zone

Store your PROJECT_ID into varianle project id
        
    export PROJECT_ID=qwiklabs-gcp-03-3a5333a6f3a8

Store your zone into the variable zone
        
    export ZONE=us-east1-d 

Create VM in your desired zone.
        
    gcloud compute instances create gcelab2 --machine-type e2-medium --zone $ZONE    

<!---lab2.1.png---> 
![lab2.1](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/6a2f1e142ab2dadbeafe40e20dbfb670048b9b04/practice-labs/lab-screenshot/lab%202.1.PNG "Image1")


*Task 2. Filtering command line output*

List compute instances available in the project

    gcloud compute instances list

List the firewall rules of the VM
        
    gcloud compute firewall-rules list

<!---lab2.2.png---> 
![lab2.2](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/6a2f1e142ab2dadbeafe40e20dbfb670048b9b04/practice-labs/lab-screenshot/lab%202.2.PNG "Image2")

*Task 3. Connecting to your VM instance*

Connect to the VM instance using the following command:

    gcloud compute ssh gcelab2 --zone $ZONE

Install Nginx web server
        
    sudo apt-get update

    sudo apt-get install -y nginx

<!---lab2.3.png---> 
![lab2.3](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/6a2f1e142ab2dadbeafe40e20dbfb670048b9b04/practice-labs/lab-screenshot/lab%202.3.PNG "Image3")

*Task 4. Updating the Firewall*

List the firewall rules
        
    gcloud compute firewall-rules list

Add tag to your virtual machine
        
    gcloud compute instances add-tags gcelab2 --tags http-server,https-server   

Update the firewall rule to allow
        
    gcloud compute firewall-rules create default-allow-http --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server

List the firewall rule for project 
        
    gcloud compute firewall-rules list --filter=ALLOW:'80'

Verify communication from VM
        
    curl http://$(gcloud compute instances list --filter=name:gcelab2 --format='value(EXTERNAL_IP)')

<!---lab2.4.png--->
![lab2.4](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/6a2f1e142ab2dadbeafe40e20dbfb670048b9b04/practice-labs/lab-screenshot/lab%202.4.PNG "Image4")

*Task 5. Viewing the system logs*

View available logs of system

    gcloud logging logs list 

View the logs related to the compute

    gcloud logging logs list --filter="compute" 

<!---lab2.5.png---> 
![lab2.5](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/6a2f1e142ab2dadbeafe40e20dbfb670048b9b04/practice-labs/lab-screenshot/lab%202.5.PNG "Image5")

*Task 6. Test your understanding*

The three basic ways to interact with google cloud services and resources are Client Libraries, Cloud Console and Command Line Interface.



###########################################################################################################



**Lab Name: Kubernetes Engine: Qwik Start (GSP100)**

Lab Link: https://www.cloudskillsboost.google/catalog_lab/911

*Task 1. Set a default compute zone*

Set the default region

    gcloud config set compute/region us-central1

Set the default zone
        
    gcloud config set compute/zone us-central1-a

<!---lab3.1.png--->
![lab3.1](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/f4522a7482eb40d25328d7ea06b49c4f971a8720/practice-labs/lab-screenshot/lab%203.1.PNG "Image1")

*Task 2. Create a GKE cluster*

Create a cluster using the google cloud shell

    gcloud container clusters create --machine-type=e2-medium lab-cluster

<!---lab3.2.png--->
![lab3.2](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/f4522a7482eb40d25328d7ea06b49c4f971a8720/practice-labs/lab-screenshot/lab%203.2.PNG "Image2")

*Task 3. Get authentication credentials for the cluster*

Authenticate to the cluster
        
    gcloud container clusters get-credentials lab-cluster

<!---lab3.3.png--->
![lab3.3](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/f4522a7482eb40d25328d7ea06b49c4f971a8720/practice-labs/lab-screenshot/lab%203.3.PNG "Image3")

*Task 4. Deploy an application to the cluster*

Create a deployment of name *hello-server* from the *hello-app* container image, run the following kubectl command:

    kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0

To create a *kubernetes service* in which you have to expose the clusters to the internet by opening a port on the cluster.
        
    kubectl expose deployment hello-server --type=LoadBalancer --port=8080

To check the service use this command:

    kubectl get service

Use the external ip of your kubernetes cluster followed by the port number and use that in the browser whether it's working or not:

    http://[EXTERNAL-IP]:8080

<!---lab3.4.png--->
![lab3.4](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/f4522a7482eb40d25328d7ea06b49c4f971a8720/practice-labs/lab-screenshot/lab%203.4.PNG "Image4")

*Task 5. Deleting the cluster*

To delete kuberenetes cluster use the following command:

    gcloud container clusters delete lab-cluster

<!---lab3.5.png--->
![lab2.5](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/f4522a7482eb40d25328d7ea06b49c4f971a8720/practice-labs/lab-screenshot/lab%203.5.PNG "Image5")



###########################################################################################################



**Lab Name: Set Up Network and HTTP Load Balancers (GSP007)**

Lab Link: https://www.cloudskillsboost.google/catalog_lab/329

*Task 1. Set the default region and zone for all resources*

Set the default region

    gcloud config set compute/region us-west4

Set the default zone
        
    gcloud config set compute/zone us-west4-c

<!---lab4.1.png--->
![lab4.1](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/22827cd85f6f3df2aab5073b1371cea8f764896a/practice-labs/lab-screenshot/lab%204.1.PNG "Image1")

*Task 2. Create multiple web server instances*

Create a virtual machine www1 in your default zone:

      gcloud compute instances create www1 \
    --zone= us-west4-c \
    --tags=network-lb-tag \
    --machine-type=e2-medium \
    --image-family=debian-11 \
    --image-project=debian-cloud \
    --metadata=startup-script='#!/bin/bash
      apt-get update
      apt-get install apache2 -y
      service apache2 restart
      echo "
    <h3>Web Server: www1</h3>" | tee /var/www/html/index.html'

Create a virtual machine www2 in your default zone:

      gcloud compute instances create www2 \
    --zone= us-west4-c \
    --tags=network-lb-tag \
    --machine-type=e2-medium \
    --image-family=debian-11 \
    --image-project=debian-cloud \
    --metadata=startup-script='#!/bin/bash
      apt-get update
      apt-get install apache2 -y
      service apache2 restart
      echo "
    <h3>Web Server: www2</h3>" | tee /var/www/html/index.html'

Create a virtual machine in your default zone:
        
      gcloud compute instances create www3 \
    --zone= us-west4-c \
    --tags=network-lb-tag \
    --machine-type=e2-medium \
    --image-family=debian-11 \
    --image-project=debian-cloud \
    --metadata=startup-script='#!/bin/bash
      apt-get update
      apt-get install apache2 -y
      service apache2 restart
      echo "
    <h3>Web Server: www3</h3>" | tee /var/www/html/index.html'

Create a firewall rule to allow external traffic to the VM:

    gcloud compute firewall-rules create www-firewall-network-lb \
    --target-tags network-lb-tag --allow tcp:80

Run the following command to see IP addresses:

    gcloud compute instances list

Verify the instances are running:

    curl http://[IP_ADDRESS]

<!---lab4.2.png--->
![lab4.2](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/22827cd85f6f3df2aab5073b1371cea8f764896a/practice-labs/lab-screenshot/lab%204.2.PNG "Image2")

*Task 3. Configure the load balancing service*

Create a static external IP addresses for your load balancer:

       gcloud compute addresses create network-lb-ip-1 \
    --region us-west4

Add a legacy HTTP health check resource:

    gcloud compute http-health-checks create basic-check

Add a target pool in the same region as your instances.

      gcloud compute target-pools create www-pool \
    --region us-west4 --http-health-check basic-check

Add the instances to the pool:

    gcloud compute target-pools add-instances www-pool \
    --instances www1,www2,www3

Add a forwarding rule:

    gcloud compute forwarding-rules create www-rule \
    --region us-west4 \
    --ports 80 \
    --address network-lb-ip-1 \
    --target-pool www-pool

<!---lab4.3.png--->
![lab4.3](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/22827cd85f6f3df2aab5073b1371cea8f764896a/practice-labs/lab-screenshot/lab%204.3.PNG "Image3")

*Task 4. Sending traffic to your instances*

Enter command to view the external IP address of the www-rule forwarding rule used by the load balancer:

    gcloud compute forwarding-rules describe www-rule --region us-west4

Access the external IP address of the load balancer:

    IPADDRESS=$(gcloud compute forwarding-rules describe www-rule --region us-west4 --format="json" | jq -r .IPAddress)

To view the external IP addresses:

    echo $IPADDRESS

Use curl command to access the external IP address, replacing IP_ADDRESS with an external IP address from the previous command:

    while true; do curl -m1 $IPADDRESS; done

<!---lab4.4.png--->
![lab4.4](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/22827cd85f6f3df2aab5073b1371cea8f764896a/practice-labs/lab-screenshot/lab%204.4.PNG "Image4")

*Task 5. Create an HTTP load balancer*

Create load balancer template

    gcloud compute instance-templates create lb-backend-template \
   --region= us-west4 \
   --network=default \
   --subnet=default \
   --tags=allow-health-check \
   --machine-type=e2-medium \
   --image-family=debian-11 \
   --image-project=debian-cloud \
   --metadata=startup-script='#!/bin/bash
     apt-get update
     apt-get install apache2 -y
     a2ensite default-ssl
     a2enmod ssl
     vm_hostname="$(curl -H "Metadata-Flavor:Google" \
     http://169.254.169.254/computeMetadata/v1/instance/name)"
     echo "Page served from: $vm_hostname" | \
     tee /var/www/html/index.html
     systemctl restart apache2'

Create a managed instance group based on the template:

    gcloud compute instance-groups managed create lb-backend-group \
   --template=lb-backend-template --size=2 --zone= us-west4-c

Create the fw-allow-health-check firewall rule.

    gcloud compute firewall-rules create fw-allow-health-check \
  --network=default \
  --action=allow \
  --direction=ingress \
  --source-ranges=130.211.0.0/22,35.191.0.0/16 \
  --target-tags=allow-health-check \
  --rules=tcp:80

Set up a global static external IP address which can be used to set up a global static external IP address

    gcloud compute addresses create lb-ipv4-1 \
  --ip-version=IPV4 \
  --global

    gcloud compute addresses describe lb-ipv4-1 \
  --format="get(address)" \
  --global

Create a health check for the load balancer:

    gcloud compute health-checks create http http-basic-check \
  --port 80

Create a backend service:

    gcloud compute backend-services create web-backend-service \
  --protocol=HTTP \
  --port-name=http \
  --health-checks=http-basic-check \
  --global

Add your instance group as the backend to the backend service:

    gcloud compute backend-services add-backend web-backend-service \
  --instance-group=lb-backend-group \
  --instance-group-zone= \
  --global

Create a URL map to route the incoming requests to the default backend service:

    gcloud compute url-maps create web-map-http \
    --default-service web-backend-service

Create a target HTTP proxy to route requests to your URL map:

    gcloud compute target-http-proxies create http-lb-proxy \
    --url-map web-map-http

Create a global forwarding rule to route incoming requests to the proxy:

    gcloud compute forwarding-rules create http-content-rule \
    --address=lb-ipv4-1\
    --global \
    --target-http-proxy=http-lb-proxy \
    --ports=80

<!---lab4.5.png--->
![lab4.5](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/22827cd85f6f3df2aab5073b1371cea8f764896a/practice-labs/lab-screenshot/lab%204.5.PNG "Image5")

*Task 6. Testing traffic sent to your instances*

Go to Network services > Load balancing.

Click on the load balancer you created (web-map-http)

In the backend section, check for the VM instances you created are in Healthy state.

When the VMs are healthy, test the load balancer using a web browser, going to http://IP_ADDRESS/, replacing IP_ADDRESS with the load balancer's IP address.

<!---lab4.6.png--->
![lab4.6](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/22827cd85f6f3df2aab5073b1371cea8f764896a/practice-labs/lab-screenshot/lab%204.6.PNG "Image6")