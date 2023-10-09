# 🤼 Outbound: Enrich accounts to find stakeholders

Multi-stakeholder outbound sequences are proven to be more effective than single-stakeholder reach outs. By the end of this tutorial, you will be able to enrich a segment containing accounts to identify stakeholders with specific job titles, and then crafted ensuring the right outreach for each.



## **Step 1: Construct a Segment with the Correct Filters**

**Outcome:** Your goal here is to have a precise segment of accounts, with the right filters applied, making sure there’s a column containing a company domain.

* Navigate to the ‘Entities’ section within your Cargo workspace
* If you need to apply filters to narrow down the accounts to the relevant ones
* Ensure that your segment has a column designated for 'company domain'. We’ll use this as the primary identifier to enrich these accounts later.



## Step 2: Push Records to a Workflow

**Outcome**: Once setup, your segment will automatically push the relevant records to the workflow as a function of your record enrolment rules (see workflows section)

* In the ‘Workflows’ section, create a new workflow based on the ‘Accounts’ entity (or the relevant one in your case)

### Step 3: Use Data Provider to Find Stakeholders

**Outcome:** Use Apollo (or your favourite data provider) to enrich company domain information to find a list stakeholders that match a predefined list of job titles.

* Inside the workflow you’ve set up (see the section on Workflows to learn how this works), you can inspect a test sample coming from your segment
* Add a new Apollo - Search node from the nodes catalog
* Configure the action to use the 'company domain' from the records to search for stakeholders with the specified job titles
* If Apollo is successful in enriching the account with the provided details, it should display an ‘Out’ display, with each stakeholder being a data object in the resulting output
* Use a filter node to continue the workflow only if the results from Apollo are not empty

### Step 4: Index the Found Employee Profiles

**Outcome**: The enriched employee profiles obtained need to be indexed and allocated to a specific outreach route, each designed for different job titles like founder, revenue operations manager, and head of data.

* After retrieving the employee profiles, create branches within the workflow for each job title you are targeting using a switch branch
* Assign the appropriate outreach route to each branch, ensuring that the messaging is adapted to the respective stakeholder's role
* Assign the appropriate outreach route to each branch, ensuring that the messaging is adapted to the respective stakeholder's role
