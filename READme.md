# Cloud-Native App for Best Buy
Welcome to the **Best Buy Store ** application.

This sample demo app consists of a group of containerized microservices that can be easily deployed into a Kubernetes cluster. It demonstrates a realistic scenario using a polyglot architecture, event-driven design, and common open-source back-end services (e.g., RabbitMQ, MongoDB). The application also integrates OpenAI's models to generate product descriptions and recommendations. This functionality can utilize either [Azure OpenAI](https://learn.microsoft.com/azure/ai-services/openai/overview) or [OpenAI](https://openai.com/).

This application is inspired by Azure Kubernetes Service (AKS) quickstart demo [Azure Kubernetes Service (AKS) Docs](https://learn.microsoft.com/en-us/azure/aks/).

> [!NOTE]
> This is not intended as an example of production-ready code but rather a demonstration of a realistic application running in Kubernetes.

---

## Architecture
## Architecture

The application has the following services: 
| Service                 | Description                                    | Github Repo                                                      |
|-------------------------|------------------------------------------------|-------------------------------------------------------------------|
| `store-front-bestbuy`    | Web app for customers to place orders (Vue.js) | [store-front-bestbuy](https://github.com/Serpil-Dndr/store-front-bestbuy.git) |
| `product-service-bestbuy`| Service to manage products for Best Buy        | [product-service-bestbuy](https://github.com/Serpil-Dndr/product-service-bestbuy.git) |
