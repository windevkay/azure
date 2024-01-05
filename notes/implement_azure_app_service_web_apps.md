[Documentation](https://learn.microsoft.com/en-us/training/paths/create-azure-app-service-web-apps/)

# AZURE APP SERVICE

- HTTP based, capable of running apps in both windows and linux environments
- Auto scaling support. Scale up/down (RAM, more cores) or in/out (machine instances)
- CI/CD via Azure Devops in Azure Portal
- Deployment slots - Standard Tier and above can deploy to slots other than prod
- On a Shared Pricing Tier - linux isnt available

## AZURE APP SERVICE PLANS

- An app service is a provisioned compute resource that can run one or more apps
- App service plans define an OS, Region, # of VM's, size of VM instances and pricing tier

#### APP SERVICE TIERS

- _Shared Compute: (Free and Shared)_ - Apps run on VM's shared with other apps from other customers on same plan. Scaling out is disabled
- _Dedicated Compute: (Basic, Standard, Premium, PremiumV2, PremiumV3)_ - Apps run on dedicated VM's. Available scale out instances increase the higher the tier.
- _Isolated: (Isolated, IsolatedV2)_ - Run on dedicated VM's on dedicated Azure Virtual Networks - providing network isolation. Maximum scale out.

_note - (in the non-shared compute plans) deployed apps, deployment slots, webjobs etc, and autoscaling is applied across all vm's. Shared and dedicated compute tiers are under the Multitenant service while Isolated tier is under the Single Tenant service_

## DEPLOYMENTS

App service supports both manual and automated deployments. Automated - Azure Devops, GitHub, Bitbucket. Manual - Git, CLI, FTP/S

## OTHER CORE APP SERVICE FEATURES

- **Out of the box authentication and authorization** with multiple OAuth providers (and in-built Token Store). Can be managed with Azure Resource Manager. Auth module runs in same sandbox as code except for in linux containers (where they run as a separate container)
- **Networking and request route handling** - Important for Multitenant skews - _INBOUND TRAFFIC_: App-assigned addresses, access restrictions, service endpoints, private endpoints. _OUTBOUND TRAFFIC_: Hybrid Connections, Virtual network integration, Gateway-required virtual network integration

## CONFIGS IN APP SERVICE

- Application (ENV VAR) settings
- General settings
- Path Mappings
- [Logging](https://learn.microsoft.com/en-us/training/modules/configure-web-app-settings/5-enable-diagnostic-logging)
- Security certificates

## AUTOSCALING

Autoscaling provides elasticity by enabling a scale out of your app service based on scaling conditions configured by you. You can either scale based on a metric or scale to a specific instance count on a schedule or a combination of both. Autoscaling by metrics involves monitoring the matrics of certain rules which can include:

- CPU PERCENTAGE
- MEMORY PERCENTAGE
- DISK QUEUE LENGTH
- HTTP QUEUE LENGTH
- DATA IN AND DATA OUT

## DEPLOYMENT SLOTS

Slot swaps allow for the deployment of apps into a non prod environment such as staging. It ensures the staging slot is warmed up prior to the swap to ensure the target slot (production) doesnt experience downtime. Swaps can be:

- Manual swap - Done manually within the azure portal by specifying source and target
- Swap with Preview - Same as manual but with an intermediate step to verify the changes being copied over in staging
- Auto swap - Streamline releases made in azure devops to the slots with zero cold starts and zero downtime

During a swap, certain settings are copied over from target to source to ensure they work as expected. [Details here](https://learn.microsoft.com/en-us/training/modules/understand-app-service-deployment-slots/3-app-service-slot-swapping)

**ROUTING**

With azure app service, you can configure a % of traffic to go to a specific slot automatically. You can do it manually by for example allowing your users chose a setting on the frontend. Both approaches will use a cookie on the FE to control where requests get routed to.
