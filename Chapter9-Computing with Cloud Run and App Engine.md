# Overview of Cloud Run
- A serverless, managed service for running containerized applications : support any applicaiton that can be runned in a container
- No limitation of programming language
- Do not nned to manage infrastructure
- Running as job or service

## Cloud Run Service
- when code is responding to web requests or events: an API returnning data from a cloud SQL database
- suitable for web applications, microservices, APIs, and stream data processing
- designed to listen to an HTTPS endpoint and respond to requests made to that end point

**Endpoint**
***An endpoint in the context of Cloud Run refers to the URL that clients can use to access your application once it's deployed. When you deploy your containerized application to Cloud Run, Google Cloud automatically assigns a unique URL to it, which serves as the endpoint. This URL typically looks like https://SERVICE_NAME-PROJECT_ID.run.app, where SERVICE_NAME is the name of your Cloud Run service and PROJECT_ID is your Google Cloud project ID.***

***Once your application is deployed and the endpoint is generated, clients can send HTTP requests to this URL to interact with your application. For example, if you have a RESTful API deployed on Cloud Run, clients can make HTTP GET, POST, PUT, DELETE, etc., requests to the endpoint URL to retrieve data, create resources, update data, or delete resources, respectively.***

## Cloud Run Jobs
- code executes untill a workload is complete: transform a set of files stored in cloud storage and then load it inot cloud sql
- unlike a service, which continues to accespt requests to perform tasks, hobs perfomr a task and terminate
**Revision and new Version**

***In the context of Google Cloud Run, a "revision" refers to a specific deployment of your containerized application. Each time you deploy a new version of your application to Cloud Run, it creates a new revision.***

***A revision is essentially a snapshot of your application code and configuration at a particular point in time. It includes everything needed to run your application, such as the Docker image containing your code, environment variables, resource limits, and any other settings specified during deployment***

***When you deploy a new version of your application to Cloud Run, it creates a new revision and automatically routes incoming traffic to it. However, you can also manually specify which revision should receive traffic using traffic splitting configurations.***


# Creating a cloud run service
- using console, cloud SDK, or programmatically using the API

# Creating a cloud run job

# App Engine Components
***Cloud Run allows you to run containerized applications, meaning you package your application and its dependencies into Docker containers. App Engine, on the other hand, supports multiple environments, including a flexible environment that also allows you to deploy containerized applications, but it also supports traditional "standard" and "flexible" environments where you deploy your code without containerization.***

- App engine is availbale in standard and a flexible version
- Application, service, verison, instance
- High level resource created in a project, each project can have one app engine application
- App have at least one service, which is the ocde executed in the app engine env.
- Multiple version of an app exist and app engine supports versioning of apps
- When a new version of an application executes, it creates an instance of an app
**Microservices**
***Services are typically structured to perform a single function with complex applications made up of multiple services. Services are defined by the source code and the configuration file. the conbo of those files constitute a vertsion of the app***

# Deploying an app engine application

## Deploying an app using cloud shell and sdk

# Scaling app engine applications
- When instances are scaled based on load,they are called dynamic instances

# Spliting Traffic between app engine versions
