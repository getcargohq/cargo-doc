# Table of contents

## Getting started

* [🎉 Welcome to Cargo](README.md)
* [⭐ Set up your Cargo in 5 mins](getting-started/set-up-your-cargo-in-5-mins.md)
* [🧢 Basic concepts](getting-started/basic-concepts.md)
* [⚙ Advanced concepts](getting-started/advanced-concepts.md)

## Use Cases

* [🏎 PLG: Entity-level scoring](use-cases/plg-entity-level-scoring.md)
* [🤼 Outbound: Enrich accounts to find stakeholders](use-cases/outbound-enrich-accounts-to-find-stakeholders.md)
* [🔔 Inbound: Inbound leads routing](use-cases/inbound-inbound-leads-routing.md)
* [⛹♀ PLS: Spotting decision makers in your free trial signups with AI](use-cases/pls-spotting-decision-makers-in-your-free-trial-signups-with-ai.md)
* [🏹 PLS: Enrich, summarise and route a lead to your sales rep](use-cases/pls-enrich-summarise-and-route-a-lead-to-your-sales-rep.md)

## Expressions

* [⚙ Introduction](expressions/introduction.md)
* [🧢 Expressions 101](expressions/expressions-101/README.md)
  * [🧾 Javascript snippets](expressions/expressions-101/javascript-snippets.md)
* [🤖 Write AI prompts](expressions/write-ai-prompts.md)
* [👩💻 Use JS in Cargo](expressions/use-js-in-cargo.md)
* [🤸♂ Use recipes from our community](expressions/use-recipes-from-our-community.md)

## Storage

* [⚙ Introduction](storage/introduction.md)
* [🏛 Setup a system of record](storage/setup-a-system-of-record/README.md)
  * [Use Cargo on Snowflake](storage/setup-a-system-of-record/snowflake.md)
  * [Use Cargo on PostgreSQL](storage/setup-a-system-of-record/snowflake-1.md)
  * [Use Cargo on Google BigQuery](storage/setup-a-system-of-record/bigquery.md)
  * [Use Cargo on AWS Redshift](storage/setup-a-system-of-record/redshift.md)
  * [Use Cargo's Postgres Instance](storage/setup-a-system-of-record/postgres.md)
  * [Use Cargo's Snowflake instance](storage/setup-a-system-of-record/postgres-1.md)
* [📤 Load your datasets](storage/postgres.md)
* [🗃 Creating entities in Cargo](storage/creating-entities-in-cargo.md)
* [🔁 Relationships](storage/relationships.md)
* [📊 Columns](storage/columns/README.md)
  * [🔧 Add new columns to your entity](storage/columns/add-new-columns-to-your-entity.md)
  * [🔜 Adding metrics columns](storage/columns/adding-metrics-columns.md)

## Segmentation

* [⚙ Introduction](segmentation/introduction.md)
* [🧢 Filtering 101](segmentation/filtering-101.md)
* [💠 One to many relationship filters](segmentation/one-to-many-relationship-filters.md)
* [🕊 Activity filters](segmentation/activity-filters.md)
* [👂 Segment change triggers](segmentation/segment-change-triggers.md)

## Orchestration

* [🖌 Using the Workflow Editor](orchestration/using-the-workflow-editor.md)
* [✨ Nodes 101](orchestration/nodes-101/README.md)
  * [🕐 Delay](orchestration/nodes-101/delay.md)
  * [🍕 Split](orchestration/nodes-101/split.md)
  * [🔎 Entity lookup](orchestration/nodes-101/entity-lookup.md)
  * [📍 Entity upsert](orchestration/nodes-101/entity-upsert.md)
  * [🔆 Enrichment](orchestration/nodes-101/enrichment.md)
  * [🛣 Routing](orchestration/nodes-101/routing.md)
  * [💯 Scoring](orchestration/nodes-101/scoring.md)
  * [👨🏫 Round robin](orchestration/nodes-101/round-robin.md)
  * [🪃 Variables](orchestration/nodes-101/variables.md)
  * [📤 Load](orchestration/nodes-101/load.md)
  * [🦳 Memory](orchestration/nodes-101/memory.md)
* [🚀 Triggering a workflow](orchestration/triggering-a-workflow/README.md)
  * [🚽 Push all segment records](orchestration/triggering-a-workflow/push-all-segment-records.md)
  * [🚽 Push all entity records](orchestration/triggering-a-workflow/push-all-entity-records.md)
  * [⏱ Real time webhooks](orchestration/triggering-a-workflow/real-time.md)
* [📕 Workflow versioning](orchestration/workflow-versioning.md)

## Integrations

* [📖 Integrations catalog](integrations/integrations-catalog/README.md)
  * [🪅 Salesforce](integrations/integrations-catalog/salesforce.md)
  * [🪅 Hubspot](integrations/integrations-catalog/hubspot.md)
  * [🪅 Pipedrive](integrations/integrations-catalog/pipedrive.md)
  * [🎱 Slack](integrations/integrations-catalog/slack.md)
  * [🌐 HTTP](integrations/integrations-catalog/http.md)
  * [🍧 Customer.io](integrations/integrations-catalog/customerio.md)
  * [🧮 Google sheets](integrations/integrations-catalog/clearbit/google-sheets.md)
  * [📤 Sendgrid](integrations/integrations-catalog/sendgrid.md)
  * [📤 Lemlist](integrations/integrations-catalog/lemlist.md)
  * [📤 LaGrowthMachine](integrations/integrations-catalog/lagrowthmachine.md)
  * [📤 Salesloft](integrations/integrations-catalog/salesloft.md)
  * [📤 Snov](integrations/integrations-catalog/snov.md)
  * [📤 OneSignal](integrations/integrations-catalog/onesignal.md)
  * [📤 Captain data](integrations/integrations-catalog/captain-data.md)
  * [🔭 Clearbit](integrations/integrations-catalog/clearbit.md)
  * [🔭 Outreach](integrations/integrations-catalog/outreach.md)
  * [🔭 Apollo.io](integrations/integrations-catalog/apolloio.md)
  * [🔭 Zoominfo](integrations/integrations-catalog/zoominfo.md)
  * [🔭 Cognism](integrations/integrations-catalog/cognism.md)
  * [🔭 Waterfall](integrations/integrations-catalog/waterfall.md)
  * [🔭 People Data Labs](integrations/integrations-catalog/people-data-labs.md)
  * [🔭 Lusha](integrations/integrations-catalog/lusha.md)
  * [🚓 Hunter](integrations/integrations-catalog/hunter.md)
  * [🚓 ZeroBounce](integrations/integrations-catalog/zerobounce.md)
  * [🚓 NeverBounce](integrations/integrations-catalog/neverbounce.md)

***

* [Old](old/README.md)
  * [⚙ Copy of Advanced concepts](old/copy-of-advanced-concepts.md)
  * [🎉 Copy of Basic concepts](old/copy-of-basic-concepts.md)
  * [⭐ Copy of How Cargo Works](old/copy-of-how-cargo-works.md)
