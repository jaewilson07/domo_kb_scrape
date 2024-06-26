

Intro
-------

Twilio is a cloud communications company that allows developers to programmatically make and receive phone calls and send and receive text messages using its web service APIs. You can use the Domo Twilio connector to retrieve data on accounts, calls, conferences, notifications, SMS messages, and usage records. For more information about the Twilio API, go to

https://www.twilio.com/docs/api

.


 The Twilio connector is a "Cloud App" connector, meaning it retrieves data stored in the cloud. In the Data Center, you can access the connector page for this and other Cloud App connectors by clicking
 **Cloud App**
 in the toolbar at the top of the window.


 This version of the connector differs from the advanced version in that it provides no date filtering capabilities. It simply pulls in all available data. For information about the advanced version, see

Twilio Advanced Connector

.


 This topic discusses the fields and menus that are specific to the Twilio connector user interface. For general information about adding DataSets, setting update schedules, and editing DataSet information, see

Adding a DataSet Using a Data Connector

.

  |  |
| --- | --- |
|
**Primary Use Cases**
 |
 This connector is used for compiling reports about Twilio calls, conferences, notifications, etc.
  |
|
**Primary Metrics**
 | * Call Traffic
* SMS Traffic
* Cost Trend
* Call completion rate
* Average call duration
* Call cost
* SMS cost
* Abandon rate
* Daily call volume
 |
|
**Primary Company Roles**
 |
 Product owner
  |
|
**Average Implementation Time**
 |
 ~1 hour
  |
|
**Ease of Use (on a 1-to-10 scale with 1 being easiest)**
 |
 2
  |

Best Practices
----------------

One account can own only 1000 subaccounts by default. For more, you must mail Twilio at

help@twilio.com

Prerequisites
---------------

To connect to your Twilio account and create a DataSet, you must have the following:

 A Twilio account SID.
* A Twilio auth token.

You can find both of these items in your Twilio account settings page, in the
 **API Credentials**
 section. For more information, see

http://www.twilio.com/help/faq/twilio-basics/what-is-the-auth-token-and-how-can-i-change-it

.


 Connecting to Your Twilio Account
-----------------------------------

This section enumerates the options in the
 **Credentials**
 and
 **Details**
 panes in the Twilio Connector page. The components of the other panes in this page,
 **Scheduling**
 and
 **Name & Describe Your DataSet**
 , are universal across most connector types and are discussed in greater length in

Adding a DataSet Using a Data Connector

.

##
 Credentials Pane

This pane contains fields for entering credentials to connect to your Twilio account. The following table describes what is needed for each field:


 Field
  |
 Description
  |
| --- | --- |
|
 Account SID
  |
 Enter your Twilio account SID.
  |
|
 Auth Token
  |
 Enter your Twilio auth token.
  |

After you have entered valid Twilio credentials, you can use the same account in Domo any time you create a Twilio DataSet. You can manage connector accounts in the
 **Accounts**
 tab in the

Data Center

. For more information about this tab, see

Managing User Accounts for Connectors

.

##
 Details Pane

This pane contains a primary
 **Report**
 menu in which you select a report type, as well as other fields and menus that appear, depending on the selected report.


 Menu
  |
 Description
  |
| --- | --- |
|
 |
 Select a Twilio report. The following reports are available:


|  |  |
| --- | --- |
|
 Accounts
  |
 Returns information about the authenticated user's accounts, including SID, name, type, status, auth token, etc.
  |
|
 Alerts
  |
 Returns a list of alerts generated for the authenticated user's account.
  |
|
 Calls
  |
 Returns information about calls, including phone number, call status, inbound or outbound, call start and end time, etc.
  |
|
 Conferences
  |
 Returns information about conferences, including SID, name, status, created and updated dates, etc.
  |
|
 Notifications
  |
 Returns information about notifications, including SID, message text, message date, etc.
  |
|
 SMS Messages
  |
 Returns information about SMS messages, including SID, body text, status, price, date sent, etc.
  |
|
 Usage Records
  |
 Returns information about usage records, including category, SID, start and end date, price, description, etc.
  |


 |
|
 Account Name (Optional)
  |
 Enter the name of the account you want to pull alerts data for. If you do not enter an account name, data is pulled for all accounts.
  |
|
 To Number (Optional)
  |
 Enter a telephone number to filter your report to show placed calls or SMS messages from that number.
  |
|
 From Number (Optional)
  |
 Enter a telephone number to filter your report to show received calls or SMS messages from that number.
  |
|
 Status
  |
 Select a call status to filter your report to show items with that status.
  |
|
 Log
  |
 Select a log to filter your report to show items from that log.
  |
|
 Log Level
  |
 Select the log level you want to filter your report by.
  |
|
 Category
  |
 Select a category to break down the usage records by.
  |


###
 Other Panes

For information about the remaining sections of the connector interface, including how to configure scheduling, retry, and update options, see

Adding a DataSet Using a Data Connector

.


 FAQs
------


#####
 How frequently will my data update?

As often as needed.

####
 Are there any API limits I should be aware of?

Twilio may limit API calls. To prevent rate limiting, reduce the number of DataSets scheduled to run at the same time.

####
 Can I use the same Twilio account for multiple DataSets?

Yes.


 Troubleshooting
-----------------


* Double-check your credentials.
* Log into Twilio and check the dashboard for data.


