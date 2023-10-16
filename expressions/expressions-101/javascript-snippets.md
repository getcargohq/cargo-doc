# 🧾 Javascript snippets

### **Base Search Check**

```
{{!!nodes.base_search}}
```

**Use Case**: This simple expression evaluates whether any records were returned from the node base\_search. It can be used as a condition to trigger further actions



### **Meeting Date Comparison**

```
{{ new Date(nodes.disco_meeting_date[0].salesforce_lead_disco_meeting_date) < new Date(new Date().setFullYear(new Date().getFullYear() - 1))  }}
```

**Use Case**: This expression compares a Salesforce lead's discovery meeting date with the current date minus one year. It can be used to identify leads that haven't had a meeting in the last year, potentially requiring follow-up or nurturing



### **LinkedIn Profile Check**

```
{{!!nodes.captain_data.items?.[0]?.link?.includes("linkedin.com")}}
```

**Use Case**: This expression checks if the first item in the `captain_data` array contains a LinkedIn profile link. It returns `true` if a LinkedIn link is found, facilitating targeted networking or outreach based on LinkedIn profiles



### **HubSpot ID Matching**

```
{nodes.teams.teams.find((t) => t.Hubspot_ID === nodes.crm_check[0].properties.hubspot_owner_id)}}
```

**Use Case**: This expression searches for a team in the a local variable whose `Hubspot_ID` matches the `hubspot_owner_id` of the first item in `crm_check`. It can help associate teams with specific HubSpot owners for further analysis or actions



### **Hubspot Owner ID Filtering**

```
{{!nodes.find_owners[0].properties.hubspot_owner_id && nodes.find_owners[0].properties.hubspot_owner_id != 254503852 && nodes.find_owners[0].properties.hubspot_owner_id != 241406601}}
```

**Use Case**: This expression checks conditions related to the `hubspot_owner_id` property of the first item in `find_owners`. It can filter out specific owner IDs from further processing, ensuring that certain actions are not taken for specific owners



### **Google Custom Search URL**

```
https://www.googleapis.com/customsearch/v1?key=AIzaSyA8LB9Lsitr9qklBUs_fG_8U5Lx1vlt2xM&cx=2176636b3a801449c&q={{nodes.start.firstname}} {{nodes.start.lastname}} {{nodes.start.company}} linkedin&num=1
```

**Use Case**: This expression generates a Google Custom Search URL by combining Cargo data (`nodes.start.firstname`, `nodes.start.lastname`, `nodes.start.company`) with the search query "linkedin." It allows you to automate LinkedIn profile searches

