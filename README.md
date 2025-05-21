# Deploying MongoDB and Mongo Express

## **Project Overview**
This project demonstrates building a web application (Mango-express)  and its database (Mango-db). 

---

## **Prerequisites**
- Minikube cluster running
  
## **Deploying MongoDB and MongoExpress**
- Created MongoDB Deployment
  --	Configure the deployment file to include port 27017 which is MongoDB port
  b.	Added env variable with name and values for the username and password.
  c.	The values will be in the secret config file
3.	Created secret config file
a.	The value of the secrets (username and password) is base 64 encoded
b.	          echo -n ‘username’ | base64  =  values will be paste in secret file
c.	          echo -n ‘password’ | base64  =  values will be paste in secret file
d.	Always create secret before Deployments since you want Deployment to reference it.
e.	The secret is reference using the “Value from” “secretKeyRef” 
4.	Create secret and then deployment
5.	Create service config file for MongoDB
6.	Created MongoExpress Deployment
a.	Which database it should connect to? MongoDB address.
b.	Which credentials to authenticate (username and password)
7.	Create configmap configuration file
a.	This where we reference the database url (address)
b.	Create configmap deployment 
c.	Create MongoExpress
8.	Accessing MongoExpress from the browser.
a.	Create MongoExpress service
b.	Under selector specify the service type to be LoadBalancer
c.	Specify NodePort under ports; values are from 30000-32767 
d.	Use minikube service “service name “to access the browser.

 
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
