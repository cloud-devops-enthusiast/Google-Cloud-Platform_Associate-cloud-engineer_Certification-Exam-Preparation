**A Tour of Google Cloud Hands-on Labs**

**Lab Name: Creating a Virtual Machine (GSP001)**

*Task 1: Create a new instance from the Cloud Console*

Creating a VM with the given configurations.

Zone: us-east4-b

<!---lab1.1.png--->
![lab1.1](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/3492ff64ad28f7e509b34fadb921920119d77ce7/practice-labs/lab-screenshot/lab1.1.png "Image1")

*Task 2: Install an NGINX web server*

Update the OS

    sudo apt-get update

Install Nginx

    sudo apt-get install -y nginx

Checking whether nginx is running or not

    ps auwx | grep nginx

<!---lab1.2.png--->
![lab1.2](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/3492ff64ad28f7e509b34fadb921920119d77ce7/practice-labs/lab-screenshot/lab1.2.png "Image2")

*Task 3: Create a new instance with gcloud*

Using gcloud to create a new VM's from command line

     gcloud compute instances create gcelab2 --machine-type e2-medium --zone us-east4-b

To see all defaults of the gcloud command, use the following command:

    gcloud compute instances create --help

Using google cloud shell to ssh into the created VM

    gcloud compute ssh gcelab2 --zone

<!---lab1.3.png--->
![lab1.3](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/3492ff64ad28f7e509b34fadb921920119d77ce7/practice-labs/lab-screenshot/lab1.3.png "Image3")

*Task 4: Test your knowledge*

You can create a VM instance in compute engine using The cloud console and the gcloud command line tool.



###########################################################################################################



**Lab Name: Getting Started with Cloud Shell and gcloud (GSP002)**

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