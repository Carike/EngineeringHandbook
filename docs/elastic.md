# Elastic

Learning more about Elastic and the Elastic Stack.

## Cluster management

- Cluster listing
  - Log stash must not be upgradred due to a depency on Twitter Package
- Cluster configuration to be documented
- JVM heap - ideally want 20%, if more than 70% result in trouble
- ElasticSearch nodes
  - Azure nodes ingesting and collect to be sent to on-prem
  - Other data centers
  - Warm, cold, hot, fleet & ML nodes?
- Lookup on the roles of the various nodes
- Ingest pipelines: data ingest and how much
- Cross Cluster Replication (CCR)
- Index management
  - Primary index & replica
  - Manages indexes - scale down
  - Remove replicas quickly need to make space
  - Index stays with the app
- Data streams
  - Runs continously, index create new on each day
  - Can setup data retention, see Index Lifestyle Management
  - Data retention edit policy: hot, warm, cold phases
  - Index lifecycle policesi - data you want but not use can go straight to cold storage. Skip hot & warm phases
- Data Classification:
  - what, 
  - temp level & 
  - keep time prior to deletion
    
## Learning Elastic

1. https://www.elastic.co/docs
1. https://www.elastic.co/getting-started/elasticsearch-relevance-engine-quick-start
1. [Continuous Integration and Continuous Delivery (CI/CD) monitoring](https://www.elastic.co/guide/en/observability/current/ci-cd-observability.html)
1. [Elastic Cloud Provider](https://registry.terraform.io/providers/elastic/ec/latest/docs) on Terraform Registry
1. [Demo](https://demo.elastic.co/)
1. [Demo gallery](https://www.elastic.co/demo-gallery)
  1. [Observability overview](https://www.elastic.co/demo-gallery/observability-overview)
  1. [Observability logs](https://www.elastic.co/demo-gallery/observability-logs)
1. [Getting started](https://www.elastic.co/getting-started)
1. [Elastic Search Labs Tutorials](https://www.elastic.co/search-labs/tutorials)
  1. [Search tutorial)](https://www.elastic.co/search-labs/tutorials/search-tutorial/welcome)