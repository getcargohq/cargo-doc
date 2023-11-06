---
description: >-
  This section explains how to use a group node to parse multiple elements in an
  array inside a Cargo workflow
---

# ↘ Group node

You find yourself in the following situation:

* You used a node (e.g. a People Data Labs search) that produces an array with multiple elements inside
* You need to perform an operation on each of these elements programmatically (as you would inside a function when coding)

This is where you should use the group node. The alternative would be to treat every element in the array one-by-one.\


**How to use it:**

1. Insert a Group node after the node producing the array _(PDL - Search in the example below)_
2. Within the expression, define where the array is found _(\{{nodes.node\_1\}} in the example below)_
3. Click on the expand window section at the bottom of the group node, which will open a sub-workflow window
4. The sub-workflow works exactly as a normal worfklow, except that the objects in the start node represent the elements in the array, defined in the Step 2

<figure><img src="../../.gitbook/assets/Group workflows.gif" alt=""><figcaption></figcaption></figure>
