# Table of contents

* [🎉 Introduction](README.md)
  * [⭐ Getting Started](introduction/getting-started/README.md)
    * [🤖 AI powered](introduction/getting-started/ai-powered.md)
    * [✍ Syntax](introduction/getting-started/syntax.md)
    * [⚙ Architecture](introduction/getting-started/architecture.md)

## 🏢 System of record (use your warehouse)

* [Use Cargo on Snowflake](system-of-record-use-your-warehouse/snowflake.md)
* [Use Cargo on Google BigQuery](system-of-record-use-your-warehouse/bigquery.md)
* [Use Cargo on AWS Redshift](system-of-record-use-your-warehouse/redshift.md)

## 🚠 System of record (use our warehouse)

* [Use Cargo's Postgres Instance](system-of-record-use-our-warehouse/postgres.md)
* [Copy of Use Cargo's Snowflake instance](system-of-record-use-our-warehouse/postgres-1.md)

## 🗃 Load your datasets

* [Load your datasets](load-your-datasets/postgres.md)
* [Real time webhooks](load-your-datasets/real-time.md)
* [Integrations catalog](load-your-datasets/integrations-catalog/README.md)
  * [Salesforce](load-your-datasets/integrations-catalog/salesforce.md)
  * [OneSignal](load-your-datasets/integrations-catalog/onesignal.md)
  * [Hubspot](load-your-datasets/integrations-catalog/hubspot.md)
  * [Sendgrid](load-your-datasets/integrations-catalog/sendgrid.md)
  * [Lemlist](load-your-datasets/integrations-catalog/lemlist.md)
  * [LaGrowthMachine](load-your-datasets/integrations-catalog/lagrowthmachine.md)
  * [Captain data](load-your-datasets/integrations-catalog/captain-data.md)
  * [Slack](load-your-datasets/integrations-catalog/slack.md)
  * [Clearbit](load-your-datasets/integrations-catalog/clearbit/README.md)
    * [Google sheets](load-your-datasets/integrations-catalog/clearbit/google-sheets.md)
  * [Outreach](load-your-datasets/integrations-catalog/outreach.md)
  * [Salesloft](load-your-datasets/integrations-catalog/salesloft.md)
  * [HTTP](load-your-datasets/integrations-catalog/http.md)
  * [Pipedrive](load-your-datasets/integrations-catalog/pipedrive.md)
  * [Customer.io](load-your-datasets/integrations-catalog/customerio.md)
  * [Apollo.io](load-your-datasets/integrations-catalog/apolloio.md)
  * [Zoominfo](load-your-datasets/integrations-catalog/zoominfo.md)
  * [Cognism](load-your-datasets/integrations-catalog/cognism.md)
  * [Waterfall](load-your-datasets/integrations-catalog/waterfall.md)
  * [People Data Labs](load-your-datasets/integrations-catalog/people-data-labs.md)

## 🚢 Entities

* [Creating entities in Cargo](entities/creating-entities-in-cargo.md)
* [Add new columns to your entity](entities/add-new-columns-to-your-entity.md)

## 🥍 Segments

* [Build a segment on your entity](segments/build-a-segment-on-your-entity.md)
* [Segment change triggers](segments/segment-change-triggers.md)
* [Filtering 101](segments/filtering-101.md)

## 🔫 WORKFLOWS

* [Using the Workflow Editor](workflows/using-the-workflow-editor/README.md)
  * [Nodes 101](workflows/using-the-workflow-editor/nodes-101/README.md)
    * [🕐 Delay](workflows/using-the-workflow-editor/nodes-101/delay.md)
    * [🍕 Split](workflows/using-the-workflow-editor/nodes-101/split.md)
    * [🔎 Entity lookup](workflows/using-the-workflow-editor/nodes-101/entity-lookup.md)
    * [📍 Entity upsert](workflows/using-the-workflow-editor/nodes-101/entity-upsert.md)
    * [🔆 Enrichment](workflows/using-the-workflow-editor/nodes-101/enrichment.md)
    * [🛣 Routing](workflows/using-the-workflow-editor/nodes-101/routing.md)
    * [💯 Scoring](workflows/using-the-workflow-editor/nodes-101/scoring.md)
    * [👨🏫 Round robin](workflows/using-the-workflow-editor/nodes-101/round-robin.md)
  * [Expressions 101](workflows/using-the-workflow-editor/expressions-101.md)
  * [Triggering a workflow](workflows/using-the-workflow-editor/triggering-a-workflow.md)
