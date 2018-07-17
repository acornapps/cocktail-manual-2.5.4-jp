# Catalog Layer

---

Containers implement deployments by creating images from configurations. Therefore, repetitive tasks can be minimized and frequently-used DBs and middleware runtime can be easily deployed whenever needed by creating templates of container images and deployment information.

The catalog layer is responsible for creating and managing these templates. The following diagram shows how the catalog layer is structured:

![](/assets/cocktailcloud-architecture-6.png)

The catalog layer is divided into two sections according to purpose.

* Service Catalog : The service catalog stores and manages application snapshots that the user has configured for a service. A snapshot of the service catalog can be used if migration is required due to infrastructure or cloud provider replacement. A snapshot stores the application map configuration as-is. Therefore, the snapshot configuration must be modified as needed when deploying to a different environment.

* Cocktail Catalog : The Cocktail catalog refers to the runtime template provided via Cocktail Hub in Cocktail Cloud. The user can deploy the template as-is or by changing the configuration to suit a specific environment. The Cocktail catalog currently provides widely-used open-source templates (DB, middleware, development/operations tool, blog, machine learning, etc.) and is continually being updated.

---

이전글 : [Pipeline Layer](/d30c-c774-d504-b77c-c778-b808-c774-c5b4.md)

다음글 : [Dashboard Layer](/b300-c2dc-bcf4-b4dc-b808-c774-c5b4.md)

