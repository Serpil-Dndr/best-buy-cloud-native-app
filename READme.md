# Best Buy Cloud-Native App

## Table of Contents
- [Application Overview](#application-overview)
- [Updated Architecture Diagram](#updated-architecture-diagram)
- [Application and Architecture Explanation](#application-and-architecture-explanation)
- [Deployment Instructions](#deployment-instructions)
- [Microservice Repositories](#microservice-repositories)
- [Docker Images](#docker-images)
- [Demo Video](#demo-video)
- [Issues and Limitations](#issues-and-limitations)

---

## Application Overview
This cloud-native application is designed to demonstrate a scalable and AI-integrated solution for Best Buy's online store. The application is built using a microservices architecture, deployed in a Kubernetes cluster, and features AI-powered product descriptions and image generation using GPT-4 and DALL-E.

### Components:
- **Store-Front**: Customer-facing web app for browsing products and placing orders.
- **Store-Admin**: Employee-facing admin app for managing product data and viewing orders.
- **Order-Service**: Handles order creation and sends order data to the managed queue (Azure Service Bus).
- **Product-Service**: CRUD operations for product data.
- **Makeline-Service**: Processes orders by consuming messages from the queue.
- **AI-Service**: AI-generated product descriptions and images using GPT-4 and DALL-E.
- **Database**: MongoDB for storing order and product data.


---
## Application and Architecture Explanation

The application follows a microservices-based architecture, with each service handling a specific business functionality. The services communicate via HTTP, and MongoDB is used for storing product and order information. Kubernetes manages the deployment, scaling, and configuration of all services.
## Architecture


![architecture](architecture-best-buy.png)

## Deployment Instructions
Follow these steps to deploy the application in a Kubernetes cluster:

1. Clone all microservice repositories:
   ```bash
   git clone https://github.com/Serpil-Dndr/best-buy-cloud-native-app.git

   ```

## Table of Microservice Repositories:

The application has the following services: 
| Service                  | Description                                    | GitHub Repo                                                                                      |
|--------------------------|------------------------------------------------|--------------------------------------------------------------------------------------------------|
| `store-front-bestbuy`    | Web app for customers to place orders (Vue.js) | [store-front-bestbuy](https://github.com/Serpil-Dndr/store-front-best-buy.git)                   |
| `product-service-bestbuy`| Service to manage products for Best Buy        | [product-service-bestbuy](https://github.com/Serpil-Dndr/product-service-best-buy.git)           |
| `order-service-bestbuy`  | Service to handle orders for Best Buy          | [order-service-bestbuy](https://github.com/Serpil-Dndr/order-service-best-buy.git)               |
| `store-admin-bestbuy`    | Admin interface to manage Best Buy products    | [store-admin-bestbuy](https://github.com/Serpil-Dndr/store-admin-best-buy.git)                   |
| `ai-service-bestbuy`     | AI service to generate product descriptions and images | [ai-service-bestbuy](https://github.com/Serpil-Dndr/ai-service-best-buy.git)                     |
| `makeline-service-bestbuy`| Service to manage product assembly lines for Best Buy | [makeline-service-bestbuy](https://github.com/Serpil-Dndr/makeline-service-best-buy.git)         |


## Deployment Instructions

Follow these steps to deploy the application in a Kubernetes cluster:

### 1. Build Docker Images for Each Service
For each microservice, build the Docker image and push it to Docker Hub.

```bash
docker build -t <username>/<service-name>:latest .
docker push <username>/<service-name>:latest
```


## Docker Images Table

A table listing all Docker images you created, including their names and links to their Docker Hub repositories.

| Service               | Docker Image Link                                                    |
|-----------------------|----------------------------------------------------------------------|
| Store-Front           | [https://hub.docker.com/repository/docker/serpild/store-front/general](https://hub.docker.com/repository/docker/serpild/store-front-l8/general) |
| Order-Service         | [https://hub.docker.com/repository/docker/serpild/order-service/general](https://hub.docker.com/repository/docker/serpild/order-service-l8/general) |
| Product-Service       | [https://hub.docker.com/repository/docker/serpild/product-service/general](https://hub.docker.com/repository/docker/serpild/product-service-l8/general) |
| Makeline-Service      | [https://hub.docker.com/repository/docker/serpild/makeline-service/general](https://hub.docker.com/repository/docker/serpild/makeline-service-l8/general) |
| Store-Admin           | [https://hub.docker.com/repository/docker/serpild/store-admin/general](https://hub.docker.com/repository/docker/serpild/store-admin-l8/general) |
| AI-Service            | [https://hub.docker.com/repository/docker/serpild/ai-service-l8/general](https://hub.docker.com/repository/docker/serpild/ai-service-l8/general) |



## Apply Kubernetes Manifest Files
Once the Docker images are pushed to Docker Hub, apply the Kubernetes deployment files.

```bash

kubectl apply -f  best-buy.yaml

```

### Access the Application
After the deployment is complete, you can access the application using the following URLs:

- **Store-Front**: `http://<load-balancer-ip>:3000`
- **Store-Admin**: `http://<load-balancer-ip>:3001`
