

Intro
-------


 eQuest is the world's largest job delivery company, providing global job posting distribution and recruitment services.

(It does
 *not*
 have anything to do with horses. )


 You connect to your eQuest account in the Data Center. This topic discusses the fields and menus that are specific to the eQuest connector user interface. General information for adding DataSets, setting update schedules, and editing DataSet information is discussed in

a DataSet Using a Data Connector

.


 Prerequisites
---------------

To connect to your eQuest account and create a DataSet, you must have an eQuest API key. For instructions on obtaining an API key, visit

https://support.equest.com/index.php...b.page&id=3991

.


 Connecting to Your eQuest Account
-----------------------------------


 This section enumerates the options in the
 **Credentials**
 and
 **Details**
 panes in the eQuest Connector page. The components of the other panes in this page,
 **Scheduling**
 and
 **Name & Describe Your DataSet**
 , are universal across most connector types and are discussed in greater length in

Adding a DataSet Using a Data Connector

.


###

Credentials Pane


 This pane contains fields for entering credentials to connect to your eQuest account. The following table describes what is needed for each field:


|

Field

|

Description

|
| --- | --- |
|
 API Key
  |
 Enter your eQuest API key. For instructions on obtaining an API key, visit

https://support.equest.com/index.php...b.page&id=3991

.
  |


 Once you have entered valid eQuest credentials, you can use the same account any time you go to create a new eQuest DataSet. You can manage connector accounts in the
 **Accounts**
 tab in the Data Center. For more information about this tab, see

Managing User Accounts for Connectors

.


###
 Details Pane

This pane contains menus for selecting your report type and the desired date or date range.


 Menu
  |
 Description
  |
| --- | --- |
|
 Report
  |
 Select the eQuest report you want to run. Currently only a single report is available.


|  |  |
| --- | --- |
|
 Job Postings
  |
 Returns a list of eQuest job postings for the specified timeframe.
  |

|
|
 Duration
  |
 Select whether you want to pull data for a specific date or a date range.
  |
|
 Report Date
  |
 Select whether the report data is for a specific date or for a relative number of days back from today.
  |
|
 Select Specific Date
  |
 Select the date for the report.
  |
|
 Days Back
  |
 Enter the number of past days that should appear in the report.
  |
|
 Start Date
  |
 Specify whether the first date in your date range is a specific or relative date. You select the last date in your range in
 **End Date**
 .
  |
|
 End Date
  |
 Specify whether the second date in your date range is a specific or relative date. You select the first date in your range in
 **Start Date**
 .
  |
|
 Select Specific Start Date
  |
 Select the first date in your date range.
  |
|
 Select Specific End Date
  |
 Select the second date in your date range.
  |
|
 Days Back to Start From
  |
 Enter the number of the farthest day back that should be represented in the report. Combine with
 **Days Back to End At**
 to create a range of represented days.


 For example, if you entered

10

for
 **Days Back to Start From**
 and

5

for
 **Days Back to End At**
 , the report would contain data for 10 days ago up until 5 days ago.
  |
|
 Days Back to End At
  |
 Enter the number of the most recent day back that should be represented in the report. Combine with
 **Days Back to Start From**
 to create a range of represented days.


 For example, if you entered

10

for
 **Days Back to Start From**
 and

5

for
 **Days Back to End At**
 , the report would contain data for 10 days ago up until 5 days ago.
  |


###
 Other Panes

For information about the remaining sections of the connector interface, including how to configure scheduling, retry, and update options, see

a DataSet Using a Data Connector

.


 FAQ
-----


####
 How often can data be updated?

As often as once an hour.

###
 Are there any API limits I should be aware of?

EQuest does not document rate limits in its API.
