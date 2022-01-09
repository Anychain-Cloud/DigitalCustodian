# Software Architecture and Design Approach

AnyChain is based on a Domain-Driven Design approach and implemented as a set of serverless design patterns. Our solution is focused purely on the individual functions defined within our structured domain model. The AnyChain mobile or web user interface will not be monolithic. ﻿ Our frontend uses autonomous microapps that are independently deployed. The objective of a micro frontend is to divide the user experience into a set of independent micro applications, while also providing users with a seamless experience. 

## Step1: Identify System Operations

A system operation is an abstraction of a request that the application must handle. It’s either a command, which updates data, or a query, which retrieves data. The behavior of each command is defined in terms of an abstract domain model, which is also derived from the requirements. The system operations become the architectural scenarios that illustrate how the domains collaborate.

<table>
  <tr>
    <td>Artifacts</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>User Stories</td>
    <td>The starting point are the requirements such as the user stories. An application exists to handle requests, so the first step in defining its architecture is to distill the application’s requirements into the key requests.
The AnyChain solution will be implemented via the <a href="https://www.yodiz.com/blog/what-is-scrum-in-agile-methodology-agile-development/">Agile Scrum</a> and the Product Backlog is currently implemented within Yodiz. <a href="https://www.yodiz.com/">Yodiz</a> is a simple but comprehensive agile tool which helps to manage Agile projects of all levels of complexity. </td>
  </tr>
  <tr>
    <td>System Context diagram (<a href="https://c4model.com">C4</a>)</td>
    <td>The highest granularity diagram. It has little detail but its main goal is to describe the context in which the solution resides. So, it will be composed by one single box for the whole application, and it will be surrounded by other boxes that refer to the external systems and users the application interacts with.</td>
  </tr>
  <tr>
    <td>Domains</td>
    <td>The AnyChain implementation is based on Domain-Driven Design (<a href="https://github.com/heynickc/awesome-ddd">DDD</a>). DDD defines a separate domain model for each subdomain. A subdomain is a part of the domain, DDD’s term for the application’s problem space.
DDD calls the scope of a domain model a bounded context. A bounded context includes the code artifacts that implement the model. When using the serverless architecture, each bounded context is a set of self-contained services.
The DDD concept of subdomains and bounded contexts maps nicely as a set of serverless design patterns. Our solution is focused purely on the individual functions defined within our subdomains.﻿ Our frontend uses autonomous microapps that are independently deployed. The objective of a micro frontend is to divide the user experience into a set of independent micro applications, while also providing users with a seamless experience. </td>
  </tr>
  <tr>
    <td>Domain Interface Map</td>
    <td>The Domain Interface Map defines the activity interactions between the associated domains. Activity is based on direction (i=inbound, o=outbound, b=both).</td>
  </tr>
  <tr>
    <td>Domain Diagram (<a href="https://c4model.com">C4</a>)</td>
    <td>The Domain diagram shows the high-level shape of the software architecture and how responsibilities are distributed across it. It also shows the major technology choices and how the serverless functions communicate with one another. It's a simple, high-level technology focused diagram that is useful for software developers and support/operations staff alike.</td>
  </tr>
  <tr>
    <td>Serverless Design Patterns</td>
    <td>Serverless design patterns defined within <a href="https://medium.com/@jgilbert001/serverless-an-example-system-architecture-23aed85fd504">Software Architecture Patterns for Serverless Systems: Architecting for innovation with events, autonomous services, and micro frontends</a> </td>
  </tr>
</table>


 

##  

## Step 2: Identify Domain Functions

Define functions corresponding to DDD domains.

<table>
  <tr>
    <td>Artifacts</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Sequences </td>
    <td>Sequences are interactions that detail how system operations are carried out. They capture the interaction between objects in the context of a collaboration.</td>
  </tr>
  <tr>
    <td>Use Cases</td>
    <td>A spreadsheet that defines use cases based on the defined sequences.</td>
  </tr>
  <tr>
    <td>Decompose Domains by Function</td>
    <td>Add tagging to the user stories spreadsheet.</td>
  </tr>
  <tr>
    <td>Component diagram (<a href="https://c4model.com">C4</a>)</td>
    <td>This diagram shows how a domain is made up of a set of "serverless" functions and capabilities, what each of those "serverless" functions are, their responsibilities and the technology and implementation details.</td>
  </tr>
</table>


 

## Step 3: Define APIs & Collaborations

Define each serverless function’s API: its operations and events. A serverless function API operation exists to:

* Correspond to system operations. They are invoked by external clients and perhaps by other services or functions.

* Support collaboration between functions within domains. These operations are only invoked by other services or functions.

 

<table>
  <tr>
    <td>Artifacts</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Domain API Overview</td>
    <td>A spreadsheet that details the DCI and ACC Domain Overview.

The APIs are broken down by DC Identity (DCI) and AnyChain Cloud (ACC) domains. </td>
  </tr>
    <tr>
    <td>DCI API Calls</td>
    <td>A spreadsheet that details the serverless functions, their operations and potential collaborations.

The APIs are broken down by DCI domains. </td>
  </tr>
      <tr>
    <td>ACC API Calls</td>
    <td>A spreadsheet that details the serverless functions, their operations and potential collaborations.

The APIs are broken down by ACC domains. </td>
  </tr>
</table>


## Step 4: Plan Sprint per domain

Create a planning document for each domain.

<table>
  <tr>
    <td>Artifacts</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Sprint Planning Document by Domain</td>
    <td>A document that details sprint planning and includes:
Domain Overview
Architectural Constraints
User Story Dependencies
Story Tasks for each User Story
Test Plan
Test Results</td>
  </tr>
  <tr>
    <td>Create Sprint Backlog</td>
    <td>Update Sprint backlog</td>
  </tr>
</table>


 

## Step 5: Execute Sprint

<table>
  <tr>
    <td>Artifacts</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Product Backlog Status</td>
    <td>Updated Product Backlog Status</td>
  </tr>
  <tr>
    <td>User Stories Status</td>
    <td>Updated User Story Status</td>
  </tr>
  <tr>
    <td>Sprint Backlog Status</td>
    <td>Updated Sprint Backlog Status</td>
  </tr>
  <tr>
    <td>Test Results</td>
    <td>Test results based on Test Plan</td>
  </tr>
  <tr>
    <td>Required Functional Code</td>
    <td>Executables, written code</td>
  </tr>
  <tr>
    <td>Burn Down Chart</td>
    <td>Updated Burn Down Chart</td>
  </tr>
  <tr>
    <td>Post Sprint Status</td>
    <td>Sprint Review & Retrospective Meeting statuses</td>
  </tr>
</table>
