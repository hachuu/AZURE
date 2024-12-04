# AZ-204 : Implement Azure Functions

## Explore Azure Functions

### Introduction

- Azure Functions : develop serverless applications
- be able to
  - Azure Functions, Azure Logic Apps, WebJobs의 차이점 설명
  - Azure Functions hosting plan options
  - 비즈니스 요구에 따른 Azure Functions scaling

### Discover Azure Function
- Serverless solution
- 장점
  - maintain less infrastructure
  - save on costs
  - Instead of worring about developing and maintaining server
  - cloud infrastructure provides up-to-date resources
- 제공
  - triggers : start execution of a code
  - bindings : simplify coding for input and output data

### Compare Azure Functions and Azure Logic Apps
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


### Compare Functions and WebJobs
- 차이
  - Azure Functions이 Azure App Service WebJobs보다 developer productivity를 제공함
| **Factor**                                   | **Functions**                                                                                                           | **WebJobs with WebJobs SDK**                                                                                   |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| **Serverless app model with automatic scaling** | Yes                                                                                                                    | No                                                                                                            |
| **Develop and test in browser**             | Yes                                                                                                                    | No                                                                                                            |
| **Pay-per-use pricing**                     | Yes                                                                                                                    | No                                                                                                            |
| **Integration with Logic Apps**             | Yes                                                                                                                    | No                                                                                                            |
| **Trigger events**                          | - Timer <br> - Azure Storage queues and blobs <br> - Azure Service Bus queues and topics <br> - Azure Cosmos DB <br> - Azure Event Hubs <br> - HTTP/WebHook (GitHub, Slack) <br> - Azure Event Grid | - Timer <br> - Azure Storage queues and blobs <br> - Azure Service Bus queues and topics <br> - Azure Cosmos DB <br> - Azure Event Hubs <br> - File system |


### hosting options
- Consumption plan
  - default
  - automatic scale
  - pay-as-you-go (유휴상태 비용 없음)
- Flex Consumption plan
  - incoming events에 따른 automatic scale
- Premium plan
  - continuously, function apps
  - deploy multiple function apps on the same plan with event-driven scaling.
  - high number of small executions & high execution bill, but low GB seconds
  - require virtual network connectivity
  - custom Linux image to run your functions
- Dedicated plan
  - fully predictable billing or manually sacle istances
  - run multiple web apps and function apps on the same plan
  - access to larger compute size choices
  - full compute isolation, secure network access by App Service Environment(ASE)
  - High memory usage & high scale(ASE)
- Container Apps
  - fully managed environment hosted by Azure Container Apps
  - package custom libraries
  - migration code from on-premises or legacy to cloud native microservices
  - avoid the overhead and complexity of managing Kubernetes clusters dedicated compute
  - high-end processing power by dedicated CPU compute resources

### Scale Azure Functions
- scaling behaviors of the various hosting plans
| **Plan**               | **Scale out**                                                                                             | **Max # instances**                     |
|------------------------|----------------------------------------------------------------------------------------------------------|-----------------------------------------|
| **Consumption plan**    | 이벤트 기반. 높은 부하가 있을 때에도 자동으로 확장됨. 트리거 이벤트 수에 따라 CPU 및 메모리 자원을 확장하며, 인스턴스를 추가함.   | Windows: 200<br>Linux: 100           |
| **Flex Consumption plan**| 함수별 확장. 이벤트 기반 확장 결정이 함수별로 계산되어, 함수 확장 방식을 더 결정적으로 제공.                     | 주어진 지역 내 모든 인스턴스의 총 메모리 사용량에 의해 제한됨. |
| **Premium plan**        | 이벤트 기반. 함수가 트리거되는 이벤트 수에 따라 자동으로 확장됨.                                        | Windows: 100<br>Linux: 20-100         |
| **Dedicated plan**      | 수동/자동 확장                                                                                           | 10-30 (ASE: 100)                       |
| **Container Apps**      | 이벤트 기반. 함수가 트리거되는 이벤트 수에 따라 Functions 호스트 인스턴스를 추가하여 자동으로 확장됨.                   | 10-300                                 |

- Consumption plan에서 Linux 앱은 시간당 구독당 500개의 인스턴스로 제한됩니다.
- Premium plan에서는 일부 지역에서 Linux 앱이 최대 100개 인스턴스로 확장될 수 있습니다.
- Container Apps에서는 사용할 수 있는 코어 수가 충분하면 최대 복제본 수를 설정할 수 있습니다. 


## Develop Azure Functions

### Introduction

- Azure Functions : functions share a few core technical concepts and components
- concepts
  - key components of a function
  - create triggers and bindings
  - connect a function to services in Azure
  - create a function by Visual Studio Code and Azure Functions Core Tools

### Explore Azure Functions development

- Explore Azure Functions development
  - function app share the same pricing plan, deployment method, and runtime version
- Develop and test Azure Functions locally
  - [Code and test Azure Functions locally](https://learn.microsoft.com/en-us/azure/azure-functions/functions-develop-local)
- Local project files
  - host.json => affect all functions in a function app instance
  - local.settings.json => Only your running project on local computer

### Create triggers and bindings
