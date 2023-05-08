---
description: This section gets you up and running with building workflows in Cargo
---

# ⭐ Getting Started

### Create a Workspace

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-07 à 15.54.34.png" alt=""><figcaption></figcaption></figure>

### Setup a system of record _(Optional)_

_If you don't have a system of record to link to, you can directly skip this step and jump to the connector section below._

<figure><img src=".gitbook/assets/Capture d’écran 2023-05-07 à 16.10.21.png" alt=""><figcaption><p><em>CDW setup instructions</em></p></figcaption></figure>

1. If you want to plug Cargo on top of your data warehouse, Click on 'Settings' in the side bar
2. Select the system of record to connect to: [Redshift](workspaces/redshift.md), [Snowflake](workspaces/snowflake.md) or [Bigquery](http://localhost:5000/o/4mORJs1gC0yIX9GWp4Rp/s/xm3PV8WN8Sxx6tS7U2FC/).
3. Follow the corresponding instructions. This step is often made with your data engineer.
4. Define the 'Sync Schedule' in the settings options. You can choose at custom interval, every 10 minutes, hours, daily and weekly.

### Define entities

Once your data warehouse setup, you need to define the different entities you want to work with.

1. Click on "Create" in the Entities section in the side bar
2. Follow the corresponding instructions for each entity
3. Explicit the relationships between each of your entity

### Add a Connector

1. Click on "Connectors" in the side bar
2. Select the applications to connect to&#x20;
3. Follow the corresponding instructions.

You can also plug a third party tool using the HTTP connector if there is no existing native application on Cargo.

### Choose data to engage

#### From a segment:

1. Click on the 'Segments' link in the side bar and click on 'Create'
2. Select the object/entity you would like narrow
3. If you explicited the relationships on the entity level, you can create segments leveraging the data from all defined entities.
4. You can mix 'AND' and 'OR' conditions to narrow your audience.
5. Save the segment&#x20;

#### From a webhook:

1. When Creating a workflow, Click on "Hook"&#x20;
2. You will get a webhook URL to use to connect your third party app
3. Create an API token and replace the placeholder at the end of the given webhook URL

### Create your first workflow

1. Click on the "workflow" link in the side bar and click on "Create"
2. Choose the trigger type: Segment based on your declared entities or Webhook
3. Give a name to your workflow
4. Choose the Run creation rule
5.  Start building your first workflow by adding a new action after the start: Click on "+", it opens the actions panel, where you can search or browse actions nodes.





