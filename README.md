# Deploy-application-using-CI-CD-Freestyle-application-with-5-Stages-

my pipline is : 

stage 1 for git code 

stage 2 for build code 

stage3 for create image 

stage 4 for upload image to docker hub repo 

stage 5  deploy to K&8s  

## steps : 

1-Install Jenkins manually on the same VM as the Kubernetes master node.

Prepare the Kubernetes cluster using kubeadm, with:

1 Master node

2 Worker nodes

3- Access the Jenkins Web UI using: http://192.168.142.159:8080/

4- Install and configure the required Jenkins plugins, including the Kubernetes API Plugin and other required plugins for Kubernetes integration.

5-Create Kubernetes credentials in Jenkins using a Kubernetes Service Account token/key. These credentials allow Jenkins to authenticate with the Kubernetes cluster and deploy applications directly to the Kubernetes environment.

6- on master node run : 

[root@master01 lib]# kubectl get secret $SECRET -n jenkins -o jsonpath='{.data.token}' | base64 --decode


[root@master01 lib]# SECRET=$(kubectl get serviceaccount jenkins-sa -n jenkins -o jsonpath='{.secrets[0].name}')

kubectl get secret $SECRET -n jenkins -o jsonpath='{.data.token}' | base64 --decode

[root@master01 lib]# kubectl create token jenkins-sa -n jenkins

<img width="1640" height="138" alt="image" src="https://github.com/user-attachments/assets/c806ef9d-295b-4199-82f8-c07b1706163e" />

7- Add the Kubernetes credentials in Jenkins → Manage Jenkins → Credentials.

<img width="1718" height="747" alt="image" src="https://github.com/user-attachments/assets/18c4ce67-cc70-45a6-b5ea-18152698d578" />

8- Create Docker Hub credentials in Jenkins:

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/505453aa-38c3-40a4-a06f-79f98b541d99" />

7- Start building the Jenkins pipeline stages as follows:

## Stage 1 using for git code from source repo  :

<img width="1650" height="891" alt="image" src="https://github.com/user-attachments/assets/494f55c9-c290-4d88-91df-37ea71cddef4" />

## Stage 2 using to maven to build code   :

<img width="1277" height="902" alt="image" src="https://github.com/user-attachments/assets/c55ee737-dfb2-4308-8ea8-632253598d97" />

## stage3 to build image after build code : 

<img width="1338" height="972" alt="image" src="https://github.com/user-attachments/assets/c6ecf752-2971-4c60-b09e-5bcc91410905" />

## stage 4 to uploade image to docker hub repo : 

<img width="1627" height="877" alt="image" src="https://github.com/user-attachments/assets/2930e7be-65e1-42dc-b32b-f00d92980847" />

<img width="1186" height="947" alt="image" src="https://github.com/user-attachments/assets/1f63d44b-a303-4ee1-8c9b-05b54529ba1e" />

## Stage 5 deploy app to the cluster kubernates environment : 

<img width="1555" height="897" alt="image" src="https://github.com/user-attachments/assets/0e51d0dc-14e7-4082-ae80-694437298166" />

<img width="1650" height="957" alt="image" src="https://github.com/user-attachments/assets/3414370a-4e8f-4821-b9c7-8d98af46f609" />

<img width="1712" height="957" alt="image" src="https://github.com/user-attachments/assets/7b3eb5c3-4567-4ec0-83cf-e9af98c624e6" />

## and finally start pipline : 

<img width="1891" height="722" alt="image" src="https://github.com/user-attachments/assets/4fc8b5b0-7670-4549-a174-cd8f678fabc4" />

## test environment  

<img width="752" height="377" alt="image" src="https://github.com/user-attachments/assets/85bd35c2-ecd3-4d54-8d73-9eadc8f53dd0" />

<img width="1590" height="877" alt="image" src="https://github.com/user-attachments/assets/29feeb2a-1880-409d-8676-61e089df5ae2" />








