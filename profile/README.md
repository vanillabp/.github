![VanillaBP](./vanillabp-headline.png)

## What is VanillaBP?

*VanillaBP* is an independent API for business processing engines kept simple, plain and without frills.

Checkout the [SPI for Java](https://github.com/vanillabp/spi-for-java) to see how *VanillaBP* looks like.

*Quick-links:* [Available adapters](#available-adapters), [Blueprints](#blueprints)

## Motivation

Developing [BPMN](#if-you-are-not-familiar-with-bpmn) based business processing software is an excellent way to build maintainable code focused on business value:

1. Processes can be defined by business people using a graphical representation (BPMN).
1. There is no need to code the underlying workflows as a BPMN engine is used to run the BPMN process.

Unfortunately, there is no standardized API for BPMN engines. Each BPMN engine, also called Business Processing Management System (BPMS) or workflow system, has its own API. Using a workflow system requires that a developer knows the API and also understands its paradigms. In addition, moving to other technology stacks/APIs requires re-implementation of at least parts of the business logic.

To solve these problems, we decided to introduce *VanillaBP*.

Business process engine vendors can provide implementations called adapters that hide the details of the specific workflow system's API. This allows the developer to focus on the business aspects rather than the technical details. Vendors, on the other hand, can focus on the unique features of their engine, such as available runtime environments, storage adapters, or scalability.

## Available Adapters

Vendors:

* Camunda [<img src="./external-link.png">](https://camunda.com):
    * [Version 7 adapter](https://github.com/camunda-community-hub/vanillabp-camunda7-adapter) (about [Camunda Platform 7](https://docs.camunda.org))
    * [Version 8 adapter](https://github.com/camunda-community-hub/vanillabp-camunda8-adapter) (about [Camunda Platform 8](https://docs.camunda.io))

## Blueprints

There are blueprints available for building projects using VanillaBP. Choose the best matching blueprint according to your project attributes:

1. **Standalone:**<br>
   *Type:* A (micro-)service responsible for one workflow module [<img src="./external-link.png">](https://github.com/vanillabp/spring-boot-support#workflow-modules)
   having a custom user interface for operating user tasks and workflows (not part of the blueprint).<br>
   *Available for:* [Spring Boot](https://github.com/vanillabp/blueprint-workflowmodule-springboot-standalone), Jakarta-EE, Quarkus
1. **Standalone leveraging Business Cockpit:**<br>
   *Type:* A (micro-)service responsible for one workflow module [<img src="./external-link.png">](https://github.com/vanillabp/spring-boot-support#workflow-modules)
   integrating into the VanillaBP Business Cockpit [<img src="./external-link.png">](https://github.com/vanillabp/business-cockpit)
   for operating user tasks and workflows.<br>
   *Available for:* Sprint Boot, Jakarta-EE, Quarkus
1. **Workflow Module:**<br>
   *Type:* An independent workflow module [<img src="./external-link.png">](https://github.com/vanillabp/spring-boot-support#workflow-modules)
   to be hosted next to other workflow modules in one (micro-)service.
   *Available for:* Sprint Boot, Jakarta-EE, Quarkus
1. **Host for workflow modules:**<br>
   *Type:* A (micro-)service acting as a runtime environment hosting independent
   workflow modules [<img src="./external-link.png">](https://github.com/vanillabp/spring-boot-support#workflow-modules).
   Typically used to bundle workflow modules of the same scope (e.g. same department, same business unit).<br>
   *Available for:* Sprint Boot, Jakarta-EE, Quarkus
1. **Workflow Module leveraging Business Cockpit:**<br>
   *Type:* An independent workflow module [<img src="./external-link.png">](https://github.com/vanillabp/spring-boot-support#workflow-modules)
   to be hosted next to other workflow modules in one (micro-)service
   integrating into the VanillaBP Business Cockpit [<img src="./external-link.png">](https://github.com/vanillabp/business-cockpit)
   for operating user tasks and workflows.<br>
   *Available for:* Sprint Boot, Jakarta-EE, Quarkus
1. **Host for workflow modules leveraging Business Cockpit:**<br>
   *Type:* A (micro-)service acting as a runtime environment hosting independent
   workflow modules [<img src="./external-link.png">](https://github.com/vanillabp/spring-boot-support#workflow-modules)
   integrating into the VanillaBP Business Cockpit [<img src="./external-link.png">](https://github.com/vanillabp/business-cockpit)
   for operating user tasks and workflows. 
   Typically used to bundle workflow modules of the same scope (e.g. same department, same business unit).<br>
   *Available for:* Sprint Boot, Jakarta-EE, Quarkus

## If you are not familiar with BPMN

BPMN is a graphical representation for specifying business processes in XML also including semantic information. A BPMN engine runs those processes and acts as a state engine. This helps to dramatically reduce the amount of code since only "tasks" need to be implemented and the flow is handled by the engine.

BPMN was developed by the [Object Management Group (OMG)](https://www.omg.org/bpmn/). Meanwhile [BPMN is an ISO standard](https://www.iso.org/standard/62652.html).

To build your own models try [Camunda's modeler](https://camunda.com/de/download/modeler/).
