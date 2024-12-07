# Cloud-Native App for Best Buy
Welcome to the **Best Buy Store ** application.

This sample demo app consists of a group of containerized microservices that can be easily deployed into a Kubernetes cluster. It demonstrates a realistic scenario using a polyglot architecture, event-driven design, and common open-source back-end services (e.g., RabbitMQ, MongoDB). The application also integrates OpenAI's models to generate product descriptions and recommendations. This functionality can utilize either [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/overview) or [OpenAI](https://openai.com/).

This application is inspired by Azure Kubernetes Service (AKS) quickstart demo [Azure Kubernetes Service (AKS) Docs](https://learn.microsoft.com/en-us/azure/aks/).

> [!NOTE]
> This is not intended as an example of production-ready code but rather a demonstration of a realistic application running in Kubernetes.

---

## Architecture
![architecture](https://github.com/user-attachments/assets/ec8c47d8-9c7f-4834-a954-46353c70242c)


## Table of Microservice Repositories:

The application has the following services: 
| Service                 | Description                                    | Github Repo                                                      |
|-------------------------|------------------------------------------------|-------------------------------------------------------------------|
| `store-front-bestbuy`    | Web app for customers to place orders (Vue.js) | [store-front-bestbuy](https://github.com/Serpil-Dndr/store-front-best-buy.git) |
| `product-service-bestbuy`| Service to manage products for Best Buy        | [product-service-bestbuy](https://github.com/Serpil-Dndr/product-service-best-buy.git) |
| `order-service-bestbuy`  | Service to handle orders for Best Buy          | [order-service-bestbuy](https://github.com/Serpil-Dndr/order-service-best-buy.git) |
| `store-admin-bestbuy`    | Admin interface to manage Best Buy products    | [store-admin-bestbuy](https://github.com/Serpil-Dndr/store-admin-best-buy.git) |
| `ai-service-bestbuy`     | AI service to generate product descriptions and images | [ai-service-bestbuy](https://github.com/Serpil-Dndr/ai-service-best-buy.git) |
| `makeline-service-bestbuy`| Service to manage product assembly lines for Best Buy | [makeline-service-bestbuy](https://github.com/Serpil-Dndr/makeline-service-best-buy.git) |
| `virtual-customer-bestbuy`| Simulates virtual customer interactions for testing | [virtual-customer-bestbuy](https://github.com/Serpil-Dndr/virtual-customer-best-buy.git) |
| `virtual-worker-bestbuy` | Service to simulate virtual workers for Best Buy testing | [virtual-worker-bestbuy](https://github.com/Serpil-Dndr/virtual-worker-best-buy.git) |



## Docker Images Table

A table listing all Docker images you created, including their names and links to their Docker Hub repositories.

| Service               | Docker Image Link                                                    |
|-----------------------|----------------------------------------------------------------------|
| Store-Front           | [https://hub.docker.com/repository/docker/serpild/store-front-l8/general](https://hub.docker.com/repository/docker/serpild/store-front-l8/general) |
| Order-Service         | [https://hub.docker.com/repository/docker/serpild/order-service-l8/general](https://hub.docker.com/repository/docker/serpild/order-service-l8/general) |
| Product-Service       | [https://hub.docker.com/repository/docker/serpild/product-service-l8/general](https://hub.docker.com/repository/docker/serpild/product-service-l8/general) |
| Makeline-Service      | [https://hub.docker.com/repository/docker/serpild/makeline-service-l8/general](https://hub.docker.com/repository/docker/serpild/makeline-service-l8/general) |
| Store-Admin           | [https://hub.docker.com/repository/docker/serpild/store-admin-l8/general](https://hub.docker.com/repository/docker/serpild/store-admin-l8/general) |
| AI-Service            | [https://hub.docker.com/repository/docker/serpild/ai-service-l8/general](https://hub.docker.com/repository/docker/serpild/ai-service-l8/general) |




