# 125: OpenIM 集群化部署提案 [RFC] Cluster Deployment for OpenIMSDK

> [RFC #0007] Cluster Deployment for OpenIMSDK

<!-- 🤖 design template: https://github.com/OpenIMSDK/community/blob/main/0000-template.md ⚠️ Please submit a PR to https://github.com/OpenIMSDK/community/tree/main/RFC according to the specification after the design is completed -->

## Meta

- Name: Cluster Deployment for OpenIMSDK
- Start Date: 2023-09-04
- Author(s): @cubxxw
- Status: Draft
- RFC Pull Request: (leave blank)
- OpenIMSDK Pull Request: (leave blank)
- OpenIMSDK Issue: (leave blank)
- Supersedes: N/A

## 📇Topics

- RFC #0000 Cluster Deployment for OpenIMSDK
  - [Meta](#meta)
  - [Summary](#summary)
  - [Definitions](#definitions)
  - [Motivation](#motivation)
  - [What it is](#what-it-is)
  - [How it Works](#how-it-works)
  - [Migration](#migration)
  - [Drawbacks](#drawbacks)
  - [Alternatives](#alternatives)
  - [Prior Art](#prior-art)
  - [Unresolved Questions](#unresolved-questions)
  - [Spec. Changes (OPTIONAL)](#spec-changes-optional)
  - [History](#history)

## Summary

This proposal aims to provide a streamlined approach for deploying OpenIMSDK in a cluster environment, considering multiple deployment strategies, including but not limited to helm, sealos, and k3s.

## Definitions

- **Cluster**: A set of computers that work together to run a set of applications.
- **Kubernetes (K8s)**: An open-source system for automating deployment, scaling, and management of containerized applications.
- **Helm**: A package manager for Kubernetes.
- **Sealos**: An efficient Kubernetes installer.

## Motivation

- To streamline and standardize the OpenIMSDK deployment in various cluster environments.
- To leverage the scalability, redundancy, and high availability offered by cluster deployments.
- To provide clear documentation and guidance for deploying OpenIMSDK in a cluster.

## What it is

This feature aims to provide a guideline and tools required to deploy OpenIMSDK in a cluster. Target personas include OpenIMSDK developers, platform operators, and users who wish to deploy OpenIMSDK in a scalable and efficient manner.

## How it Works

1. **K8s Environment Setup**: Choose the desired cluster setup tool, such as k3s, sealos, or helm. Set up the cluster according to the respective tool's documentation.
2. **Service Deployment**: Deploy OpenIMSDK server components followed by chat components using the respective Kubernetes configurations.
3. **Configuration & Environment Variables**: Adjust configuration files and environment variables based on the deployment environment and requirements.
4. **Scaling & Load Balancing**: Based on demand, scale the services either manually or automatically using Kubernetes' horizontal pod autoscaler.
5. **Monitoring & Logging**: Use tools like Prometheus and Grafana to monitor the health and performance of the services.

## Migration

Users currently running OpenIMSDK in non-clustered environments can migrate their data to the new cluster environment. Detailed steps will be provided, including backup, transfer, and restore procedures.

## Drawbacks

- Increased complexity in setup and maintenance.
- Requires expertise in Kubernetes and the chosen cluster deployment tools.

## Alternatives

- Continue to support traditional non-cluster deployments.
- Explore other cloud-native deployment tools beyond the mentioned in this proposal.

## Prior Art

Several contributors and even the official team have previously provided cluster deployment solutions:

- [k8s-jenkins](https://github.com/OpenIMSDK/k8s-jenkins)
- [Open-IM-Server-k8s-deploy](https://github.com/OpenIMSDK/Open-IM-Server-k8s-deploy)
- [openim-charts](https://github.com/OpenIMSDK/openim-charts)
- [deploy-openim](https://github.com/showurl/deploy-openim)

## Unresolved Questions

- Which deployment strategy is the most efficient and reliable for OpenIMSDK?
- How do we ensure a seamless migration experience for users transitioning from a non-clustered to a clustered environment?

## Spec. Changes (OPTIONAL)

There may be a need to introduce new configurations or environment variables specific to clustered deployments. This section will be updated as these changes are identified during the implementation phase.

## History

+ https://github.com/OpenIMSDK/Open-IM-Server/issues/601

**Fix Issue:** 
+ https://github.com/OpenIMSDK/Open-IM-Server/issues/688
+ https://github.com/OpenIMSDK/Open-IM-Server/issues/621
+ https://github.com/OpenIMSDK/Open-IM-Server/issues/459
