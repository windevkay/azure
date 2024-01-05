[Documentation](https://learn.microsoft.com/en-us/training/paths/az-204-implement-iaas-solutions/)

## AZURE CONTAINER REGISTRY

Use the Azure Container Registry (ACR) service with your existing container development and deployment pipelines, or use Azure Container Registry Tasks to build container images in Azure. Build on demand, or fully automate builds with triggers such as source code commits and base image updates.

**USES**

- Push existing container images from an external development workflow.
- Automate the build of containers on demand, triggered by new commits or change in base image.
- Can work together with other systems and services such as kubernetes and azure services such as azure kubernetes service, app service etc.

ACR tiers include Basic, Standard and Premuim (which all benefit from encryption at rest). Each successive tier has higher storage and image throughput. ACR can also store other items including Helm charts. ACR supports both linux and windows based images.

[Build and run an image with ACR Tasks](https://learn.microsoft.com/en-us/training/modules/publish-container-image-to-azure-container-registry/6-build-run-image-azure-container-registry)

## AZURE CONTAINER INSTANCES

ACI provides an optimzed way to run already existing images as a container. [Deploying a container using the Azure CLI](https://learn.microsoft.com/en-us/training/modules/create-run-container-images-azure-container-instances/3-run-azure-container-instances-cloud-shell)

## AZURE CONTAINER APPS

Azure Container Apps provides the flexibility you need with a serverless container service built for microservice applications and robust autoscaling capabilities without the overhead of managing complex infrastructure.
[Deploying a container app](https://learn.microsoft.com/en-us/training/modules/implement-azure-container-apps/3-exercise-deploy-app)
