# Creating a new AEM CIF Project

The [CIF Project archetype](https://github.com/adobe/aem-cif-project-archetype) creates a minimal Adobe Experience Manager (AEM) CIF project as a starting point for customer projects using [CIF Core Components](https://github.com/adobe/aem-core-cif-components). The CIF Project archetype should be used for new projects looking to integrate AEM and Magento using the Commerce Integration Framework. The CIF Project archetype can also serve as a useful reference for existing AEM projects looking to add the CIF related dependencies.

In this guide we will generate a new AEM CIF project using the CIF Project archetype and explore how to use it.

## Background

**What is a Maven project?** - [Apache Maven](https://maven.apache.org/) is a software management tool to build projects. All AEM implementations use Maven projects to build, manage and deploy custom code on top of AEM.

**What is a Maven archetype?** - A [Maven archetype](https://maven.apache.org/archetype/index.html) is a template or pattern for generating new projects. The CIF Project archetype allows us to generate a new project with a custom namespace and include a project structure that follows best practices.

## Prerequisites

The following tools and technologies are required:

* [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/index.html) or [Java 11](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html) (AEM 6.5+ only)
* [Apache Maven](https://maven.apache.org/) (3.3.9 or newer)
* Adobe Experience Manager
  * [AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/technical-requirements.html)
  * [AEM 6.4.4+](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html)

It is also considered a best practice to include the Adobe Public Maven Repository in your Maven settings. This file, commonly found at `~/.m2/settings.xml` can be updated following this [Knowledge Base](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html) article.

## Generate the project

The next series of steps will take place using a UNIX based command line  terminal,  but should be similar if using a Windows terminal.

1. Verify that Maven is correctly installed and available from the command line:

    ```shell
    $ mvn -version
      Apache Maven 3.3.9
      Maven home: /Library/apache-maven-3.3.9
      Java version: 11.0.2, vendor: Oracle Corporation
      Java home: /Library/Java/JavaVirtualMachines/jdk-11.0.2.jdk/Contents/Home
    ```

2. Navigate to a directory, i.e a source folder, in which you want to generate the project:

    ```shell
    $ cd ~/src
    ```

3. Copy+Paste the following command to initiate the creation of a new project in interactive mode:

    ```shell
    mvn archetype:generate \
    -DarchetypeGroupId=com.adobe.commerce.cif \
    -DarchetypeArtifactId=cif-project-archetype \
    -DarchetypeVersion=0.2.0
    ```

    > *Note, in the above command we use version **0.2.0** of the archetype. As a best practice, always use the latest [released version of the archetype](https://github.com/adobe/aem-cif-project-archetype/releases).*

4. The CIF Project Archetype will prompt a series of parameters to generate the project. For the sake of this tutorial and in order to see the effects of the different parameters we will generate the project for the fictitious **Acme Corporation**.

    Use the following values:

    | Name                  | Value                | Description                        |
    | --------------------- | -------              | ---------------------------------- |
    | groupId               | **com.acme.cif**     | Base Maven groupId                 |
    | appsFolderName        | **acme**             | `/apps` folder name                |
    | artifactId            | **acme-store**       | Base Maven ArtifactId              |
    | version               | **1.0-SNAPSHOT**     | Version                            |
    | package               | **com.acme.cif**     | Java Source Package                |
    | artifactName          | **Acme Store**       | Maven Project Name                 |
    | componentGroupName    | **Acme.Content**     | AEM component group name           |
    | confFolderName        | **acme**             | `/conf` folder name                |
    | contentFolderName     | **acme**             | `/content` folder name             |
    | optionAemVersion      | *6.5.0*              | Target AEM version                 |
    | optionIncludeExamples | *y*                  | Include Component Library examples |
    | packageGroup          | **acme**             | Content Package Group name         |
    | siteName              | **Acme Store**       | AEM site name                      |

    > Note: If the archetype is executed in interactive mode the first time properties with default values can't be changed (see [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) for more details). The value can be changed when the property confirmation at the end is denied and the questionnaire gets repeated or by passing the parameter in the command line (e.g. `-DoptionIncludeExamples=n`).

5. The following folder and file structure will be generated by the archetype:

    ```plain
    ~/src/
        |--- acme-store/
              |--- all/
              |--- core/
              |--- samplecontent/
              |--- ui.apps/
              |--- ui.content/
              |--- README.md
              |--- pom.xml
    ```

    * **Parent POM** - deploys maven modules and manages dependency versions
    * **core** - Java bundle containing all core functionality like Sling Models, OSGi services, and other component related Java code such as servlets or request filters.
    * **ui.apps** - contains the `/apps` part of the project, including proxy components for CIF core components and WCM Core Components.
    * **ui.content** - contains structural content and configurations (`/content`, `/conf`) including CIF templates like catalog template, category template, and search result template.
    * **samplecontent** - contains some sample assets and pages to get started. Once a project reaches maturity, this module can be removed and should be removed prior to production.
    * **all** - combines all of the sub-modules and CIF dependencies into a single package that can be installed to a local AEM instance.

## Deploy the project to AEM

Now that we have generated a new project, we can deploy the project code to a local instance of AEM.

1. Ensure you have an instance of AEM running locally on port **4502**.
2. From the command line navigate into the `acme-store` project directory:

    ```shell
    $ cd acme-store/
    ```

3. Run the following command to build and deploy the entire project to AEM:

    ```shell
    $ mvn clean install -PautoInstallAll

    ...

    Package installed in 6388ms.
    [INFO] ------------------------------------------------------------------------
    [INFO] Reactor Summary:
    [INFO]
    [INFO] acme-store ......................................... SUCCESS [  0.306 s]
    [INFO] Acme Store - Core .................................. SUCCESS [  7.399 s]
    [INFO] Acme Store - UI apps ............................... SUCCESS [  3.211 s]
    [INFO] Acme Store - UI content ............................ SUCCESS [  1.069 s]
    [INFO] Acme Store - Sample Content ........................ SUCCESS [  2.257 s]
    [INFO] Acme Store - All-in-one package .................... SUCCESS [  8.572 s]
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESS
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time: 24.882 s
    [INFO] Finished at: 2019-07-18T17:36:20-07:00
    [INFO] Final Memory: 46M/167M
    [INFO] ------------------------------------------------------------------------
    ```
  
    Since we ran the maven command at the root of the project, all sub-modules of the project are built. Maven goals of `clean` and `install` cause existing artifacts to be removed and re-compiled. The profile `autoInstallAll` part of the **all** module and is used to package up all of the modules into a single AEM package that is deployed.

4. Navigate to AEM to view the deployed packages: [http://localhost:4502/crx/packmgr/index.jsp](http://localhost:4502/crx/packmgr/index.jsp).

    Search for the package **acme-store.all-1.0-SNAPSHOT.zip**:

    ![Acme Store All Package](assets/acme-store-all-package.png)

    Many more packages were installed than just the **acme-store.all-1.0-SNAPSHOT.zip** package. This is because the **acme-store.all-1.0-SNAPSHOT.zip** embedded multiple sub-packages within it. Some of these sub-packages even included sub-sub-packages! Luckily the archetype took care of setting up these dependencies for us.

    Below are the important packages that were installed that you should be aware of:

    **Project Packages**

    * `acme-store.ui.apps-1.0-SNAPSHOT.zip` - This is the compiled package from the **ui.apps** module generated by the archetype. All of the components and customizations related to the Acme store project will be managed here.
    * `acme-store.ui.content-1.0-SNAPSHOT.zip` - This is the compiled package from the **ui.content** module generated by the archetype. All of the configurations and policies related to the Acme store project will be managed here.
    * `acme-store.samplecontent-1.0-SNAPSHOT.zip` - This is the compiled package from the **samplecontent** module. Keep in mind this module is intended to be used just in the beginning of a project.

    **Commerce Dependency Packages**
  
    * `core.wcm.components.all-2.4.0.zip` - [AEM WCM Core Components](https://github.com/adobe/aem-core-wcm-components) are a standardized set of web content management components like Text, Image, and List. These components are used across AEM implementations.
    * `core-cif-components-all-0.2.0.zip` - [AEM CIF Core Components](https://github.com/adobe/aem-core-cif-components) are a standardized set of commerce components for integrating AEM, CIF, and Magento.
    * `cif-connector-content-0.1.1.zip` - [AEM CIF Connector](https://github.com/adobe/commerce-cif-connector) provides an AEM Commerce connector for Magento and GraphQL and authoring tools.

5. Navigate to the AEM Sites Console to view the sample content: [http://localhost:4502/sites.html/content/acme/us](http://localhost:4502/sites.html/content/acme/us)

    ![Acme Store Sites Console](assets/acme-store-sites-console.png)

    If you have followed the video on the [Getting Started AEM - Magento Integration](01-getting-started.md) and installed the [Venia Demo Store Project](https://github.com/adobe/aem-cif-project-archetype/releases/tag/latest) this should look familiar. This is because the **samplecontent** installed with the archetype is the same content that the Venia Demo Store project uses. Now that we have our own AEM project, with a custom namespace, we can use the Venia Store as a base and begin to customize the project to meet our needs.

## Setup AEM - Magento Integration

At this point the [Acme storefront](http://localhost:4502/editor.html/content/acme/us/en.html) does not render any products or categories. While the archetype does a lot of heavy lifting for us, it does **not** include the configurations needed to bind a Magento store. Aspects of these configurations will be unique to each customer.

If you have followed the video on the [Getting Started AEM - Magento Integration](01-getting-started.md) you'll know that these configurations can be done via the AEM web UI. Now that we have generated our own project we can add these configurations directly to the project. Adding these configurations to the project will eliminate the need to manually setup the integration every time we start a new instance of AEM and ensure consistency across environments.

In the following steps we will be adding modifying several files in the generated project beneath `acme-store` (where you generated the project on the file system). You can use your favorite text-editor or import the Maven project using an [IDE like Eclipse, IntelliJ or Visual Studio Code](https://helpx.adobe.com/experience-manager/kt/platform-repository/using/local-aem-dev-environment-article-setup.html#setup-integrated-env).

### Add OSGi Configurations

1. Beneath `ui.apps/src/main/content/jcr_root/apps/acme` add a new folder named `config`

    ```diff
      /ui.apps
        ...
          /apps
            /acme
              /components
    +         /config
    ```

    > AEM uses the notion of [Run Modes](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/configure-runmodes.html) to define specific configurations for specific environments. The easiest way to target different environments is via the folder name. In this case *config* will apply to all environments. You can create additional run-modes with different folder names to target different environments. More [details can be found here](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/configure-runmodes.html#Definingconfigurationpropertiesforarunmode). This may be useful if you wish to have different Magento configurations based on Author vs. Publish or Dev/QA vs. Production.

2. Create a new XML file beneath the `/config` folder named: `com.adobe.cq.commerce.graphql.client.impl.GraphqlClientImpl-acmestoreclient.xml`

    ```diff
      /ui.apps
        ...
          /apps
            /acme
              /components
              /config
    +             com.adobe.cq.commerce.graphql.client.impl.GraphqlClientImpl-acmestoreclient.xml
    ```

    > Note the suffix of `-acmestoreclient` to the name of the file. The `GraphqlClientImpl` is an OSGi Configuration Factory and allows for multiple configurations. You can add more configurations, you just need to ensure that each has a unique suffix so that AEM doesn't get confused during installation. More details about [OSGi Configuration with files can be found here](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/configuring-osgi.html?cq_ck=1368002864971#OSGiConfigurationwithconfigurationfiles).

3. Populate `com.adobe.cq.commerce.graphql.client.impl.GraphqlClientImpl-acmestoreclient.xml` with the following, replacing *YOUR-MAGENTO-HOST* with your Magento hostname.

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0"
      jcr:primaryType="sling:OsgiConfig"
      acceptSelfSignedCertificates="{Boolean}false"
      identifier="acme"
      maxHttpConnections="{Long}20"
      url="https://YOUR-MAGENTO-HOST/graphql"/>

    ```

    > Note that we are setting the identifer to **acme**. This will be used in several locations in the following steps.

4. Create a second XML file beneath the `/config` folder named: `com.adobe.cq.commerce.graphql.magento.GraphqlDataServiceImpl-acmestoregraphql.xml`

    ```diff
      /ui.apps
        ...
          /apps
            /acme
              /components
              /config
                 com.adobe.cq.commerce.graphql.client.impl.GraphqlClientImpl-acmestoreclient.xml
    +            com.adobe.cq.commerce.graphql.magento.GraphqlDataServiceImpl-acmestoregraphql.xml
    ```

    > Like the `GraphqlClientImpl`, `GraphqlDataServiceImpl` is an OSGi Configuration factory, hence the unique suffix of `-acmestoregraphql`.

5. Populate `com.adobe.cq.commerce.graphql.magento.GraphqlDataServiceImpl-acmestoregraphql.xml` with the following, replacing *YOUR_ROOT_CATEGORY_ID* with the number of your Magento's default category. This will be a number like *2*.

    ![Magento Root Category ID](assets/magento-default-category.png)

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0"
        jcr:primaryType="sling:OsgiConfig"
        catalogCachingEnabled="{Boolean}true"
        catalogCachingSchedulerEnabled="{Boolean}true"
        catalogCachingTimeMinutes="{Long}60"
        categoryCachingSize="{Long}100"
        identifier="acme"
        productCachingEnabled="{Boolean}true"
        productCachingSize="{Long}1000"
        productCachingTimeMinutes="{Long}5"
        rootCategoryId="{Long}YOUR_ROOT_CATEGORY_ID"
        storeCode="default"/>
    ```

    > Note the `identifier` is set to **acme**, corresponding to the `GraphqlClientImpl` configuration from Step 3.

### Add Product Console Binding

1. Beneath `ui.content/src/main/content/META-INF/vault/` open the file `filter.xml`
2. Add a new filter root to the configuration:

    ```diff
      <?xml version="1.0" encoding="UTF-8"?>
      <workspaceFilter version="1.0">
          <filter root="/conf/acme" mode="merge"/>
          <filter root="/content/acme" mode="merge"/>
          <filter root="/content/dam/acme" mode="merge"/>
    +     <filter root="/var/commerce/products/acme-store" />
      </workspaceFilter>
    ```
3. Create a folder structure beneath `ui.content/src/main/content/jcr_root` that matches the path added in the previous step:

    ```diff
    /ui.content
      ...
        /jcr_root
            /conf
            /content
    +       /var
    +         /commerce
    +           /products
    +             /acme-store
    ```

4. Beneath the `ui.content/src/main/content/jcr_root/var/commerce/products/acme-store` folder add a new file named `.content.xml`. Populate the file with the following:

  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0" xmlns:cq="http://www.day.com/jcr/cq/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0"
      cq:catalogDataResourceProviderFactory="magento-graphql"
      cq:catalogIdentifier="acme"
      jcr:language="en"
      jcr:primaryType="sling:Folder"
      jcr:title="Acme Store"/>
  ```

  > Note the `cq:catalogIdentifier` is set to **acme** which corresponds to the OSGi Configuration added earlier.

### Update Sample Content

Next we will update the **samplecontent** module to match the configurations.

1. Open the file `samplecontent/src/main/content/jcr_root/content/acme/us/.content.xml`. This is the root configuration for the sample US storefront site.
2. Update the `cq:graphqlClient` value to point to `acme`.

    ```diff
    <?xml version="1.0" encoding="UTF-8"?>
    <jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0" xmlns:cq="http://www.day.com/jcr/cq/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0"
        jcr:primaryType="cq:Page">
        <jcr:content
    -       cq:graphqlClient="default"
    +       cq:graphqlClient="acme"
            cq:lastModified="{Date}2019-04-17T12:05:17.396+02:00"
            cq:lastModifiedBy="admin"
    ```

    > Note that **acme** is the identifier used for the GraphQL client configured in the **Add OSGi Configurations** above.

3. Open the file `samplecontent/src/main/content/jcr_root/content/acme/us/en/products/.content.xml`. This is the configuration properties for the US Product Page.
4. Update the `magentoRootCategoryId` from **4** to the value of your Magento default category id. This will be the number used in step 5 of **Add OSGi Configurations** above.

    ```diff
    <?xml version="1.0" encoding="UTF-8"?>
    <jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0" xmlns:cq="http://www.day.com/jcr/cq/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0"
        jcr:primaryType="cq:Page">
        <jcr:content
            cq:lastModified="{Date}2019-04-17T13:22:08.497+02:00"
            cq:lastModifiedBy="admin"
            cq:lastRolledout="{Date}2019-04-17T13:22:08.503+02:00"
            cq:lastRolledoutBy="admin"
            cq:template="/conf/acme/settings/wcm/templates/catalog-page"
            jcr:mixinTypes="[cq:LiveRelationship]"
            jcr:primaryType="cq:PageContent"
            jcr:title="Catalog Page"
            sling:resourceType="acme/components/structure/catalogpage"
    -       magentoRootCategoryId="4"
    +       magentoRootCategoryId="YOUR_ROOT_CATEGORY_ID"
            showMainCategories="{Boolean}true"/>
    ```

### Deploy the project to AEM

1. From the command line navigate into the `acme-store` project directory:

    ```shell
    $ cd acme-store/
    ```

2. Run the following command to build and deploy the entire project to AEM:

    ```shell
    $ mvn clean install -PautoInstallAll

    ...

    Package installed in 6388ms.
    [INFO] ------------------------------------------------------------------------
    [INFO] Reactor Summary:
    [INFO]
    [INFO] acme-store ......................................... SUCCESS [  0.306 s]
    [INFO] Acme Store - Core .................................. SUCCESS [  7.399 s]
    [INFO] Acme Store - UI apps ............................... SUCCESS [  3.211 s]
    [INFO] Acme Store - UI content ............................ SUCCESS [  1.069 s]
    [INFO] Acme Store - Sample Content ........................ SUCCESS [  2.257 s]
    [INFO] Acme Store - All-in-one package .................... SUCCESS [  8.572 s]
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESS
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time: 24.882 s
    [INFO] Finished at: 2019-07-18T17:36:20-07:00
    [INFO] Final Memory: 46M/167M
    [INFO] ------------------------------------------------------------------------
    ```

3. Navigate to the OSGi Configuration manager: [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr) and verify that both OSGi Configurations have been persisted:

    ![OSGi Configurations](assets/osgi-configurations.png)

4. Navigate to the AEM Products Console: [http://localhost:4502/aem/products.html/var/commerce/products](http://localhost:4502/aem/products.html/var/commerce/products) and verify that the Acme Store products have binded successfully with Magento:

    ![Commerce Console](assets/commerce-console.png)
  
5. Navigate to the AEM Sites Console and open the **US** `>` **EN** homepage: [http://localhost:4502/editor.html/content/acme/us/en.html](http://localhost:4502/editor.html/content/acme/us/en.html). Switch into **Preview** mode. The navigation of the site should now be populated with categories from the binded Magento instance:

    ![US EN Home Page](assets/us-en-samplesite.png)

    You should now be able to browse catalogs and products within the sample refrence storefront site.

## Additional Resources {#additional-resources}

* [AEM CIF Archetype](https://github.com/adobe/aem-cif-project-archetype)
* [AEM CIF components](https://github.com/adobe/aem-core-cif-components)
* [AEM CIF connector and authoring tools](https://github.com/adobe/commerce-cif-connector)
* [Set up a Local AEM Development Environment](https://helpx.adobe.com/experience-manager/kt/platform-repository/using/local-aem-dev-environment-article-setup.html)
* [Getting Started with AEM Sites](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)
* [AEM Run Modes](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/configure-runmodes.html)
