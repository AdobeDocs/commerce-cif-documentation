
# Commerce Integration Framework GitHub Release Overview

## Overview of Sytem Requirements

Review the minimum system requirements in the table below for the CIF version you are currently using or plan to use in the future.

|GitHub| System Requirements| 
|:-------|:-----:|
|CIF Connector |[System Requirements](https://github.com/adobe/commerce-cif-connector/blob/master/VERSIONS.md)|
|CIF Core Components |[System Requirements](https://github.com/adobe/aem-core-cif-components/blob/master/VERSIONS.md)|
|AEM Project Archetype |[System Requirements](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)|

## Release Notes

#### Release Date: March, 2021

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.9.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.10.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Venia Reference Site| 2021.03.25|[Release Notes](https://github.com/adobe/aem-cif-guides-venia/releases)|

### What's new

**Features**
* Support for Magento 2.4.2

### What's improved
* Improved re-usability of product detail component for content driven pages

* Better caching and less backend calls for PDPs

* Multiple bug fixes.

***

#### Release Date: February, 2021

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.8.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.8.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Venia Reference Site| 2021.02.24|[Release Notes](https://github.com/adobe/aem-cif-guides-venia/releases)|

### What's new

**Features**
* Product Experience Management: Enrich product catalog pages individually with Experience Fragments.

* Extended product console properties to show linked Assets and Experience Fragments, including action to quickly navigaet to the associated content.

### What's improved
* Enhanced client-side data layer with product image url and cateogry information

* Multiple bug fixes.

***

#### Release Date: January, 2021

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.7.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.7.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Venia Reference Site| 2021.02.02|[Release Notes](https://github.com/adobe/aem-cif-guides-venia/releases)|

### What's new

**Features**
* Product Experience Management: New 'Commerce' property tab for Assets and Experience Fragments. This tab enables you to link Assets and Experience Fragments to products & categories. The tab also shows real-time data for linked commerce objects and a link to show details in the product console.

### What's improved
* Send user data after authentication to Adobe Client Data Layer.

* Multiple bug fixes.

***

#### Release Date: November, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.6.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.6.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Venia Reference Site| 2020.12.01|[Release Notes](https://github.com/adobe/aem-cif-guides-venia/releases)|

### What's new

**Features**
* Template inheritance added to specific category page. This feature improves business user efficiency because it makes it possible for all sub-categories to inherit the template that was created for a specific top category.

* Venia reference storefront updated to use Experience Fragment for the footer. Business users have the ability to edit  the page footer using AEM authoring tools.

### What's improved
* Checkout component improved to provide shoppers with the ability to enter destination country to allow billing/shipping addresses outside the United States.

* Navigation component extended to hydrate Adobe Client Data Layer.

* Multiple bug fixes.

***

#### Release Date: October, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.5.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.5.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Venia Reference Site| 2020.10.27|[Release Notes](https://github.com/adobe/aem-cif-guides-venia/releases)|

### What's new

**Features**
* New Category carousel component added to enable business users to drag and drop this component on AEM content pages to enrich content pages with commerce data.

* CIF core components extended to hydrate the Adobe Client Data Layer by sending commerce data. The Adobe Client Data Layer is a standardized method to collect data and communicate the data to digital analytics and reporting servers. For more details, refer to [Adobe Client Data Layer](https://github.com/adobe/adobe-client-data-layer/wiki).

### What's improved
* Product Detail and Product List pages extended to automatically populate SEO metadata (e.g. title, meta description, meta keywords) configured from within the Magento admin UI

* Commerce teaser component bug fixed.

***


#### Release Date: September, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.4.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.4.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Venia Reference Site| 2020.10.2|[Release Notes](https://github.com/adobe/aem-cif-guides-venia/releases)|

### What's new

**Features**
* Supports queries for Magento 2.4.0 Schema.

* Account information features added to allow shoppers to update personal information.

* Lazy loading pagination style implemented for Product list and Search results pages to allow developers to configure these components to display "Load more" button as the pagination style.

* Password reset page implemented to allow shoppers to be able to update/reset their account password.

* Support for Bundled products types available.


### What's improved
* Developers can configure the HTML tags for Product Carousel, Related Products, and Featured Category List components to follow SEO best practices.

* My Account bugs fixed. 

* Multiple bug fixes.

***


#### Release Date: August, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.3.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.3.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Venia Reference Site| 2020.9.2|[Release Notes](https://github.com/adobe/aem-cif-guides-venia/releases)|

### What's new

**Features**
* Breadcrumb component added to support content and commerce pages.

* Commerce tab added on Page properties to expose CIF properties for Landing Page and Experience Fragments.


### What's improved
* Searchbar component improved to support option to display placeholder text

* Added flexibility to Product and Product Teaser components to support easy customizations.

* Added flexibility to override and configure default CTA button label for Product Teaser component.

* Address Book component improved to allow registered shopper to choose shipping and billing addresses saved in the addreess book during checkout.

* Multiple bug fixes.

***


#### Release Date: July, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.2.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.2.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Venia Reference Site| 2020.8.14|[Release Notes](https://github.com/adobe/aem-cif-guides-venia/releases)|

### What's new
* CIF Venia Reference Site was extracted from the CIF Archetype repo and is now a standalone GitHub repository. 

* CIF Archetype merged with AEM Project Archetype. For new projects, use [AEM Project Archetype](https://github.com/adobe/aem-project-archetype) as the starting point.

**Features**
* Address book management added to allow signed-in users to manage their addresses.

* CIF Cloud Configuration UI supports publish/unpublish actions.

### What's improved
* Sign-in component moved to user drop-down for easy access.

* Simplified the aem-core-cif-react-components package.

* Multiple bug fixes.

***

#### Release Date: June, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.1.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.1.1|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.11.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|

### What's new
This is the 1st version of CIF Core Components that is supported on Adobe Experience Manager Cloud Service.

**Features**
* Added product sorting on Product List page and Search Results page to allow shoppers to sort based on relevance, price, and product name.

* Added category filtering as a facet to allow shoppers to filter based on category.

* Added service user mapping as part of security requirement to ensure access to /conf via service users and not by directly manipulating ACLs. CIF Core Components now must use a service user to access configurations.

### What's improved
* Product List page and Search Result page display total number of items. Number of items is updated when shopper applied filters.

* Faceted search optimized by combining category query with product search query.

* Category/Product pickers for page preview honor cq:catalogPath.

* Multiple bug fixes.

***


#### Release Date: May, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 1.0.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |1.0.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.11.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|


### What's new

**Features**
* Supports queries for Magento 2.3.5 Schema.

* Faceted Search support added to Search Page and Product List Page to allow shoppers to filter search results based on Product facets.

* New OSGi service added to customize PDP/PLP URLs for SEO purposed. For more details, refer to this [documentation](https://github.com/adobe/aem-core-cif-components/wiki/configuration).

* Product Binding automatically created when a Cloud Configuration is created.


### What's improved
* Cloud Configration extended to display "Create Folder" action.

* Multiple bug fixes applied.


***


#### Release Date: April, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.10.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.10.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.10.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|


### What's new

**Features**
* Configuration settings for CIF Connector unified and simplified. For more details checkout [Getting Started](https://www.adobe.io/apis/experiencecloud/commerce-integration-framework/getting-started.html) or [New AEM CIF Project Setup](https://www.adobe.io/apis/experiencecloud/commerce-integration-framework/getting-started.html#!AdobeDocs/commerce-cif-documentation/master/getting-started/02-new-cif-project.md)


### What's improved
* Shopping cart and checkout flow extended to support registered shoppers.

* Extended internationalization support across all components.

* Support for Grouped Products and Virtual Products available.

* Related Products, Product Carousel, and Featured Category components improved to support optional title.

* Multiple bug fixes applied.


***


#### Release Date: February, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.9.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.9.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.9.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|


### What's new

**Features**
* Supports queries for Magento 2.3.4 Schema.

* Added search support in Category Picker.

* Pagination in Catogory List component to support large catalog sets.


### What's improved
* Shopping cart enhanced to display discounts.

* Product Detail, Product Teaser and Product List components support display of advanced pricing information.

* Product search in Product Console and Product Picker improved.

* Multiple bug fixes applied.


***

#### Release Date: January, 2020

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.8.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.8.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.7.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|


### What's new

**Features**
* Experience Fragment (XF) component added to enable customers to create XF in their commerce project.


**Components**
* Change password functionality available in my account.

* i18n support for AEM CIF server-side core components.

* Generic related product component available.


### What's improved
* Support to display CTA button on product teaser.

* Option to change/select images in the Featured Category List component.

* Option to hide/display title/banner in the Product List component.

* Drag and drop feature applied to Prodcut Carousel component.

* Multiple bug fixes applied.


***



#### Release Date: November, 2019

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.7.1|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.6.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.6.2|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|


### What's new

**Features**
* Authors can preview product detail and product list pages with products/categories with a new "View with product/category" option in the Sites editor.

* Authors can tag assets by product SKU and search for product-specific assets by SKU. 


**Components**
* Add/remove coupon support added in shopping cart.

* Braintree payment support added in AEM Venia store front.


### What's improved
* Category/Product pickers enhanced to respect specified Magento store view in a multi-store setup.

* React-based components available as a npm package. This allows developers to use the React Components package as a dependency for a new React project to allow customization of existing components or develop new React-based components.

* GraphQL query customization simplified. This allows developers to customize CIF core components with less code.


***



#### Release Date: October, 2019

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.6.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.5.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.5.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|


### What's new

**Features**
* Fully authorable templates for product detail page and product list page. Authors can now create new templates and drag and drop product list and product detail components on these templates. In addition to adding other components, authors can now change the layout of these templates too, giving them unlimited freedom to create amazing experiences combining marketing and commerce content. 

* All author-friendly CIF core-components have been enhanced to support [AEM's Style System](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html). Example styles have been provided for the product list component.


**Components**
* React-based client-side components for account management. This release supports the following functionalities: Sign In, Forgot Password, and Create Account.


### What's improved
* Product detail and product list components have been enhanced to show dummy data to provide authors with a preview of the layout when these components are placed on a template/page.

* Minicart and Checkout components now use React hooks for improved extensibility.

***


#### Release Date: September, 2019

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.5.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.4.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.4.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|


### What's new

**Features**
* Multi-template feature to allow authors to enrich specific product detail page or product list page. Authors can easily create a custom product detail page or product list page and use the product or category picker to assign the custom page to a specific product(s) or category(s).

* Multi-catalog binding to allow authors to bind multiple catalogs in the AEM product console. Authors can also edit and view the catalog binding properties after creating the binding.


**Components**
* React-based client-side Checkout and Mini Cart using GraphQL to support a complete basic shopping journey.

* Checkout component includes address forms, payment selection, and shipping method selection.


### What's improved
* Product Teaser and Product Carousel components support product variants.

***


#### Release Date: August, 2019

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.4.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.3.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.3.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|

### What's new

**Features**
* Embedding CIF Connector in CIF Archetype made optional to provide developers more flexibility.  

* CIF Components decoupled from "Venia" specific CSS styling to allow developers to apply CSS styling of their choice.

* Multi-store/site feature to allow use of CIF Core Components on multiple AEM site structures and enabling the underlying GraphQL client implementation to connect to different Magento store/store views.

* GraphQL caching enabled for certain GraphQL queries via HTTP GET to reduce response time.

* Product description view enabled in AEM Products console.


**Components**
* Commerce Teaser extends WCM Teaser component to allow authors to also add CTA fields to a product detail page or a product list page.

* Button to allow authors to place on an AEM page and link to either an AEM page, product detail page, product list page, or an external link.


### What's improved
* Magento store configuration moved from OSGi to AEM Product console to make the integration setup more author-friendly.

***

#### Release Date: July, 2019

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.3.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.2.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|
|CIF Archetype |0.2.0|[Release Notes](https://github.com/adobe/aem-cif-project-archetype/releases)|

### What's new

#### Features
* First CIF Archetype to provide developers with several deployment options: 1.Deploy AEM Venia storefront 2. Deploy scaffolding for a new project 3. Use CIF elements in an existing project

* Multi-level catalog navigation to support navigation through categories and sub-categories.

* Pagination on category pages for better UX.

* Client-side rendering of price attribute in Product Detail and Product List components to support rendering of dynamic attributes. 


#### Components
* Server-side Product Carousel to display list of featured products in a carousel style.

* Server-side Featured Category List to display list of categories on an AEM page.



### What's improved
* Support for Magento 2.3.2 and bug fixes related to product properties display in the product console.

***

#### Release Date: June, 2019

|GitHub| Version| Detailed Release Notes|
|:-------|:-----:|---------------------:|
|CIF Connector | 0.2.0|[Release Notes](https://github.com/adobe/commerce-cif-connector/releases)|
|CIF Core Components |0.1.0|[Release Notes](https://github.com/adobe/aem-core-cif-components/releases)|


### What's new

#### Features
*  AEM B2C storefront with mobile-first Venia CSS styling, landing page, dynamic catalog navigation via product and category pages, product search page, and shopping cart capabilities to kickstart and accelerate commerce projects.

* CIF Connector and authoring tools (Product Console, Product Picker, and Category Picker) to enable authors to create experiences in AEM with commerce content.


#### Components
*  First version of CIF Core Components compatible with Magento 2.3.1:
    * Product Detail
    * Product List
    * Product Teaser
    * Navigation
    * Product Search
    * Shopping Cart (REST)
