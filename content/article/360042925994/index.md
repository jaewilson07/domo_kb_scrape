

Intro
-------

With DataSet Alerts, you can build flexible and powerful Alerts right on a DataSet. You can be Alerted based on
 *any*
 change or addition to your data. Unlike traditional Alerts, these can be built on multiple trigger rules. And the Alert message can include complex calculations and even data from other DataSets, making the custom message more customizable and more useful.


 For example, let's say user Barry is a sales manager for his company. He wants to know the exact moment that a new deal closes, along with any pertinent information about the deal, such as the salesperson who closed the deal, the name of the customer, the amount of the deal, the number of consulting hours purchased, and so on. Before DataSet Alerts, Barry could only set Alerts on the Card level. These Alerts would indicate that a predefined threshold had been surpassed but could not relay any other data from the DataSet. But now, with DataSet Alerts, Barry can set an Alert on the DataSet level. The Alert message can include
 *any*
 information from the DataSet, including all of the data Barry wanted.


 Barry's Alert message as created in Domo looks as follows:


`[Sales Rep], on the [Sales Team] team, closed a deal with [Account Name] for [Deal Amount]. This deal includes [# of Users] users and [# of Consulting Hours Purchased] consulting hours (at a rate of [Consulting Rate] per hour). The competitor for this deal was [Competitor Name]. This opportunity was created on [Opportunity Start Date] from a [Lead Type].`


 Thereafter, when a deal closes, the Alert message that is sent out is populated with the data from the indicated columns. This message might appear as follows:


 "Darcy McKay, on the Corporate team, closed a deal with Kablinko Toys for $23,560. This deal includes 12 users and 8 consulting hours (at a rate of $225 per hour). The competitor for this deal was Red Puffin Electronics. This opportunity was created on 08-12-2017 from a Marketing-generated Lead."


 You manage DataSet Alerts in the Alert Center, just as with Card Alerts. There you can edit rules and messages, change your notification settings, see the Alert history, share Alerts with other users, and subscribe to other DataSet Alerts. For more information about the Alert Center, see

Alert Center Layout

.

*Video - Using DataSet Alerts**

Creating a DataSet Alert
--------------------------

You create DataSet Alerts in the Data Center, in the

details view for the DataSet

. Click on
 **Alerts**
 in the details view tab bar to open the
 **Alerts**
 tab. This tab shows cards for all Alerts that have been created on this DataSet. You can click any Alert to open a panel in which you can edit the Alert, see its history, share it, and so on. In this tab you can also click
 **New Alert**
 to open the 3-step Alert wizard, where you can configure your new Alert. The steps in the wizard are as follows:

. **Rule.**
 Here you specify the conditions that trigger your Alert. You can also specify how often Domo checks to see if the Alert conditions have been met.
2. **Message**
 . Here you can customize the message for the Alert using a variety of different macros to indicate available metrics.
3. **Share**
 . Here you specify the users, groups, and Buzz conversations that receive notifications when the Alert is triggered.

All of these steps are described in more detail in continuation.

##
 Setting Up Your Alert Rule

In Step 1 of the wizard, you specify the conditions that cause your Alert to trigger. You can also set the frequency at which Domo checks to see if the Alert has triggered.


 If PDP policies have been set on this DataSet, you can specify how PDP is applied to Alerts in Step 1 of the wizard. For more information, see

PDP and Alerts

.

###
 Specifying the Alert Conditions

There are two types of DataSet Alerts: individual row Alerts and column aggregation Alerts. You select the type of Alert you want in the
 **Metric**
 menu in the
 **Rule**
 section of the Alert wizard.


#####
 Individual row Alerts

You can create Alerts that trigger when changes are made to individual rows in your DataSet. These changes include rows being added, changed, or deleted from the DataSet. For example, you might have an Alert set to trigger when a row for a new customer account is added to your sales DataSet.

*Note:**
 The following DataSet types do not support row Alerts:


* Fusions
* Views
* Appends
* Upserts
* Federated DataSets
* DataSets with more than 1M rows.

When you choose an individual row option, two additional configuration options appear. The first of these,
 **Add Filter**
 , is optional. Here, you can set your Alert to trigger
 *only*
 when specific rows are added, changed, or deleted. To do this, you choose the desired column in the
 **Metric**
 menu, select an operator in the
 **Meets this condition**
 menu, then enter or select the desired value in the
 **For this value**
 field. So for example, if user Fiona only wants to receive Alerts when the "Marketing" department is impacted, she would select
 **Department**
 in the first menu and
 **Is equal to**
**(=)**
 in the second menu, then check the box for "Marketing" in the blank field.


 You can add additional filters by clicking
 **Add Filter**
 .

By adding multiple filters, you can build complex Alert rules for your DataSets. For example, let's say I have a DataSet that includes rows for customer deals in the pipeline. I want to receive an Alert
 *only*
 when these three criteria are met:

 I have won the deal (indicated by the "isWon" column being set to "True").
* The deal was previously open (indicated by the "isClosed" column being previously set to "False").
* The deal is now closed (indicated by the "isClosed" column being now set to "True").

I could build a single rule incorporating all three of these criteria. by creating three separate filters, as follows:

The second option asks you to select one or more columns that identify a row in this DataSet as unique. In the previous example, I specified "AccountID" as this column because the account ID is unique for every row. Unlike the filters option, this is required to proceed.

####
 Column aggregation Alerts

Column aggregation Alerts occur when the aggregation for a column meets a specified threshold, just as with Card Alerts. For example, you might have an Alert set to trigger when the sum of the "Total Budget" column for your DataSet falls below a certain value.


 To build a column aggregation Alert, you first choose a column in the
 **Metric**
 menu, followed by the desired aggregation. Different aggregation types are available depending on the data type of the selected column.


 Available aggregations for string columns are as follows:

 **Unique Count**
 . The number of unique values in the column (i.e. if a value appears more than once, it is only counted once).
* **Null Count**
 . The number of NULL values in the column.
* **Non-null Count**
 . The number of non-NULL values in the column.
* **Total Count**
 . The total number of values in the column, including all null and non-unique values.
* **Minimum String Length**
 . The length in characters of the shortest string in the column.
* **Maximum String Length.**
 The length in characters of the longest string in the column.
* **Average String Length**
 . The average length of characters of all of the strings in the column.

Available aggregations for value and date columns are as follows:

 **Unique Count**
 . The number of unique values in this column (i.e. if a value appears more than once, it is only counted once).
* **Null Count**
 . The number of NULL values in the column.
* **Non-null Count**
 . The number of non-NULL values in the column.
* **Total Count**
 . The total number of values in the column, including all null and non-unique values.
* **Minimum**
 . The smallest value or earliest date in the column.
* **Maximum**
 . The largest value or latest date in the column.
* **Average**
 . The average value in the column.
* **Sum**
 . The sum of all of the values in the column.
* **Standard Deviation**
 . The standard deviation of the values in the column.
* **Median**
 . The median value in the column.
* **Lower Quartile**
 . The lower quartile for the column.
* **Upper Quartile**
 . The upper quartile for the column.

Once you choose the column and aggregation, you can build the conditional statement for the Alert. A conditional statement connects the selected metric to the value or percentage and determines when your Alert is sent. You choose the condition in the
 **Meets this condition**
 menu and enter the value in the
 **For this value**
 field. Domo provides a variety of conditions to choose from, including greater than, less than, and equal statements and combinations of these. You can also specify a particular degree of change using the
 **changes by**
 ,
 **increases by**
 , and
 **decreases by**
 condition statements.


 For example, if you wanted to create an Alert set to trigger when the total value of the "Budget" column fell below $10,000, you would do the following:

. Select "Budget" in the
 **Metric**
 menu, then choose
 **Sum**
 as the aggregation type.
2. Select
 **is less than (<)**
 in the
 **Meets this condition**
 menu.
3. Enter

10000

in the
 **For this value**
 field.


####
 Specifying the Alert Frequency

Also in step 1 of the Alert wizard, you can specify how often Domo checks to see if the Alert is in a triggered state. You do this by clicking the arrow at the bottom right of the configuration options and selecting the desired option.

Options include
 **Every time the data updates**
 ,
 **Hourly**
 ,
 **Daily**
 ,
 **Weekly**
 , and
 **Monthly**
 .

 If you select
 **Every time the data updates**
 , Domo checks the Alert any time the data in the card is refreshed.
* If you select
 **Hourly**
 or
 **Daily**
 , you can choose whether to include weekends in your evaluation. You can also set the specific time of day when you choose
 **Daily**
 .
* If you select
 **Weekly**
 , you can select the specific day of the week along with the time of day.
* If you select
 **Monthly**
 , you can select a specific date or the first/last day of the month, along with the time of day.

Depending on the Alert condition you've selected, a checkbox may also appear reading
 **Keep sending notifications while in a triggered state**
 . When this box is checked, instead of sending out a single Notification as soon as the Alert enters a triggered state (which is the default functionality), Domo sends out Notifications based on the selected frequency
 *until the Alert conditions are no longer met*
 . For example, let's say user Gus creates the Alert rule "Summary Number is less than 500," selects
 **Weekly**
 as the frequency, then checks this box. As soon as the Summary Number surpasses 500, a Notification is sent. Then, as long as the Summary Number remains above 500, new Notifications are sent on the specified weekday at the specified time. If the number drops below 500, Notifications will stop being sent. If, on the other hand, Gus doesn't check this box, only an initial Notification is sent when the Alert is triggered.


 The
 **Keep sending notifications while in a triggered state**
 checkbox appears only for threshold-based Alerts, as opposed to those one-time Alerts that trigger when a certain degree of change is met. For example, for an "Is greater than" Alert (e.g. an Alert that triggers when its value surpasses 1000), this box would be available because the Alert still applies as long as the value remains above the threshold. But for a "Changes by" Alert, the box is not available because once the given value is reached, only a single Notification needs be sent—the Alert's work is then done.

##
 Customizing Your Alert Message

In Step 2 of the wizard, you can customize the Notification message that is sent whenever the Alert is triggered. You can choose from a wide variety of macros to include in the message. Macros are used to reference different variables related to your Alert, such as Alert name, Alert owner, current or previous value of the rule column, the time the Alert was last triggered at, and so on. With individual row Alerts, you can configure the message header, body, and footer separately.

You can see a list of macros by clicking the
 **Metric**
 button. Where available, the list shows you the name of the corresponding variable in your Alert so you know if you are pulling over the right information.

If you edit the custom message then decide you want to revert it back to the default, you can do so by clicking
 **Restore Default**
 .

##
 Attaching an action

Alert Actions drive powerful action for your business by triggering events such as Webhook integration with third-party systems and Projects & Tasks integrations in Domo. You can attach an action to an Alert by clicking the
 **Attach Action**
 button below the message preview pane, choosing the action type (either a Webhook or Task), then configuring the action.

###
 Webhook actions

By attaching Webhook actions to Alerts, you can cause events to be triggered in third-party systems when your Alert threshold is attained. For example, as a CFO,  you might create a Webhook that causes a celebratory message to be posted to your company Facebook page when your stock value reaches a certain price.


 To create a Webhook action, all you need to do is input the Webhook URL, choose the HTTP API method (POST, DELETE, PATCH, GET, and PUT are available), then enter a secret authorization key if required. You cannot edit the Webhook body aside from the customized Alert message, which was discussed previously.


 After you have configured your action, you can test it by clicking
 **Send Test**
 .


**To configure a Webhook action,**

. Click the
 **Attach Action**
 button, which is located under the
 **Message**
 pane in the Alert Wizard.
2. Select
 **Domo Webhook**
 .
3. Enter the URL for the desired Webhook.
4. Select the desired HTTP method in the
 **Method**
 menu (
 **POST**
 is the default).
5. (Conditional) Enter an authorization key in the
 **Secret**
 field if necessary to authenticate.
6. (Conditional) If you didn't customize your Alert message previously, you can do this by clicking the arrow next to
 **Webhook body**
 , scrolling down to the bottom of the body content, then clicking the pencil to open the message editor. For more information about the options here, see

Customizing your Alert message

.
7. (Optional) Click
 **Send Test**
 if you want to test your configuration.
8. Click
 **Next**
 to move onto the next step in the wizard.


####
 Task creation action

You can cause a Task to be created when an Alert is triggered. You can choose the Project in which the new Task will be added, edit the customized Alert message if you haven't already, and select an owner for the new Task. As soon as the Alert threshold is reached, this new Task will be added to Domo and assigned to the owner you have selected. For more information about Projects and Tasks, see

Projects and Tasks

.


**To configure a Task action,**

. Click the
 **Attach Action**
 button, which is located under the
 **Message**
 pane in the Alert Wizard.
2. Select
 **Task**
 .
3. In the
 **Project**
 menu, select the Project where this Task should live.


 If the desired parent Project doesn't exist yet, you will need to create it. For more information, see

Creating a Project

.
4. (Conditional) If you didn't customize your Alert message previously, you can do this here by updating the fields in the
 **Task name**
 area as necessary. For more information about the options here, see

Customizing your Alert message

.
5. Select the desired Task owner in the
 **Owner**
 menu.
6. Click
 **Next**
 to move onto the next step in the wizard.


###
 Sharing the Alert

In Step 3 of the wizard, you can share Alerts with other users and/or groups in your Domo so they receive notifications every time that Alert triggers. You can also write a custom message to let users know what is happening as well as delete users and groups who should no longer be able to see the Alert. You can delete users and groups only if you have an "Admin" default security profile or a custom role with "Manage All Groups" enabled. For more information about default security profiles, see

Default Security Role Reference

. For more information about custom roles, see

Managing Roles

.


 You can also share Alerts in Buzz conversations, in which case all users following the conversation receive Notifications. You can search for conversations then select those conversations you want the Alert to be shared in. This search searches keywords from conversation names only; it does
 **not**
 search conversation content.


 Alerts are sent to the email address and telephone number specified in the user profile. For more information, see

Profile Page

.


 For information about configuring Notifications, see

Configuring Notification and Alert Settings

.


 When you share Alerts with other users in your Domo, they automatically gain access to the cards those Alerts are tied to if they do not already have it.

*Video - Sharing Alerts**

*To share an Alert with users and/or groups,**

. In the
 **Share this Alert**
 step of the Alert creation wizard, add a person or group to share with by clicking in the
 **Enter users, groups, or emails**
 field and selecting the desired user, group, or email.


 When you select a user or group, that user or group's name appears in the field. You can share with multiple users and/or groups by selecting all of their names and adding them to the field.
2. (Optional) Write a message in the "I thought you might find this interesting" field to let users know what is happening.
3. Click
 **Save**
 .

The Alert is shared with the selected users. If you wrote a Notification message, that message is sent to the users you shared with.


**To remove users or groups from the shared list for this Alert,**

. In the Details view for the card with the Alert, click the

icon to show the Alerts for this card.
2. Click the
 **Share**
 button for the Alert you want to remove users from.
3. Expand the section at the bottom of the dialog by clicking the message reading "Already shared with [person]."


 This displays rows for all users and/or groups the Alert is being shared with.
4. Remove a user or group from the shared list by clicking the "x" for that user or group.

The user or group is removed from the shared list and no longer receives Notifications when this Alert is triggered.


**To share an Alert in a Buzz channel,**

. In the
 **Share this Alert**
 step of the Alert creation wizard, click the
 **Buzz**
 tab.
2. (Optional) Use the
 **Filter Buzz channels and chats**
 field to search for conversations you want to share this Alert in.
3. Check the boxes for all conversations you want to share the Alert in.
4. Click
 **Share**
 .

The Alert is shared in the selected conversations. Any users following those conversations will now receive notifications any time the Alert is triggered.


 Saving your Alert
-------------------

After you've selected the desired Alert components and entered a value, click
 **Save**
 .


 Your new Alert now appears in the

Alert Center

. You can do any of the following with this Alert:

 Open it for editing.
* "Unsubscribe" from it so you do
 *not*
 receive Notifications when it is triggered. By default, when you create an Alert, you are set to follow it.
* See how many times it has been triggered.
* Delete it.
* Set instant, daily, or weekly notifications on the Alert.
* See a listing of Alert events.
* See a list of followers.

Editing an Alert
------------------

You can open an Alert for editing by doing any of the following:

 Select
 **Alerts**
 in the app toolbar at the top of the screen, locate the Alert you want to edit, click in the top portion of the Alert card, then click
 **E**
**dit**
 .
* Open the details view for the Alert in the Data Center then click the
 **Alerts**
 tab.


