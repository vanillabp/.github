![VanillaBP](./vanillabp-headline.png)

## What is VanillaBP?

*VanillaBP* is one small Java API for business process engines. Your business code uses that API
and never the API of the engine. So the engine underneath can change, and your business code stays
as it is.

You model a process in BPMN. An adapter runs it on the engine you chose. Your code serves the
tasks of the model and keeps the data of a workflow in an object of your own domain model.

More on [www.vanillabp.io](https://www.vanillabp.io).

*Quick links:* [Get started](#get-started), [The platform](#the-platform),
[Adapters](#adapters), [Add-ons](#add-ons), [Blueprints](#blueprints)

## Get started

1. Read the [VanillaBP wiki](https://github.com/vanillabp/adapter-platform-integration/wiki).
   It explains the concepts and takes you through the setup on your platform.
1. Pick a [blueprint](https://github.com/vanillabp-blueprints). Each one is a small application
   which runs right away.
1. Working with a coding agent? Install the [VanillaBP skills](https://github.com/vanillabp/skills).
   They let the agent pick and combine the blueprints your BPMN model needs.

Coming from VanillaBP 1? The wiki has a
[section for you](https://github.com/vanillabp/adapter-platform-integration/wiki#coming-from-vanillabp-1).
The skills include one for the upgrade.

## The platform

* [SPI for Java](https://github.com/vanillabp/spi-for-java): the API your business code uses.
  Its README is the reference for the annotations and for `ProcessService`.
* [Platform integration](https://github.com/vanillabp/adapter-platform-integration): brings the
  SPI to Spring Boot and to Quarkus. Its [wiki](https://github.com/vanillabp/adapter-platform-integration/wiki)
  is the main documentation of VanillaBP.

## Adapters

An adapter connects VanillaBP to one engine. You add it as a dependency. An application may use
more than one adapter at a time. That is how you change the engine: new workflows start on the new
one, and running workflows finish on the old one.

* Camunda [<img src="./external-link.png">](https://camunda.com):
    * [Camunda 7 adapter](https://github.com/camunda-community-hub/vanillabp-camunda7-adapter),
      for the embedded engine ([about Camunda 7](https://docs.camunda.org))
    * [Camunda 8 adapter](https://github.com/camunda-community-hub/vanillabp-camunda8-adapter),
      for a Camunda 8 cluster ([about Camunda 8](https://docs.camunda.io))

Both adapters live in the Camunda Community Hub. An adapter for the
[Process Engine API](https://github.com/bpm-crafters/process-engine-api) of bpm-crafters is in
preparation.

## Add-ons

These repositories add something to an application. You need none of them to use VanillaBP. Add
one when your application needs what it does.

<!--
  This page is written by hand. A new add-on repository is one line in the list below:
  its link and one sentence on what it adds.
-->

* [Shared election cache on Hazelcast](https://github.com/vanillabp/hazelcast-shared-election-cache):
  lets the nodes of one application share what they know about which engine holds a workflow.
  For Spring Boot and Quarkus.
* [Phase-two outbox on gruelbox](https://github.com/vanillabp/gruelbox-phase-two-outbox):
  keeps the outbox of an application in the gruelbox table it used before. For Spring Boot only.
  A new application takes the outbox VanillaBP brings itself.
* [Business Cockpit](https://github.com/vanillabp/business-cockpit): the application business
  people work in. It lists their user tasks and business cases, whichever engine runs them.
  Its [wiki](https://github.com/vanillabp/business-cockpit/wiki) explains how to connect a
  workflow module. The part which runs in your application is one adapter per engine:
    * [Business Cockpit adapter for Camunda 7](https://github.com/vanillabp/businesscockpit-camunda7-adapter)
    * [Business Cockpit adapter for Camunda 8](https://github.com/vanillabp/businesscockpit-camunda8-adapter)
    * An adapter for the Process Engine API is in preparation.

## Blueprints

A blueprint is a small application which shows one aspect of building business process software
with VanillaBP. There is one repository per blueprint and platform, for Spring Boot and for Quarkus.
Which engine a blueprint runs on is a Maven profile and never a code change.

The [blueprints organisation](https://github.com/vanillabp-blueprints) lists all of them.

## If you are not familiar with BPMN

BPMN is a graphical notation for business processes. A BPMN model is stored as XML. A BPMN engine
runs those models and keeps track of where each workflow stands. So you only write the code of the
tasks, and the engine handles the flow between them.

BPMN was developed by the [Object Management Group (OMG)](https://www.omg.org/bpmn/). It is also an
[ISO standard](https://www.iso.org/standard/62652.html).

To draw your own models, try [Camunda's modeler](https://camunda.com/download/modeler/).
