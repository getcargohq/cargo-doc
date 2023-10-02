# Segment change triggers

Segments aren't just static groups; they're continuously evolving based on the underlying data.



Here's what they're always on the lookout for:

**1. New Record Additions:** Whenever a new record that meets the criteria of your segment is added to the dataset or entity, the segment updates to include this record. For instance, if you have a segment for "New Users," it will automatically include users who've just signed up.

**2. Property Updates of Records:** Sometimes, existing records undergo changes that might move them in or out of a segment. For example, if you have a segment tracking "Active Users," and a user goes from being inactive to active, they'll now be included in this segment. Conversely, if they become inactive, they'll be removed.

**3. Record Removals:** If a record that was previously part of a segment gets deleted from the dataset or entity, the segment updates to exclude this record. This ensures that your segments remain relevant and don't include phantom or obsolete data.

