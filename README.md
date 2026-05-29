# Snowflake Horizon Managed Connector

A managed connector for [Google Cloud Knowledge Catalog](https://cloud.google.com/dataplex/docs/knowledge-catalog-overview) that extracts both structural and governance metadata from Snowflake.

## What It Does

Connects to a Snowflake database, extracts metadata, and imports it into Knowledge Catalog as catalog entries:

| Metadata Type | Source | Entry Type |
|---|---|---|
| Database structure | INFORMATION_SCHEMA.TABLES | `snowflake-database`, `snowflake-schema` |
| Table/view columns | INFORMATION_SCHEMA.COLUMNS | `snowflake-table`, `snowflake-view` |
| Governance tags | ACCOUNT_USAGE.TAGS | `snowflake-tag` |
| Tag assignments | INFORMATION_SCHEMA.TAG_REFERENCES | `snowflake-tag-ref` |

## Based On

This project is based on the [community Snowflake connector](https://github.com/GoogleCloudPlatform/cloud-dataplex/tree/main/managed-connectivity/community-contributed-connectors/snowflake-connector) for Google Cloud Dataplex, originally developed by Google LLC. See [NOTICE](NOTICE) for attribution details.

Key additions:
- Horizon governance metadata (tags and tag references)
- Real-time tag reference extraction via INFORMATION_SCHEMA
- Data type mapping with semi-structured type fallbacks
- Cloud Workflows pipeline with error handling and retry logic
- Explicit Snowflake role support

## Status

🚧 Under development. See [Issues](../../issues) for the implementation roadmap.
