

Intro
-------

When setting up PDP (Personalized Data Permissions) policies on DataSets in Domo, you should be aware how those policies affect DataFlows and DataFusions.


 PDP with DataFlows
--------------------

Input DataSets in a DataFlow cannot be restricted by PDP policies—all available rows
 *must*
 pass through the DataFlow. Because of this you must apply PDP policies to the output DataSets generated by a DataFlow.


 When you build a DataFlow using an input DataSet with PDP policies in place, the DataFlow breaks unless at least one of the following criteria applies:

 You have an "Admin" security profile or a custom role with "Manage DataFlows" enabled.
* You are the DataSet owner.
* You are part of the "All Rows" policy. This gives you access to all of the rows in the DataSet.

If a DataFlow breaks as a result of PDP policies being applied to input DataSets, you can fix it by adding the owner to the "All Rows" policy as follows:

. Open the
 **Personalized Data Permissions**
 tab for the PDP-affected DataSet.
2. Click
 **Impact**
 .


 This opens the
 **PDP Outcomes for this DataSet**
 dialog, which lists all of the items in Domo that have been impacted as a result of PDP policies. For more information, see

Creating and Deleting PDP Policies

.
3. Click
 **Attention**
 .
4. In the list, locate the DataFlow you want to fix.
5. Click
 **Fix It**
 .

This adds the DataFlow owner to the "All Rows" policy for this DataSet. The DataFlow can now be run as normal.


 PDP with DataFusions
----------------------

PDP can be applied to both input and output DataFusion DataSets.


 If you are creating a DataFusion that includes one or more DataSets with PDP enabled, you must have "all rows" access for those DataSets.


 If the owner of a DataFusion loses access to one or more PDP-enabled input DataSets, the DataFusion will be disabled.

