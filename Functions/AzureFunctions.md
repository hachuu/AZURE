# AZ-204 : Implement Azure Functions


## Introduction

- Azure Functions : develop serverless applications
- be able to
  - Azure Functions, Azure Logic Apps, WebJobs의 차이점 설명
  - Azure Functions hosting plan options
  - 비즈니스 요구에 따른 Azure Functions scaling

## Discover Azure Function
- Serverless solution
- 장점
  - maintain less infrastructure
  - save on costs
  - Instead of worring about developing and maintaining server
  - cloud infrastructure provides up-to-date resources
- 제공
  - triggers : start execution of a code
  - bindings : simplify coding for input and output data

## Compare Azure Functions and Azure Logic Apps
- 공통
  - Serverless workloads
  - create orchestrations (collection of functions or steps)
- 차이
  - Azure Functions : serverless compute service
  - Azure Logic Apps : serverless workflow integration platform
| **Topic**           | **Azure Functions**                                      | **Logic Apps**                                                                                  |
|----------------------|---------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| **Development**      | Code-first (imperative)                                 | Designer-first (declarative)                                                                    |
| **Connectivity**     | About a dozen built-in binding types, write code for custom bindings | Large collection of connectors, Enterprise Integration Pack for B2B scenarios, build custom connectors |
| **Actions**          | Each activity is an Azure function; write code for activity functions | Large collection of ready-made actions                                                         |
| **Monitoring**       | Azure Application Insights                              | Azure portal, Azure Monitor logs                                                               |
| **Management**       | REST API, Visual Studio                                 | Azure portal, REST API, PowerShell, Visual Studio                                              |
| **Execution context**| Runs in Azure, or locally                               | Runs in Azure, locally, or on premises                                                         |


## Compare Functions and WebJobs
- 차이
  - Azure Functions이 Azure App Service WebJobs보다 developer productivity를 제공함
| **Factor**                                   | **Functions**                                                                                                           | **WebJobs with WebJobs SDK**                                                                                   |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| **Serverless app model with automatic scaling** | Yes                                                                                                                    | No                                                                                                            |
| **Develop and test in browser**             | Yes                                                                                                                    | No                                                                                                            |
| **Pay-per-use pricing**                     | Yes                                                                                                                    | No                                                                                                            |
| **Integration with Logic Apps**             | Yes                                                                                                                    | No                                                                                                            |
| **Trigger events**                          | - Timer <br> - Azure Storage queues and blobs <br> - Azure Service Bus queues and topics <br> - Azure Cosmos DB <br> - Azure Event Hubs <br> - HTTP/WebHook (GitHub, Slack) <br> - Azure Event Grid | - Timer <br> - Azure Storage queues and blobs <br> - Azure Service Bus queues and topics <br> - Azure Cosmos DB <br> - Azure Event Hubs <br> - File system |


## hosting options
- Consumption plan
  - default
  - automatic scale
  - pay-as-you-go (유휴상태 비용 없음)
- Flex Consumption plan
- Premium plan
- Dedicated plan