![VanillaBP](./vanillabp-headline.png)

## What is VanillaBP?

*VanillaBP* is an independent API for business processing engines kept simple, plain and without frills.

Checkout the [SPI for Java](https://github.com/vanillabp/spi-for-java) to see how *VanillaBP* looks like.

## Motivation

Developing [BPMN](#if-you-are-not-familiar-with-bpmn) based business processing software is an excellent way to build maintainable code focused on business value:

1. Processes can be defined by business people using a graphical representation (BPMN).
1. There is no need to code the underlying workflows as a BPMN engine is used to run the BPMN process.

Unfortunately, there is no standardized API for BPMN engines. Each BPMN engine, also called Business Processing Management System (BPMS) or workflow system, has its own API. Using a workflow system requires that a developer knows the API and also understands its paradigms. In addition, moving to other technology stacks/APIs requires re-implementation of at least parts of the business logic.

To solve these problems, we decided to introduce *VanillaBP*.

Business process engine vendors can provide implementations called adapters that hide the details of the specific workflow system's API. This allows the developer to focus on the business aspects rather than the technical details. Vendors, on the other hand, can focus on the unique features of their engine, such as available runtime environments, storage adapters, or scalability.

## Available Adapters

Vendors:

* Camunda [<img src="profile/external-link.png">](https://camunda.com):
    * [Version 7 adapter](https://github.com/Phactum/vanillabp-camunda7-adapter) (about [Camunda 7](https://docs.camunda.org))
    * [Version 8 adapter](https://github.com/Phactum/vanillabp-camunda8-adapter) (about [Camunda 8](https://docs.camunda.io))

## If you are not familiar with BPMN

BPMN is a graphical representation for specifying business processes in XML also including semantic information. A BPMN engine runs those processes and acts as a state engine. This helps to dramatically reduce the amount of code since only "tasks" need to be implemented and the flow is handled by the engine.

BPMN was developed by the [Object Management Group (OMG)](https://www.omg.org/bpmn/). Meanwhile [BPMN is an ISO standard](https://www.iso.org/standard/62652.html).

To build your own models try [Camunda's modeler](https://camunda.com/de/download/modeler/).