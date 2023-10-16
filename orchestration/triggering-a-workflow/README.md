# 🚀 Triggering a workflow

## Test your workflow before deploying it



Choose a test sample by clicking on the start icon and then **Change test sample.** You can apply filters until you get to the record that is suitable for your workflow

<figure><img src="../../.gitbook/assets/Test sample.gif" alt=""><figcaption></figcaption></figure>

Play workflow using the chosen test sample:

<figure><img src="../../.gitbook/assets/Play workflow.gif" alt=""><figcaption></figcaption></figure>



## Deploy to automatically enrol records from your segment



Before deploying, choose the right enrolment conditions so that the workflow triggers for the right kind of records.

#### **Change kinds**

* **Added**: Trigger on records that have been freshly added to the segment
* **Updated:** Trigger on records that have one of their attributes updated&#x20;
* **Removed:** Trigger on records that have been removed from the segment

#### **Run creation rule**

* **Always enroll**: Always triggers on records from the segment even if it has already been treated
* **Enroll once**: Skip records from the segment if it has already been treated
* If is **not currently enrolled:** Skip records if they are currently in the process of being treated by the workflow

<figure><img src="../../.gitbook/assets/Enrolment rules.gif" alt=""><figcaption></figcaption></figure>

Deploy, name and enable your workflow to enable it to automatically enrol records when the segment changes

<figure><img src="../../.gitbook/assets/Deploy and enable workflow.gif" alt=""><figcaption></figcaption></figure>



