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
1. [Role mapping resource properties](https://www.elastic.co/docs/deploy-manage/users-roles/cluster-or-deployment-auth/role-mapping-resources#mapping-roles-rule-field) 
1. Ideas to investigate
  1. [Group by function in Discover](https://discuss.elastic.co/t/group-by-function-in-discover/305922)
  1. [View field statistics](https://www.elastic.co/docs/explore-analyze/discover/show-field-statistics)
  1. [Using ES|QL](https://www.elastic.co/docs/explore-analyze/discover/try-esql)
1. [Elasticsearch Labs Blogs  - Video Tutorials](https://www.youtube.com/playlist?list=PL_mJOmq4zsHbjdYy9vzgZ2GljJXYhNWYa) YouTube playlist
1. Elastic RAG
  1. [How to Build a RAG Ready MCP Server with Elasticsearch Integration](https://www.youtube.com/watch?v=GMMx3g_Op5o)
  1. [Building an MCP server with Elasticsearch for real health data](https://www.elastic.co/search-labs/blog/how-to-build-mcp-server)
  1. [Welcome to FastMCP 2.0!](https://gofastmcp.com/getting-started/welcome)
  1. [Create a connector](https://URL/app/elasticsearch/content/connectors/select_connector)
  1. [crawler](https://github.com/elastic/crawler) on Elastic repo
  1. [elastic connectors for knowledge base markdown site](https://www.google.com/search?q=check+available+elastic+connectors+for+knowledge+base+markdown+site&sca_esv=78726570b3b899ae&rlz=1C1GCEU_enZA1040ZA1040&sxsrf=AE3TifOW9_USXhBwNpkBjDZ5iHnS1VUX3Q%3A1755779805762&ei=3RKnaPehLpKlhbIPz8WHsQE&ved=0ahUKEwi3hIG99ZuPAxWSUkEAHc_iIRYQ4dUDCBA&uact=5&oq=check+available+elastic+connectors+for+knowledge+base+markdown+site&gs_lp=Egxnd3Mtd2l6LXNlcnAiQ2NoZWNrIGF2YWlsYWJsZSBlbGFzdGljIGNvbm5lY3RvcnMgZm9yIGtub3dsZWRnZSBiYXNlIG1hcmtkb3duIHNpdGVIsw5Q9AFYxAxwAXgAkAEAmAGxAqABgAmqAQUyLTMuMbgBA8gBAPgBAZgCAKACAJgDAIgGAZIHAKAHyAOyBwC4BwDCBwDIBwA&sclient=gws-wiz-serp)
  1. [AI Assistant Knowledge Base](https://www.elastic.co/docs/solutions/security/ai/ai-assistant-knowledge-base)
  1. [mcp-server-elasticsearch](https://github.com/elastic/mcp-server-elasticsearch) repo
  1. [Content connectors](https://www.elastic.co/docs/reference/search-connectors)
  1. [connectors](https://github.com/elastic/connectors) repo
  1. [Connectors](https://www.elastic.co/docs/deploy-manage/manage-connectors) deploy and manage docs
  1. [Preconfigured connectors](https://www.elastic.co/docs/reference/kibana/connectors-kibana/pre-configured-connectors) docs
1. [Data Analysis with Kibana On-Demand](https://app.strigo.io/training/ondemand/nSWuMZ9ojsbgmchhe) workshop
