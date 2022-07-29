**A Tour of Google Cloud Hands-on Labs**

**Lab Name: Creating a Virtual Machine**

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




