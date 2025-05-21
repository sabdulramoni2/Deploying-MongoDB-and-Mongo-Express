# Deploying MongoDB and Mongo Express

## **Project Overview**
This project demonstrates building a web application (Mango-express)  and its database (Mango-db). 

---

## **Prerequisites**
- Minikube cluster running
  
## **Deploying MongoDB and MongoExpress**
- Created MongoDB Deployment
  -	Configure the deployment file to include port 27017 which is MongoDB port
  - Added env variable with name and values for the username and password.
  - The values will be in the secret config file
-	Created secret config file
     - The value of the secrets (username and password) is base 64 encoded
     - echo -n ‘username’ | base64  =  values will be paste in secret file
     - echo -n ‘password’ | base64  =  values will be paste in secret file
     - Always create secret before Deployments since you want Deployment to reference it.
     - The secret is reference using the “Value from” “secretKeyRef” 
- Create secret and then deployment
- Create service config file for MongoDB
- Created MongoExpress Deployment
    - Which database it should connect to? MongoDB address.
    - Which credentials to authenticate (username and password)
-	Create configmap configuration file
    -	This where we reference the database url (address)
    - Create configmap deployment 
    -	Create MongoExpress
-	Accessing MongoExpress from the browser.
    -	Create MongoExpress service
    -	Under selector specify the service type to be LoadBalancer
    -	Specify NodePort under ports; values are from 30000-32767
    -	Use minikube service “service name “to access the browser.

 
---

## **Deploying MongoDB and MongoExpress**
- Created MongoDB Deployment
- Created Secret for Mongo Credentials
  
  ![image](https://github.com/user-attachments/assets/ca8c8afd-e725-4a42-920e-704c45b9787d)

- Created MongoDB Internal Service

  ![image](https://github.com/user-attachments/assets/a72db9cc-2d3a-4024-8f81-65cd7b808bfa)

- Created MongoExpress Deployment
- Created ConfigMap for DB Server URL
- Created Mongo Express External Service

  ![image](https://github.com/user-attachments/assets/15471577-5957-449e-9b2f-73d201b38e05)


  ![image](https://github.com/user-attachments/assets/640b1e1e-a0ab-497b-9f89-3e6decb51269)


## **Useful Links:**
- **Mongo Express Docker Image**:  https://hub.docker.com/_/mongo-express

---
