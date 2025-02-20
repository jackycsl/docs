---
type: docs
title: Workflow overview
linkTitle: Overview
weight: 1000
description: "Overview of Dapr Workflow"
---

{{% alert title="Note" color="primary" %}}
Dapr Workflow is currently in alpha.
{{% /alert %}}

Dapr Workflow makes orchestrating the logic required for messaging, state management, and failure handling across various microservices easier for developers. Dapr Workflow enables you to create long running, fault-tolerant, stateful applications. Prior to Dapr Workflow, you'd often need to build ad-hoc workflows in custom, complex code in order to achieve long running, fault-tolerant, stateful applications. 

The durable, resilient Dapr Workflow capability:

- Offers a built-in workflow runtime for driving Dapr Workflow execution
- Provides SDKs for authoring workflows in code, using any language
- Provides HTTP and gRPC APIs for managing workflows (start, query, suspend/resume, terminate)
- Integrates with any other workflow runtime via workflow components

<img src="/images/workflow-overview/workflow-overview.png" width=800 alt="Diagram showing basics of Dapr Workflow">

Some example scenarios that Dapr Workflow can perform are:

- Order processing involving inventory management, payment systems, shipping, etc.
- HR onboarding workflows coordinating tasks across multiple departments and participants.
- Orchestrating the roll-out of digital menu updates in a national restaurant chain.
- Image processing workflows involving API-based classification and storage.


## Features

### Workflows and activities

With Dapr Workflow, you can write activites and then compose those activities together into a workflow. Workflow activities are:
- The basic unit of work in a workflow
- The tasks that get orchestrated in the business process

[Learn more about workflow activities.]({{< ref "workflow-features-concepts.md##workflow-activities" >}})

### Child workflows

In addition to activities, you can write workflows to schedule other workflows as child workflows. A child workflow is independent of the parent workflow that started it and support automatic retry policies.

[Learn more about child workflows.]({{< ref "workflow-features-concepts.md#child-workflows" >}})

### Timers and reminders

Same as Dapr actors, you can schedule reminder-like durable delays for any time range. 

[Learn more about workflow timers]({{< ref "workflow-features-concepts.md#durable-timers" >}}) and [reminders]({{< ref "workflow-architecture.md#reminder-usage-and-execution-guarantees" >}})

### Workflow HTTP calls to manage a workflow

When you create an application with workflow code and run it with Dapr, you can call specific workflows that reside in the application. Each individual workflow can be:

- Started or terminated through a POST request
- Queried through a GET request

[Learn more about how manage a workflow using HTTP calls.]({{< ref workflow_api.md >}})

### Manage other workflow runtimes with workflow components

You can call other workflow runtimes (for example, Temporal and Netflix Conductor) by writing your own workflow component. 

## Workflow patterns

Dapr Workflow simplifies complex, stateful coordination requirements in microservice architectures. The following sections describe several application patterns that can benefit from Dapr Workflow. 

Learn more about [different types of workflow patterns]({{< ref workflow-patterns.md >}})

## Workflow SDKs

The Dapr Workflow _authoring SDKs_ are language-specific SDKs that contain types and functions to implement workflow logic. The workflow logic lives in your application and is orchestrated by the Dapr Workflow engine running in the Dapr sidecar via a gRPC stream.

### Supported SDKs

You can use the following SDKs to author a workflow.

| Language stack | Package |
| - | - |
| .NET | [Dapr.Workflow](https://www.nuget.org/profiles/dapr.io) |

## Try out workflows

### Quickstarts and tutorials

Want to put workflows to the test? Walk through the following quickstart and tutorials to see workflows in action:

| Quickstart/tutorial | Description |
| ------------------- | ----------- |
| [Workflow quickstart]({{< ref workflow-quickstart.md >}}) | Run a .NET workflow application with four workflow activities to see Dapr Workflow in action  |
| [Workflow .NET SDK example](https://github.com/dapr/dotnet-sdk/tree/master/examples/Workflow) | Learn how to create a Dapr Workflow and invoke it using ASP.NET Core web APIs. |

### Start using workflows directly in your app

Want to skip the quickstarts? Not a problem. You can try out the workflow building block directly in your application. After [Dapr is installed]({{< ref install-dapr-cli.md >}}), you can begin using  workflows, starting with [how to author a workflow]({{< ref howto-author-workflow.md >}}).

## Watch the demo

Watch [this video for an overview on Dapr Workflow](https://youtu.be/s1p9MNl4VGo?t=131):

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/s1p9MNl4VGo?start=131" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Next steps

{{< button text="Workflow features and concepts >>" page="workflow-features-concepts.md" >}}

## Related links

- [Workflow API reference]({{< ref workflow_api.md >}})
- [Try out the .NET example](https://github.com/dapr/dotnet-sdk/tree/master/examples/Workflow)
