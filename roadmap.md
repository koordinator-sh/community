# Roadmap

This document outlines the development roadmap for the Koordinator project.

## v1.8 Roadmap(WIP)
- Queue and Quota Management: Integrate Kube-Queue with Koordinator for comprehensive queue scheduling support ([#2662](https://github.com/koordinator-sh/koordinator/issues/2662))
- Queue and Quota Management: Support PreEnqueue and QueueHint in Quota plugin ([#2581](https://github.com/koordinator-sh/koordinator/issues/2581))
- Queue and Quota Management: Enhance Quota resource reclamation with PDB awareness ([#2651](https://github.com/koordinator-sh/koordinator/issues/2651))
- Task Scheduling: Discuss with upstream developers about how to support Coscheduling and find a more elegant way to solve the following problems
  - Addressing the issue in the current Coscheduling implementation where Pods are more likely to enter the BackoffQ ([#2559](https://github.com/koordinator-sh/koordinator/issues/2559))
  - Addressing the issue where PreEnqueue interception of Gang Pods prevents Pod events from being generated until the Gang MinMember requirement is met. ([#2480](https://github.com/koordinator-sh/koordinator/issues/2480))
  - Fix Nominated Node handling when Pod is gated during scheduler restart
  - Address GatedMetric Negative issues ([kubernetes#133464](https://github.com/kubernetes/kubernetes/issues/133464))
- Heterogeneous Scheduling Strategy: Consider GPU allocation in rescheduling for cluster resource consolidation ([#2332](https://github.com/koordinator-sh/koordinator/issues/2332))
- Heterogeneous Resources Scheduling: Introduce Dynamic Resource Allocation (DRA) framework support
- Heterogeneous Resources Scheduling: Expand support for more types of heterogeneous resources
- Infrastructure and Compatibility: Upgrade to Kubernetes 1.33
- Utils: Support PreAllocation in Reservation ([#2150](https://github.com/koordinator-sh/koordinator/issues/2150))
- Utils: Implement Pod scheduling audit for pods in schedulingQueue ([#2552](https://github.com/koordinator-sh/koordinator/issues/2552))
- Utils: Provide tooling for Pod scheduling audit analysis

## v1.3 Roadmap

- scheduling: network topology aware scheduling
- scheduling: improve Reservation for allocation strategies
- scheduling: NUMA topology aware scheduling
- scheduling: add ResourceSummary CRD to show the resource view of cluster
- slo: improve framework of interference detection
- slo: provide ability of blkio isolation

## v1.2 Roadmap

- koord-scheduler: retrieve reservationInfo from cache first in preFilter hook
- koord-scheduler: ElasticQuota Plugin need DecoratePod OnPodDelete
- koord-descheduler: support pod deletion cost and eviction cost
- koord-descheduler: limits frequently migrated workloads
- koordlet: Feat add more metrics for cpu burst and suppress
- koordlet: support cpu eviction in cpuset supress mode with cpu static policy
- koordlet: add metrics for batch resources

## v1.1 Roadmap

- api: add percentile node usage to NodeMetric
- koord-scheduler: LoadAware scheduling support percentile usage and load scheduling by Prod Pods
- koord-scheduler: NodeCPUBindPolicy supports SpreadByPCPUs
- koord-scheduler: ElasticQuota supports Decorator to decorate Node, Pod and ElasticQuota
- koord-descheduler: support loadaware/lowNodeLoad descheduling
- koordlet: node resource report and common QoS features support cgroups-v2
- koordlet: Other qos features support cgroups v2

## v1.0 Roadmap

- apis: support customizing different priority ranges
- add webhook and node topo feature gates control
- koord-scheduler: optimize ElasticQuota plugin's update logic
- koord-scheduler: improve nodeNUMAResource allowUseCPUSet and sortCPUsByRefCount
- koord-manager: support calculate batch resource based on memory request
- koordlet: CPI collector for Interference Detection
- koordlet: enable group identity by sysctl when cpu qos enabled
- runtime-proxy: Support hook server deployed by k8s pod

