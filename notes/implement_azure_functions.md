[Documentation](https://learn.microsoft.com/en-us/training/paths/implement-azure-functions/)

# AZURE FUNCTIONS

Azure functions are a serverless solution. They support triggers (for code execution) and bindings (to simplify input and output data). Azure functions are used for serverless compute while Azure logic apps are used for serverless workflow integrations.Azure Functions offers more developer productivity than Azure App Service WebJobs does.

**HOSTING**

Azure functions can be hosted on either a Consumption, Premium or Dedicated plan.

- Consumption plan - Pay only when compute resources run. Automatic scaling
- Premium plan - Same as consumption but with pre-warmed workers to enable less latency
- Dedicated plan - Pricing is based on regular app service plans due to long running nature of the functions

On any plan, a function app requires a general Azure Storage account, which supports Azure Blob, Queue, Files, and Table storage. This is because Functions rely on Azure Storage for operations such as managing triggers and logging function executions, but some storage accounts don't support queues and tables.

Azure Functions uses a component called the scale controller to monitor the rate of events and determine whether to scale out or scale in. The scale controller uses heuristics for each trigger type. For example, when you're using an Azure Queue storage trigger, it scales based on the queue length and the age of the oldest queue message.

The unit of scale for Azure Functions is the function app. When the function app is scaled out, more resources are allocated to run multiple instances of the Azure Functions host. Conversely, as compute demand is reduced, the scale controller removes function host instances. The number of instances is eventually "scaled in" to zero when no functions are running within a function app.

[Practical](https://learn.microsoft.com/en-us/training/modules/develop-azure-functions/1-introduction)
