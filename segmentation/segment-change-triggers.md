---
description: >-
  Segments aren't just static groups; they're continuously evolving based on the
  underlying data.
---

# 👂 Segment change triggers

Navigate to the 'Changes' view on your segment to observe the additions, updates, and removals from the Segment:

<figure><img src="../.gitbook/assets/Segment changes.gif" alt=""><figcaption></figcaption></figure>

Here's what those three indicators means:

### **New Record Additions:**&#x20;

Whenever a new record that meets the criteria of your segment is added to the dataset or entity, the segment updates to include this record. For instance, if you have a segment for "New Users," it will automatically include users who've just signed up.

### **Property Updates of Records:**&#x20;

Sometimes, existing records undergo changes that might move them in or out of a segment. For example, if you have a segment tracking "Active Users," and a user goes from being inactive to active, they'll now be included in this segment. Conversely, if they become inactive, they'll be removed.

### **Record Removals:**

&#x20;If a record that was previously part of a segment gets deleted from the dataset or entity, the segment updates to exclude this record. This ensures that your segments remain relevant and don't include phantom or obsolete data.



**Note**: See here for a tutorial on [how to trigger your workflows in Cargo as a function](https://docs.getcargo.io/orchestration/triggering-a-workflow) of these changes

