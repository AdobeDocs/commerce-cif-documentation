# Commerce Integration Framework Introduction

Adobe’s Commerce Integration Framework (CIF) vision is to enable Adobe customers to build and deliver extraordinary and personalized omnichannel shopping experience based on state-of-the-art technology.

## Principles

The CIF provides you with adaptable Commerce business processes that are exposed as microservices:

*  Microservices are small, modular services that provide a specific business function.  

*  Easily developed and customized to complex support omnichannel scenarios and quickly adapt to changing market conditions. 

*  Reduces the time, cost, and complexity of supporting complex omnichannel commerce scenarios.


## CIF Benefits

The main benefits are: 

1. The integration is an abstraction layer to standardize and encapsulate integrations with multiple systems. It provides a flexible and re-usable customization for every service.

2. The extension is a serverless, microservice-based process and business logic layer that allows you to customize and extend commerce services.

3. CIF supports headless/omnichannel experiences:
    * Single Page applications and Multipe Pages Applications
    * GraphQL endpoints
    
4. CIF provides bi-directional integrations with the Experience Cloud. That means integrated SDKs to leverage the power of Adobe's services and solutions, as well as out-of-the-box integrations with Adobe solutions such as Campaign, and AEM.


## CIF on Adobe I/O Runtime

The CIF on Adobe I/O Runtime enables two use-cases: 1. 3rd party integrations via microservice layer and 2. Extensibility of microservices. This architecture is based on [OpenWhisk](https://openwhisk.apache.org) & [Adobe I/O Runtime](https://www.adobe.io/apis/cloudplatform/runtime.html). The main building blocks of the commerce services are serverless functions (OpenWhisk actions). These actions run on Adobe I/O Runtime inside an isolated container, stateless and serverless interacting with the commerce backend system or other endpoints via their APIs. 

This will be available later in 2019.

## CIF Elements

This list presents the main CIF elements:

#### AEM CIF Cloud Connector
The connector connects AEM with CIF Cloud GraphQL endpoint. It allows AEM to access and exchange commerce data via GraphQL.

#### AEM Venia Storefront
This is the storefront accelerator for AEM (Author, Preview, Deploy). It supports Adobe Commerce GraphQL endpoints and works with AEM core components and client-side commerce components.
It is a reference store-front and allows you to kickstart projects to quickly build a standard storefront based on AEM technologies.

#### AEM Components

The AEM components are server-side rendered components with Magento GraphQL support. They're used to create static, cacheable and SEO-friendly content based on AEM technologies.

#### Web Components

The Web Components are ReactJS components rendered client-side with Adobe Commerce GraphQL support. There is an AEM wrapper to enable component authoring and configuration. They allow you to create dynamic components, such as shopping cart and search.

#### CIF Extension Layer

The CIF extension layer runs on a serverless I/O Runtime architecture. It allows you to extend end-to-end service calls by injecting business and process logic on a microservice level. Business logic would be for example to use location and channel to determine an inventory strategy. Process logic would be for example to retrieve personalized information.

#### CIF Integration Layer

The CIF integration layer runs on a serverless I/O Runtime architecture. It standardizes third party solution integrations on a microservice level to encapsulate third party commerce solutions by mapping third party APIs against the Adobe Commerce APIs. This allows you to use AEM tools, multiple page authoring and components out-of-the-box.

#### Campaign Integration

The [Campaign integration](https://github.com/adobe/commerce-cif-cart-abandonment) provided extensible microservices on I/O Runtime that enriches *cart abandonment* events with live data before calling Campaign. It calls Magento to get cart details and calls Campaign's APIs to provide data.
