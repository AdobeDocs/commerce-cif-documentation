# AEM - Magento Integration using Commerce Integration Framework FAQ

1. Is GraphQL only used for Magento or will this be available for querying content authored on
AEMs JCR?
We have adopted Magento’s GraphQL APIs as our official commerce API for all commerce related
data. Hence, we use GraphQL to exchange commerce data with Magento and later this year with
any commerce engine via I/O Runtime. However, we do want to address GraphQL for querying in
AEM in the future.
2. How does Adobe I/O come into play? Does AEM talk to Magento directly?
The AEM commerce connector connects to Magento GraphQL. Hence, AEM can directly connect
to Magento without an I/O Runtime layer. If there is need to integrate additional 3rd party
solutions, the I/O Runtime platform can be used to host the mapping layer to connect the
Magento GraphQL APIs to any 3rd party solutions APIs.
The I/O Runtime platform can also be used to extend or customize commerce services. For this
use-cases you would call the I/O Runtime endpoint that will then host a customized
implementation of the respective service. Integration and extension use-cases can be combined.
3. Can Product assets (images) be stored and referenced from AEM via Magento admin? How
can we consume assets from Dynamic Media?
We currently do not have a productized AEM Assets – Magento integration. As a workaround you
can store product assets (images) in AEM Assets but you will have to manually store the asset
URLs in Magento. Dynamic Media is now part of AEM Assets and will work the same way.
4. Does it matter where Magento is deployed? (On-prem or in the cloud)
It does not matter where Magento is deployed. Our integration and the new AEM Venia store
front will work regardless of the deployment model. However, if it is deployed based on our
approved E2E reference architecture, we will be running E2E tests against performance KPIs that
we have gathered that represent an enterprise customer’s profile. So, this will provide you with
additional information that you can use as a benchmark.
5. How are catalog pages / product pages created in AEM? How do they persist in AEM?
This new integration does not need the classic CIF on-prem workflow to import product and
create product pages in AEM. Catalog pages and product pages are created and cached
dynamically in AEM based on generic catalog and product page templates. No Product / Catalog
data is imported and stored in AEM.
6. Do you also cache pricing and other data via Dispatcher. Does that raise a frequent cache
invalidation challenge?
Dynamic data such as price or inventory is not cached on the Dispatcher. Dynamic data is fetched
client-side with web components directly via GraphQL APIs. We cache only static data (such as
product/category data) on the Dispatcher. If product data changes, there will be need for cache
invalidation, which we have considered.
7. Why are you not using We.Retail?
We are using the Venia theme (developed by Magento) which is mobile first and aligned with
Magento’s PWA. The Venia theme represents the latest in-terms of CSS styling and AEM core
components.
8. When you update product data in Magento, is that a real-time push to AEM? Or is it a batch
process?
We have developed a connector (AEM-CIF connector) which enables data to flow from Magento
to AEM on-demand. Hence, this is not a real-time push or a batch process when there is an
update in Magento.
9. Is there any recommendation on unified search across AEM content + Commerce?
We provide a product search reference implementation but no unified search with content. This
feature is usually very customer specific and better solved on project-specific.
10. How can product data be used in MSM or translations?
Product data is usually already translated in PIM or in Magento. The AEM – Magento Integration
supports the connection to multiple Magento stores & store views. In an MSM setup typically one
AEM site is linked to one Magento store view.
11. How does CIF work with other commerce platforms?
We will be enabling integration with 3rd party solutions (e.g. other commerce solutions) by end of
Q3 via the I/O Runtime platform. We will be enabling GraphQL support on the I/O Runtime
platform so that you can build a mapping layer (hosted on I/O Runtime) to map our GraphQL
APIs to the 3rd party solution’s APIs to build the integration.
12. Is there a way to enhance the product data with commercial text? Where do you do this? In
AEM or in Magento?
This functionality is planned in early 2020 but can be developed on a project-level. There are
multiple ways to achieve this and depends on the use case. One way would be to work with
custom attributes. Allow AEM authors to mutate these fields in AEM’s product editor and sync the
data back to the PIM. Another option would be leveraging AEM Experience Fragments which gets
injected into the product pages.
13. When will GraphQL on Adobe I/O be released?
We are planning to enable GraphQL on I/O Runtime later in 2019.
14. Who should we contact if we face issues while setting up the connector?
You can submit issues/create tickets on GitHub: https://github.com/adobe/commerce-cifconnector/issues
15. Does the integration between AEM-Magento change when Adobe I/O Runtime platform is
used?
Customers will not need to re-do the integration once GraphQL on I/O Runtime is available.
Customers who want to extend commerce services can use the same integration and write action
sequences hosted on the I/O Runtime platform to inject business logic and enrich the commerce
services.
16. With no products stored in AEM, how do you envision authors mapping images to a specific
product?
You can store product assets (images) in AEM Assets but you will have to manually store the
asset URLs in Magento. We will also provide authors with a tagging feature in Q3 2019 so that
they can tag assets with product / catalog to enable product specific asset search.
17. Since AEM creates product and catalog pages dynamically based on a generic template in
AEM, what would I see if I were to open CRXDE Lite and check under content? Would I see an
entire product tree based on the products in Magento? If not, how would an author enhance
those pages?
There are no JCR catalog / product pages anymore. See question 12.
18. Will SPA store front work with AEM SPA editor?
AEM can be used as an authoring tool for any kind of store front. Currently, we are used hybrid
rendering for our new store front. In the future, we will look into SPA and PWA and use AEM for
authoring.
19. How does PIM play into this framework?
PIM data gets exposed to AEM and clients via GraphQL requests.