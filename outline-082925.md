# Outline

# References and Background Information

* [OpenShift Local Getting Started](https://developers.redhat.com/products/openshift-local/getting-started)
* [OKD - Origin Kubernetes Distribution](https://okd.io)
* [Using OpenShift Local or OKD](https://crc.dev/docs/using/) 
* [OpenShift Local Releases](https://github.com/crc-org/crc/releases)
* [OpenShift Local Release 2.53.0 Download](https://mirror.openshift.com/pub/openshift-v4/clients/crc/2.53.0/)

* [Red Hat Console for OpenShift Local](https://console.redhat.com/openshift/create/local)
* [Red Hat Developer Subscriptions for Individuals (Terms and Conditions)](blob:https://www.redhat.com/a7408878-d8fb-49f5-9d01-35cb3bb2344c)

* [Installing OpenShift on a single node](https://docs.okd.io/latest/installing/installing_sno/install-sno-installing-sno.html)
* [Operator Framework FAQ](https://operatorframework.io/faq)
* [MCP - Model Context Protocol](https://modelcontextprotocol.io/)
* [HELM - The package manager for Kubernetes](https://helm.sh)

* [ToolHive GitHub Repository](https://github.com/stacklok/toolhive)
* [ToolHive Documentation](https://docs.stacklok.com/toolhive)
* [ToolHive Operator CRDs Helm Chart](https://github.com/stacklok/toolhive/tree/main/deploy/charts/operator-crds)
* [ToolHive Operator Helm Chart](https://github.com/stacklok/toolhive/tree/main/deploy/charts/operator)

* [MCP Inspector](https://github.com/modelcontextprotocol/inspector)

* [Fetch MCPServer CRD instance example](https://github.com/stacklok/toolhive/blob/main/examples/operator/mcp-servers/mcpserver_fetch.yaml)
* [Yardstick MCPServer CRD instance example](https://github.com/stacklok/toolhive/blob/main/examples/operator/mcp-servers/mcpserver_yardstick_stdio.yaml)


## Prerequisites

* HELM installed
* Access to a an OpenShift based kubernetes cluster, either OpenShift Local or OKD 
  * Usually admin access is required as you will need to be installing CRDs for an operator
* OpenShift Local can be a great option here or a single node okd cluster
If OpenShift Local is not a fit for you, check out OKD (okd.io) and the instructions
for installing a single node instance
Reference: https://docs.okd.io/latest/installing/installing_sno/install-sno-installing-sno.html
* MCP Inspector running

## Installation TL;DR

* helm upgrade released operator-crds
* helm upgrade released operator
* oc create -f examples/operator/mcp_servers/mcpserver_yardstick.yaml
* oc create -f examples/operator/mcp_servers/mcpserver_fetch.yaml

## Introduction
* set the context for what follows

### What is MCP
* briefly cover the purpose of MCP, the Model Context Protocol


### What is ToolHive?
* briefly cover the what ToolHive is in relation to MCP, the Model Context Protocol
  * ensure the ToolHive operator is covered, that is the kubernetes experience on okd via the operator

#### ToolHive Operator
* give an introduction to the ToolHive operator drawn from the ToolHive Documentation and the ToolHive GitHub Repository
  * MCPServer CRD description
  * The MCPServer controller that does reconciliation
  * The Operand proxy-runner and the context of it being a derivative from the local developer tooling.
  * The use of a kubernetes Deployment for the proxy and a StatefulSet for the MCP Server itself
* talk about extended concepts how the proxy allows you to run stdio servers in kubernetes while doing authentication and telemetry

### MCPServer CRD usage

* Basics
** Examples
*** yardstick stdio echo server
*** fetch streamable http server
** Extended Examples possible with PodTemplateSpec but not covered here

### Summary of what was observed above

* Diagram / screenshot of traffic flow

### Proxying - how the examples work

#### stdio

* yardstick

#### sse / streamable http

* fetch


