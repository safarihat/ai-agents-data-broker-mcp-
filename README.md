# ai-agents-data-broker-mcp-
ai agent broker

 Broker — AI-Native Data Intelligence
  
  MCP server delivering government procurement intelligence, corporate registries, director networks, patent
  data, and entity risk scores to AI agents at runtime.
  
  ## Connect
  
  ```json
  {
    "mcpServers": {
      "broker": {
        "url": "https://ai-agents-data.com/mcp",
        "headers": {
          "Authorization": "Bearer YOUR_API_KEY"
        }
      }
    }
  }
  
  Data Coverage
  
  - 50,000+ US federal contract awards (USASpending.gov, FY2024)
  - 200+ UK government contracts (Contracts Finder)
  - 15 UK company registrations (Companies House)
  - 13 company directors with appointment history
  - 10,000+ resolved canonical entities with cross-source linkage
  - Semantic vector search across all contracts (384-dim embeddings)
  - Apache AGE knowledge graph for director network traversal
  
  Tools
  
  ┌──────────────────────┬────────────┬───────────────────────────────────────────────────────────┐
  │ Tool                 │ Tier       │ Description                                                      │
  ├──────────────────────┼────────────┼──────────────────────────────────────────────────────────────────┤
  │ search_contracts     │ free       │ Keyword and semantic search across government contracts          │
  ├──────────────────────┼────────────┼──────────────────────────────────────────────────────────────────┤
  │ filter_contracts     │ free       │ Filter by value, date, jurisdiction, supplier                    │
  ├──────────────────────┼────────────┼──────────────────────────────────────────────────────────────────┤
  │ get_contract_detail  │ standard   │ Full contract record with entity linkage                         │
  ├──────────────────────┼────────────┼──────────────────────────────────────────────────────────────────┤
  │ search_patents       │ standard   │ Search patent titles and abstracts by keyword or assignee        │
  ├──────────────────────┼────────────┼──────────────────────────────────────────────────────────────────┤
  │ get_director_network │ enterprise │ Graph traversal of director appointments to depth 2              │
  ├──────────────────────┼────────────┼──────────────────────────────────────────────────────────────────┤
  │ cross_reference      │ enterprise │ Full entity profile: contracts, companies, directors,            │
  │                      │            │ enforcement, trends                                              │
  ├──────────────────────┼────────────┼──────────────────────────────────────────────────────────────────┤
  │ get_risk_score       │ enterprise │ Composite risk score from enforcement history, network           │
  │                      │            │ complexity, concentration                                        │
  ├──────────────────────┼────────────┼──────────────────────────────────────────────────────────────────┤
  │ health_check         │ enterprise │ Platform status and last ingestion timestamps                    │
  └──────────────────────┴────────────┴──────────────────────────────────────────────────────────────────┘
  
  Pricing
  
  ┌────────────┬─────────────────────┬───────────────────────────────────────┐
  │ Tier       │ Price               │ Access                                │
  ├────────────┼─────────────────────┼───────────────────────────────────────┤
  │ Free       │ £0 (10 queries/day) │ search_contracts, filter_contracts    │
  ├────────────┼─────────────────────┼───────────────────────────────────────┤
  │ Standard   │ £299/month          │ + get_contract_detail, search_patents │
  ├────────────┼─────────────────────┼───────────────────────────────────────┤
  │ Enterprise │ £999/month          │ All tools                             │
  └────────────┴─────────────────────┴───────────────────────────────────────┘
  
  Get Access
  
  Email access@ai-agents-data.com (mailto:access@ai-agents-data.com)
  
  Standard and enterprise keys issued within 24 hours. Free tier available on request.
  
  Example Queries
  
  Search contracts by meaning (semantic):
  
  search_contracts(query="cybersecurity network defense", semantic=true)
  
  Filter by buyer and value:
  
  filter_contracts(buyer_name="Department of Defense", min_value=1000000)
  
  Cross-reference an entity:
  
  cross_reference(entity_id="<uuid>")
  → Returns: contracts, company registrations, directors, enforcement actions, monthly trends
  
  Director network traversal:
  
  get_director_network(entity_id="<uuid>", depth=2)
  → Returns: directors of the company + other companies those directors are linked to
  
  Technical Details
  
  - Protocol: Model Context Protocol (MCP)
  - Transport: HTTP + SSE
  - Auth: Bearer token (API key)
  - Rate limits: Per-tier (free: 10/day, standard: 60/min, enterprise: 120/min)
  - Data refresh: Daily ingestion pipelines
  - Entity resolution: Fuzzy name matching with confidence scores
  - Search: Full-text (PostgreSQL GIN) + semantic (pgvector cosine similarity)
  
  Status
  
  Live and accepting connections
