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

* https://www.elastic.co/docs
* https://www.elastic.co/getting-started/elasticsearch-relevance-engine-quick-start
* [Continuous Integration and Continuous Delivery (CI/CD) monitoring](https://www.elastic.co/guide/en/observability/current/ci-cd-observability.html)
* [Elastic Cloud Provider](https://registry.terraform.io/providers/elastic/ec/latest/docs) on Terraform Registry
* [Demo](https://demo.elastic.co/)