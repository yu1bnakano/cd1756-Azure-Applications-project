# Write-up

## Choosing an Azure Resource
When deciding between deploying the CMS app using Azure VMs or Azure App Service, it’s important to weigh the trade-offs across cost, scalability, availability, and workflow. Both options are feasible, but the better choice depends on the existing architecture (if there's any), team expertise, and future growth expectations.

## Virtual Machine (VM) vs. App Service

VM - Is a type of cloud computing service (IaaS) that provide full access to a compute resource, which can either be a Windows or Linux machines. VM's are hhighly available, and scalable. Also, VM's are highly customizable too, which could be preferred for specific usecases. Although, these require more on-going maintenance and up-keep by cloud developers.

App Service - An Azure Platform as a Service (PaaS) is a type of cloud computing service that allow developers to focus more on their apps than the underlying infrastructure i.e Azure takes care of the infrastructure. It is an HTTP-based service for hosting web applications, REST APIs, and mobile back ends. It supports multiple languages and continuous deployment.

### Cost:
App service  offers flexible pricing tiers and built-in load balancing that reduces infrastructure overhead. Also, it is designed to scale dynamically and can be configured to scale down during idle times. Here you pay only for the resources your app actually uses, especially in consumption or shared plans.

VM's, on the other hand, typically runs continuously unless you explicitly stop or deallocate it. Thus, it could incur higher costs due to continuous resource consumption—even when idle. 

### Scalability:

App Service supports both vertical and horizontal scaling with minimal effort. Developers can scale up by changing pricing tiers or by increasing instance counts.

VMs likewise can be scaled vertically and horizontally. Spinning up new VMs can take minutes, which may not be ideal for sudden traffic spikes.

### Availability:

App Service benefits from Microsoft’s global datacenter infrastructure and comes with a high availability SLA. It allows developers to deploy apps closer to users and ensures uptime without needing to manage the underlying infrastructure

### Workflow:

App Service streamlines deployment workflows with built-in CI/CD integrations for GitHub, ADO , and other repositories. Developers can automate build, test, and deployment pipelines with ease. 

VMs, on the other hand, require manual setup of the environment, including OS, middleware, and runtime libraries, which can slow down deployment cycles.

## Recommended Solution: Azure App Service
Given the CMS app’s current state and the need for a fast, and scalable deployment, Azure App Service is the more appropriate choice. It allows the development team to focus on building and improving the app rather than managing infrastructure. The app is already written in a supported language and the team does not require control over the underlying OS or custom server configurations at this stage.

The justification for choosing Azure App Service lies in its ability to significantly reduce operational overhead. With App Service, there is no need to manage operating system updates, apply security patches, or configure server infrastructure, allowing teams to focus more on development. Additionally, App Service offers built-in scalability and high availability, enabling the application to handle traffic spikes and maintain uptime without manual intervention. From a financial perspective, it is cost-efficient, offering a pay-as-you-go model that allows organizations to start small and scale resources as demand increases.

While Azure App Service is currently the ideal choice for deploying the CMS application, there are specific scenarios where transitioning to Virtual Machines would be appropriate. If the application eventually requires a custom operating system or the installation of specialized software that App Service does not support, VMs would offer the necessary control over the environment. Similarly, if the app is rewritten in a programming language that is not supported by App Service, deploying it on a VM would be the only viable option. In cases where the application evolves to handle high performance or resource heavy workloads, VMs would be better suited to meet those demands.
