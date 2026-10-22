# Yelp Camp Web Application

This web application allows users to add, view, access, and rate campgrounds by location. It is based on "The Web Developer Bootcamp" by Colt Steele, but includes several modifications and bug fixes. The application leverages a variety of technologies and packages, such as:

- **Node.js with Express**: Used for the web server.
- **Bootstrap**: For front-end design.
- **Mapbox**: Provides a fancy cluster map.
- **MongoDB Atlas**: Serves as the database.
- **Passport package with local strategy**: For authentication and authorization.
- **Cloudinary**: Used for cloud-based image storage.
- **Helmet**: Enhances application security.
- ...

## Setup Instructions

To get this application up and running, you'll need to set up accounts with Cloudinary, Mapbox, and MongoDB Atlas. Once these are set up, create a `.env` file in the same folder as `app.js`. This file should contain the following configurations:

```sh
CLOUDINARY_CLOUD_NAME=[Your Cloudinary Cloud Name]
CLOUDINARY_KEY=[Your Cloudinary Key]
CLOUDINARY_SECRET=[Your Cloudinary Secret]
MAPBOX_TOKEN=[Your Mapbox Token]
DB_URL=[Your MongoDB Atlas Connection URL]
SECRET=[Your Chosen Secret Key] # This can be any value you prefer
```

# End to End K8s Project: 

A 3 tier Camp application like district zomato having front-end, back-end and database.

The main intention of this application is we need to post the campion’s or create an event in the application. If we post them then anyone can buy those tickets.

The application requirements are create the event or anyone wants to book an event. First they have to login to it.

Frontend -> user create or user login by using email, username and password. Rule here is if they provide an email id then same mail id or user name cannot be given for new account creation.

email and user name should be unique 

Once user gets logged in -> Application

Application: user can see list of events or can create a new event 

If anyone wants to create an event : 

What is the event name 
In which location we are going to conduct this event  ( along with google maps )
Price 
Description 
Image 

So all this data has to be stored in database

# Technical Stack: 
To run the application in local I need an EC2 instance. If it works then we need to containerise it and later final deployment in EKS ( Pre and Prod Deployment )

Tools oriented to application are: 
To integrate Google Maps for location, we have to use Map box : https://www.mapbox.com/

Developers will use this map box whenever they want to integrate the maps

To upload an image related to event. To store it we will use cloudinary : https://cloudinary.com/
To integrate images in websites like puma, adidas related to their products 

Kuberntes services for application deployment are 
<img width="240" height="344" alt="image" src="https://github.com/user-attachments/assets/6c57ed60-898e-45e8-9fc2-43c600bf5ed5" />

For database we are not using statefulsets. Want to configure it outside with mangodb. We can create the database and monitor it 

In stateful sets we have to configure pods, PV and PVC. We have to maintain it.
In mongodb we can use the free resources and maintenance is easy 

Here Mapbox, cloudinary and Mongo were third party tools we have to create the accounts of them and get the API keys of it to integrate with application

https://www.mongodb.com/ ( this is same like creation of RDS in AWS cloud )
Click on explore other options and next page is 

<img width="2037" height="1390" alt="image" src="https://github.com/user-attachments/assets/07740c07-56ed-41e2-bf0f-6b86628ef823" />

<img width="2525" height="1191" alt="image" src="https://github.com/user-attachments/assets/49e545b2-e73e-4177-ad3b-be7202c2e87b" />

<img width="1095" height="1126" alt="image" src="https://github.com/user-attachments/assets/58a32cd7-5c6b-4ce1-b654-a3eadc5f5e8e" />

<img width="1042" height="1117" alt="image" src="https://github.com/user-attachments/assets/ea6bb18b-c1d1-46f4-8504-aee99a0e2a44" />

To integrate this cluster with our application we have to allow network ( from application to database layer ).
<img width="2551" height="660" alt="image" src="https://github.com/user-attachments/assets/b6d37fad-96b9-470d-867c-a5976b498a54" />

<img width="2541" height="1097" alt="image" src="https://github.com/user-attachments/assets/eee332a6-15de-4823-be0c-43176539a7b0" />

<img width="2553" height="529" alt="image" src="https://github.com/user-attachments/assets/46c48804-127e-4f36-90a2-73b12495e191" />

Below is my database cluster

<img width="2550" height="873" alt="image" src="https://github.com/user-attachments/assets/bc7a1aab-ee16-4101-8353-f48e58b4a2a3" />

<img width="2492" height="1083" alt="image" src="https://github.com/user-attachments/assets/6bb32288-0489-40a3-8030-c3d22b72483c" />

<img width="2544" height="779" alt="image" src="https://github.com/user-attachments/assets/a78a25e8-563b-4499-9fb6-1e59de6b07c8" />

<img width="2544" height="756" alt="image" src="https://github.com/user-attachments/assets/01267e9a-fa00-4d6f-84df-c09db2d82a04" />

For local testing of application create an EC2 instance
<img width="2543" height="405" alt="image" src="https://github.com/user-attachments/assets/97a7191b-8d2c-4e3f-a1d9-ebc63ba83139" />

To run the application manually we have to use node commands

To get the source code : yum install git -y

https://github.com/JyothsnaVysyaraju/3-Tier-Full-Stack-yelp-camp.git

<img width="1443" height="959" alt="image" src="https://github.com/user-attachments/assets/b22fc5cc-18f9-4de1-bd27-dc3004983816" />

To run this we have to install nodejs in our system

<img width="1862" height="1332" alt="image" src="https://github.com/user-attachments/assets/85816b65-258f-46d6-8e82-9aa4ef3e81cf" />

<img width="1451" height="1341" alt="image" src="https://github.com/user-attachments/assets/949d2f9b-6e88-4d08-b7e1-8dd45b4aaf42" />

To install dependencies: npm install

<img width="2481" height="1051" alt="image" src="https://github.com/user-attachments/assets/4248fb38-ee5e-4540-b2e7-5b3c235da9c1" />

Starting the npm: npm start

<img width="1904" height="835" alt="image" src="https://github.com/user-attachments/assets/f0c59b27-095b-4228-99e8-2b09b96c222d" />

Getting error because we have not yet provided the token. So we have to setup the vim .env file 
And update the required variables

<img width="1678" height="234" alt="image" src="https://github.com/user-attachments/assets/057b85d5-1992-448c-b0fd-c0dfdc2f5fae" />

<img width="1825" height="318" alt="image" src="https://github.com/user-attachments/assets/3072f631-b3e8-45fe-8ada-11761d30dcda" />

<img width="2551" height="1031" alt="image" src="https://github.com/user-attachments/assets/6a978704-0158-4672-9c31-092fd7d3731e" />

<img width="2348" height="1262" alt="image" src="https://github.com/user-attachments/assets/d3e1aeb5-17f7-4b69-a976-b4098c4dc756" />

<img width="2513" height="1313" alt="image" src="https://github.com/user-attachments/assets/1ea0c5c8-5ca2-4746-bd27-17aa679178fd" />

To see the user details in mongodb

<img width="2528" height="1117" alt="image" src="https://github.com/user-attachments/assets/cbf13600-12ee-4a15-804c-94f249982dbf" />

I can see my details under test -> users

<img width="2547" height="735" alt="image" src="https://github.com/user-attachments/assets/234d0f38-18de-42d6-b865-4ac2fe851ce5" />

To host the new Campaign: click one new campground

<img width="2415" height="1174" alt="image" src="https://github.com/user-attachments/assets/73eb3c48-0dba-424b-af6c-8f4b29328092" />

<img width="2515" height="1376" alt="image" src="https://github.com/user-attachments/assets/da8d904a-46c1-40b5-9a9c-94bc528726e7" />

<img width="2483" height="1371" alt="image" src="https://github.com/user-attachments/assets/5f98acd9-3c70-45ab-b66f-85da2e479d02" />

Refresh and check the data in campground in mongodb

<img width="2325" height="862" alt="image" src="https://github.com/user-attachments/assets/3370f073-bf60-44d9-bdf3-e3bde3643a7a" />

We can also see reviews given by end users
<img width="2487" height="1395" alt="image" src="https://github.com/user-attachments/assets/a3e1da56-12ef-4392-b865-83e8393c72fb" />

<img width="2539" height="889" alt="image" src="https://github.com/user-attachments/assets/ef9e5c55-dea8-4e89-97e9-81ae08bf1037" />

Before doing CICD configuration we have to store the .env file . But in real time we cannot store these credentials in GitHub because it is a confidential data. 

We need these env variables while running the application means during container creation
So we can pass these values while creating the container and also we can pass it through the jenkins

# CICD integration and Containerising the application:

<img width="2552" height="546" alt="image" src="https://github.com/user-attachments/assets/43808ea9-46ee-48d5-ad46-e3e1dd0259be" />

yum install java-21-amazon-corretto -y
sudo wget -O /etc/yum.repos.d/jenkins.repo     https://pkg.jenkins.io/rpm-stable/jenkins.repo
yum install jenkins -y
systemctl start jenkins
systemctl status jenkins

<img width="2559" height="452" alt="image" src="https://github.com/user-attachments/assets/822ac997-fc0c-4b46-81ad-eb916f9e33ce" />

<img width="2289" height="1406" alt="image" src="https://github.com/user-attachments/assets/37904044-fc94-487e-b3b6-3614eef72177" />

Install Git, Jenkis, Docker, Sonarqube

Provide access to docker for running jenkins pipeline: chmod 777 /var/run/docker.sock

Sonarqube using docker: docker run -d --name sonar -p 9000:9000 sonarqube:lts-community

Default credentials for sonarqube is admin and admin

<img width="2560" height="394" alt="image" src="https://github.com/user-attachments/assets/9cbe8fd0-5c4b-4c46-b779-7909b2ef2c15" />

Select manually

<img width="2266" height="1142" alt="image" src="https://github.com/user-attachments/assets/2c2ecae9-65de-4ea1-a452-9ebd5e04e3da" />

<img width="1307" height="1091" alt="image" src="https://github.com/user-attachments/assets/4b1ba17e-75d1-4710-85a0-52712a0eb008" />

<img width="2099" height="1135" alt="image" src="https://github.com/user-attachments/assets/643d4b6d-b8b4-4081-8bca-51708125597d" />

<img width="2168" height="1411" alt="image" src="https://github.com/user-attachments/assets/51f200e3-d59c-4a14-a9e0-193c0caafeec" />

withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }

<img width="2546" height="1389" alt="image" src="https://github.com/user-attachments/assets/d0de891c-49db-44a1-82cc-31ff9cd0a263" />

<img width="2520" height="1209" alt="image" src="https://github.com/user-attachments/assets/1f09e76d-ede5-4dfc-a23a-ae4924125323" />

<img width="745" height="680" alt="image" src="https://github.com/user-attachments/assets/0cefa25e-407f-458c-a18d-43dba89fd3a0" />

<img width="2415" height="1394" alt="image" src="https://github.com/user-attachments/assets/b69baab4-e456-48c9-91f4-f0289115f50d" />

<img width="1854" height="1441" alt="image" src="https://github.com/user-attachments/assets/c6c10937-efa4-45e5-8e6f-fdf6ded2afae" />

<img width="2377" height="1115" alt="image" src="https://github.com/user-attachments/assets/e1065685-d39a-4db3-aae9-32a1a7d129da" />

<img width="2116" height="1110" alt="image" src="https://github.com/user-attachments/assets/1c21aa49-dad8-4ca1-a7f4-a4fab3b1685c" />

<img width="2542" height="477" alt="image" src="https://github.com/user-attachments/assets/533d96ae-b287-430a-ad9d-faf9ec55d5e2" />

Quality gates were passed, next we have to create docker file and build the docker image and push the image to docker hub.

To push into docker hub we need docker pipeline plugin

<img width="2552" height="677" alt="image" src="https://github.com/user-attachments/assets/0b81d912-53f7-4939-bf33-08eacd8d98a2" />

<img width="2532" height="640" alt="image" src="https://github.com/user-attachments/assets/a798d6ba-d65b-4e2e-9095-ef5aa53a8df3" />

For smtp configuration

Username: mail id
Password: go to gmail -> apps -> account -> app password

<img width="2211" height="905" alt="image" src="https://github.com/user-attachments/assets/ae439bad-49a4-4e5e-95ce-03099589714e" />

<img width="1736" height="1191" alt="image" src="https://github.com/user-attachments/assets/fedda81c-3f4d-40ab-84ab-1249415d14c4" />

<img width="999" height="945" alt="image" src="https://github.com/user-attachments/assets/221e6fd0-d5fb-4218-9642-9659a2c9dd69" />

<img width="2343" height="1367" alt="image" src="https://github.com/user-attachments/assets/40d93b2e-3055-45ac-a9f8-8382149ec3d7" />

<img width="1093" height="775" alt="image" src="https://github.com/user-attachments/assets/925eb077-84d4-4271-b3b9-e7b7f41f12d7" />

Now build the docker file

<img width="1386" height="1061" alt="image" src="https://github.com/user-attachments/assets/c1138900-b5e3-42cd-8851-b27fdbc55c85" />

To Scan the docker image: curl -sfL https://raw.githubusercontent.com/aquasecurity/trivy/main/contrib/install.sh | sudo sh -s -- -b /usr/local/bin v0.71.2

<img width="1381" height="205" alt="image" src="https://github.com/user-attachments/assets/e771004a-96f3-470d-8736-f5d839d40e13" />

Now configure docker hub credentials in jenkins

<img width="1692" height="1214" alt="image" src="https://github.com/user-attachments/assets/4c2a3223-72ac-477e-9ae5-35bc470a578a" />

<img width="1729" height="1302" alt="image" src="https://github.com/user-attachments/assets/1fc591d8-3bc1-4853-b592-f2e7c79fecf8" />

<img width="1436" height="1221" alt="image" src="https://github.com/user-attachments/assets/8572be84-473c-4009-936f-50134608b30f" />

<img width="1697" height="1292" alt="image" src="https://github.com/user-attachments/assets/94f4d2fd-a9ed-46f2-b282-2a1ed79be88e" />

<img width="2267" height="913" alt="image" src="https://github.com/user-attachments/assets/6d7e8c87-f02e-425c-861d-4382781e92ca" />

<img width="2078" height="293" alt="image" src="https://github.com/user-attachments/assets/2a7241fc-edf5-4949-aacd-855d8194237a" />

Container was created but it is not in running state

<img width="2143" height="301" alt="image" src="https://github.com/user-attachments/assets/e4cbebb8-4bbb-4cc8-b4a3-e48fd92907a7" />

<img width="2143" height="301" alt="image" src="https://github.com/user-attachments/assets/9a4f9fdc-8316-4ab8-8a1e-b2dc1d07af23" />

Tokens related to mapbox, cloundinary and mongo were missing hence container was not running 

We have to integrate the credentials .env file things in the jenkins -> manage jenkins-> credentials-> save them with secret text

<img width="1673" height="1282" alt="image" src="https://github.com/user-attachments/assets/894b7541-36b6-4c5b-8ba1-a000905f27a4" />

<img width="1668" height="1130" alt="image" src="https://github.com/user-attachments/assets/648448c8-2e34-4cd7-9a35-97fcc24d366b" />

<img width="2347" height="965" alt="image" src="https://github.com/user-attachments/assets/59df90a8-1ae3-4fdb-9aa3-eeb933b993c8" />

<img width="2527" height="217" alt="image" src="https://github.com/user-attachments/assets/88787b0f-693d-4922-8a58-7b889aed9195" />

<img width="2542" height="972" alt="image" src="https://github.com/user-attachments/assets/d683ca15-5581-489b-875a-ccf38f0431f9" />

<img width="1407" height="1328" alt="image" src="https://github.com/user-attachments/assets/ed009905-6991-47ac-b915-0e9f5def827f" />

Login with same credentials used while doing testing and create new camp to test the db

<img width="1753" height="1064" alt="image" src="https://github.com/user-attachments/assets/0432fe1a-56ad-4481-93f9-03da11fb048a" />

<img width="2537" height="502" alt="image" src="https://github.com/user-attachments/assets/a725a17f-bdd3-4882-b48a-8267652f0b89" />

<img width="2514" height="1271" alt="image" src="https://github.com/user-attachments/assets/abf09eee-7e6a-4f5d-b152-0715eacf4f10" />

<img width="2544" height="1146" alt="image" src="https://github.com/user-attachments/assets/1ba2ae1b-acf9-4f35-9af3-9e87b2ca9801" />

<img width="2510" height="1108" alt="image" src="https://github.com/user-attachments/assets/ff76e453-f57f-449f-a2c8-883aa9e01aab" />

Now we have to take EKS cluster and create the infrastructure through it

Install terraform

sudo yum install -y yum-utils shadow-utils
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
sudo yum install terraform

https://github.com/JyothsnaVysyaraju/k8s-project-using-terraform.git

<img width="1450" height="1138" alt="image" src="https://github.com/user-attachments/assets/55bf230f-d921-4ff9-8045-c04de084f7a8" />

<img width="515" height="478" alt="image" src="https://github.com/user-attachments/assets/bede8b50-b182-4b80-8ca3-4a96441a2eba" />

<img width="1034" height="212" alt="image" src="https://github.com/user-attachments/assets/3df6c287-87f9-4873-9c07-08db8b141bbd" />

Attach the IAM permissions to existing EC2 instance so that we can access the aws resources through CLI

<img width="1531" height="375" alt="image" src="https://github.com/user-attachments/assets/9af79acb-fb92-4416-b7cd-02202652f65d" />

<img width="1911" height="163" alt="image" src="https://github.com/user-attachments/assets/976e05f9-4395-4bca-990e-f0e1a451395b" />

Once the infra was created, now we have to configure the manifest files for EKS

For Application Deployment -> Deployment.yml is required 
Generally for database we will use statefulset but here for this Project we have configured mongo cloud

If this application needs high availability we have to create HPA ( horizontal pod autoscaling )

Eventhough node gets deleted the pods should not delete at a time for that we have to create resource quota ( requests and limits )

poddisruptionbudgets(PDB): even though application gets updated or new version may come but we can set the limits like always how many no of pods should be in running. So that if its getting updated also some old pods will be in running state ( high availability )

RBAC: to integrate the pipeline with EKS. We have to create a service account, for this service account we have to create role and provide permissions to all the kubernetes resources which we are going to create like deployment, spa, secrets etc and later we have to do the role-binding. We called it as RBAC if we want to do it through jenkins pipeline

<img width="2555" height="1009" alt="image" src="https://github.com/user-attachments/assets/35c01585-a473-4a4e-b0c7-461c3522e1e8" />

Here we have to update our secret values and those secrets has to be provided in encrypted format

<img width="2532" height="646" alt="image" src="https://github.com/user-attachments/assets/050ab506-5fb1-4365-8545-e5325ae907bc" />

Now we have to include all these encoded values in the secret.yml file 

<img width="2543" height="710" alt="image" src="https://github.com/user-attachments/assets/7ca66c03-e8c1-4912-bcfc-989e12e9f9cb" />

<img width="2011" height="761" alt="image" src="https://github.com/user-attachments/assets/431078f1-a350-492a-90d5-e61e718a48ec" />

<img width="2127" height="819" alt="image" src="https://github.com/user-attachments/assets/8fa6e9b8-8bb3-4273-875b-91aa7270cf2e" />

First we have to install EKS CTL 

# for ARM systems, set ARCH to: `arm64`, `armv6` or `armv7`
ARCH=$(uname -m | sed 's/x86_64/amd64/' | sed 's/aarch64/arm64/')
PLATFORM=$(uname -s)_$ARCH

curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"

# (Optional) Verify checksum
curl -sL "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_checksums.txt" | grep $PLATFORM | sha256sum --check

tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp && rm eksctl_$PLATFORM.tar.gz

sudo install -m 0755 /tmp/eksctl /usr/local/bin && rm /tmp/eksctl

<img width="1458" height="788" alt="image" src="https://github.com/user-attachments/assets/bb312843-8e5c-4b5e-8a82-5dd173b20f7c" />

curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.36.2/2026-07-05/bin/linux/amd64/kubectl
To login to our cluster, to switch from one cluster to another cluster: 

aws eks update-kubeconfig --region us-east-1 --name EKS_CLOUD
Once that context was added then only we can see eks nodes

<img width="1942" height="662" alt="image" src="https://github.com/user-attachments/assets/f1f96c1b-0a69-403e-944d-d64595da059d" />

Once that context was added then only we can see eks nodes

<img width="1183" height="157" alt="image" src="https://github.com/user-attachments/assets/8238dbc7-4d0a-4ea8-a6eb-762e6fe1164a" />

Once the cluster was created we have to create the namespace. Inside that namespace all the resources will be created from pipeline

Our manifest files are there in GitHub. To get them into pipeline and execute into that namespace we have to create service account for this namespace, role & role-binding and create an secret and integrate with it.

<img width="334" height="160" alt="image" src="https://github.com/user-attachments/assets/c8d65782-47ad-4257-9e2a-a1cdbdf421c6" />

<img width="1072" height="1087" alt="image" src="https://github.com/user-attachments/assets/99664e40-e82b-477e-b1eb-42e6ad3d549d" />

Now create the role-binding( created app-role was getting attached to the service account which is named jenkins)

<img width="603" height="405" alt="image" src="https://github.com/user-attachments/assets/b80d10ae-4e80-41df-9f81-8db5b1314de4" />

At last if we want to intergrate Jenkins we have to create the secret

<img width="688" height="274" alt="image" src="https://github.com/user-attachments/assets/86c755ce-098d-4b89-a17c-b29f168b96db" />

<img width="875" height="426" alt="image" src="https://github.com/user-attachments/assets/27fe852c-74f1-41a5-a951-4ed613f63d25" />

Now we have to create another pipeline in real time we will create another pipeline for production

<img width="1850" height="1387" alt="image" src="https://github.com/user-attachments/assets/ebf02590-7a2f-416a-b2be-42163314f47c" />

<img width="1054" height="533" alt="image" src="https://github.com/user-attachments/assets/17ca8090-cab4-439c-b1d7-938f216d4a0a" />

Means all the configurations in MyDeployment will be copied to FinalDeployment-PROD pipeline

<img width="2543" height="472" alt="image" src="https://github.com/user-attachments/assets/210e6065-9557-445e-b72b-43455ca01ded" />

Now we have to store the credentials 
As we have created the secret get that secret text 

<img width="2139" height="588" alt="image" src="https://github.com/user-attachments/assets/7f6d6009-8384-43b1-ad61-ace21f96d778" />

This is required because jenkins has to integrate with kubernetes with that namespace
This will works only for this namespace not for others

<img width="2411" height="1026" alt="image" src="https://github.com/user-attachments/assets/c8417469-9326-426a-a468-2382cdd4275a" />



