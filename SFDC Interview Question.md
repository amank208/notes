1.	Can two users have the same profile?
Yes
2.	Can two profiles be assigned to the same user?
No
3.	What is a sandbox org?  What are the different types of sandboxes in Salesforce?
A sandbox is a copy of the production environment/ org, used for testing and development purposes.
Types of Sandboxes are:
•	Developer
•	Developer Pro
•	Partial Copy
•	Full
4.	Can you edit an apex trigger/ apex class in production environment? Can you edit a Visualforce page in production environment?
No, it is not possible to edit apex classes and triggers directly in production environment.
It needs to be done first in Developer edition or testing org or in Sandbox org. Then, to deploy it in production using deployment tools.
However, Visualforce pages can be created and edited in both sandbox and in production.
Only if the page has to do something unique (different values), it would have to be developed via Sandbox.
5.	What is WhoId and WhatId in activities?
WhoID refers to people. Typically: contacts or leads. Example: LeadID, ContactID
WhatID refers to objects. Example: AccountID, OpportunityID
6.	What is a wrapper class in Salesforce?
A wrapper class is a type of container class, which contains a group of objects as its members. It is of an abstract data type. We use a wrapper class for enclosing the collected data. A wrapper class is defined by a programmer, that acts as custom objects, along with wrapper class properties.
The instances of a wrapper class are helpful in displaying various objects in the corresponding table on a Visualforce page.
Some of the main advantages of using wrapper class by developers in Salesforce are given below:
•	The wrapper class structure is as efficient as that of a good data visualization process for a web page, especially in the case where the developers are dealing with the JSON structure.
•	The developers are not required to manage the passing of any map structure in order to browse necessary elements. Moreover, usage of wrapper class by developers will lead to ease the process of managing relationships between different objects.
•	Wrapper class usage prevents any penalty faced by the users for passing an object of Salesforce. Also, it makes the respective object extendable to constructors of a class.
•	The use of the wrapper class supports the developers for efficiently organizing the concerned data, provided the data is properly nested.
7.	What is Future annotation(@future)?
•	Future annotations are used to specify methods that are executed asynchronously.
•	Methods having future annotation must be static methods and can only return a void type. The arguments specified must be primitive data types or arrays of primitive data types or collections of primitive data types. These methods cannot take sObjects or objects as parameters.
•	When you specify a method with @future annotation, it will be executed only when Salesforce has available resources.
•	For example, you can use future annotation while making an asynchronous web service callout to an external service. Whereas without the usage of future annotation, web service callout will be created from the same thread which is executing the Apex code, and no additional processing will take place until that callout is complete (synchronous processing).
8.	Is it possible to write a validation rule which will fire only on insert of record not on update of record ?
Answer: Use isnew() function which checks if the formula is running during the creation of a new record and returns TRUE if it is. If an existing record is being updated, this function returns FALSE.

9.	 Is it possible to write a validation rule on record delete?
No, only in insert and update events you can write validation rule.

10.	 rollup summary in Salesforce?
Rollup Summary field is used to calculate the sum of a fields in the child object record. It is compulsory to be in a Master-Detail relationship to use the rollup summary. A rollup summary field is always created on Master record. (Parent to Child).

11.	 What is the purpose or use of @TestVisible?
Answer: Use the TestVisible annotation to allow test methods to access private or protected members of another class outside the test class. These members include methods, member variables, and inner classes.
Using this annotation, you do not have to change the access modifiers of your methods and member variables to public if you want to access them in a test method.
For example, if a private member variable isn’t supposed to be exposed to external classes but it should be accessible by a test method, you can add the TestVisible annotation to the variable definition.

12.	 What is the difference between trigger and workflow in Salesforce ?
Answer:
Workflow:
•	Workflow will be helpful to update the same object or master object in custom master-detail relationships.
•	Coding is not required.
•	Workflow actions are Field Update, Email alert, Task alert and outbound message.
•	We cannot use SOQL query from database on workflow.
•	We cannot fire workflows after record has been deleted.
Trigger:
•	Trigger can work across objects.
•	Coding is required.
•	Trigger executes before or after these types of operations insert, update, delete, merge, upsert & undelete.
•	We can use SOQL’s from data base in one trigger.
•	We can fire Trigger after record has been deleted.

13.	Can we convert formula field into any other data type ?
Answer: No, Formula fields are special read-only fields that cannot be converted to any other data type. Likewise, you cannot convert any other field type into a formula field.

14.	 What is the difference between Role and Profile in Salesforce?
Answer: 
Role control record level access can be controlled by Role.
Profiles control the objects level access settings.
In simple words, Profile defines what user can do in your salesforce org and Role defines what user can see.
Other difference is, Profile is mandatory, Role is not.

15.	 What is Web-to-Lead in Salesforce?
Answer: Web-to-Lead is Generate Leads from Your Website for Your Sales Teams. This feature create or generate upto 500 leads per day with prospecting data from your company’s website visitors.
Salesforce runs field validation rules before creating records submitted via Web-to-Lead and only creates records that have valid values.
If a new lead cannot be generated due to errors in your Web-to-Lead setup, Customer Support is notified of the problem so that we can help you correct it.

16.	 What is the Web-to-Case in Salesforce?
Answer: Capture Cases from your Website.
Gather customer support requests directly from your company’s website and automatically generate up to 5,000 new cases a day with Web-to-Case. This can help your organisation respond to customers faster, improving your support team’s productivity.
Note:
•	Whenever possible, Web-generated cases are automatically linked to the relevant contact and account based on the customer’s email address.
•	Salesforce runs field validation rules before creating records submitted via Web-to-Case and only creates records that have valid values. All universally required fields must have a value before a record can be created via Web-to-Case.
•	Salesforce doesn’t support rich text area (RTA) fields on Web-to-Case forms.
•	If you exceeded the daily limit and you want to increase that limit then go to Help & Training and raise a case with salesforce.

17.	How many rows return by list controller?
 Answer: 10000 records

18.	How can we check the object accessibility on visualforce page? 
Answer: {!$ObjectType.MyCustomObject__c.accessible}

19.	What are the Best Practises for Improving Visualforce Performance ?
Answer:
1) The view state size of your Visualforce pages must be under 170 KB. By reducing your view state size, your pages can load quicker and stall less often.
2) Large page sizes directly affects load times. To improve Visualforce page load times:
·        Cache any data that is frequently accessed, such as icon graphics.
·        Avoid SOQL queries in your Apex controller getter methods.
·        Reduce the number of records displayed on a page by adding filter condition in SOQL
3) Reduce Multiple Concurrent Requests: use <apex:actionpoller>
4) By using the with sharing keyword when creating your Apex controllers, you have the possibility of improving your SOQL queries by only viewing a data set for a single user.
5) Preventing Field Values from Dropping Off the Page.

20.	 What are the Salesforce best practices for apex?
Answer: 
•	Bulkify your Code
•	Avoid SOQL Queries or DML statements inside FOR Loops
•	Bulkify your Helper Methods
•	Using Collections, Streamlining Queries, and Efficient For Loops
•	Streamlining Multiple Triggers on the Same Object
•	Querying Large Data Sets
•	Use of the Limits Apex Methods to Avoid Hitting Governor Limits
•	Use @future Appropriately
•	Writing Test Methods to Verify Large Datasets
•	Avoid Hardcoding IDs.

21.	 Primitive and Non-Primitive Data Types.
Primitive data structure is a fundamental type of data structure that stores the data of only one type whereas the non-primitive data structure is a type of data structure which is a user-defined that stores the data of different types in a single entity.
Primitive data structure is a kind of data structure that stores the data of only one type.
Primitive data structure should contain some value, i.e., it cannot be NULL.
Examples of primitive data structure are Integer, Double, Long, Date, Datetime, String, ID, or Boolean.
Primitive data structure can be used to call the methods.

Non-primitive data structure is a type of data structure that can store the data of more than one type.
Non-primitive data structure can consist of a NULL value.
Examples of non-primitive types are Strings, Arrays, Classes, Interface, etc.
Non-primitive data structure cannot be used to call the methods.

22.	How many ways call controller from visualforce page ?
Answer:
Commandbuton,
commandlink,
Javascript remoting,
actionpoller,
actionFunction.

23.	What is the size of view state in salesforce ?
Answer: 170 KB (Prior to Spring 19 release it was 135 KB).
24.	I want to count how many times execute method executed in Batch class ?
Answer: With the help of Database.stateful

25.	Compare JavaScript Remoting and <apex:actionFunction> ?
Answer: The <apex:actionFunction> component also lets you call controller action methods through JavaScript.
In general, <apex:actionFunction> is easier to use and requires less code, while JavaScript remoting offers more flexibility.
Here are some specific differences between the two :
The <apex:actionFunction> tag:
•	lets you specify rerender targets
•	submits the form
•	doesn’t require you to write any JavaScript

JavaScript remoting:
•	lets you pass parameters
•	provides a callback
•	requires you to write some JavaScript

26.	What are the Salesforce best practices for apex?
Answer: 
•	Bulkify your Code
•	Avoid SOQL Queries or DML statements inside FOR Loops
•	Bulkify your Helper Methods
•	Using Collections, Streamlining Queries, and Efficient For Loops
•	Streamlining Multiple Triggers on the Same Object
•	Querying Large Data Sets
•	Use of the Limits Apex Methods to Avoid Hitting Governor Limits
•	Use @future Appropriately
•	Writing Test Methods to Verify Large Datasets
•	Avoid Hardcoding IDs.
27.	What are various standard exceptions that salesforce throws?
Answer - salesforce throws number of standard exceptions.
Some of the important ones are as below-
dmlexception,
listexception,
email exception,
calloutexception,
JSONexception,
mathexception,
Queryexception,
sObjectexception,
xmlexception,
typeexception,
visualforceexception,
stringexception,
searchexception,
nullpointerexception,
noaccessexception.



28.	What is recursive workflow rule? How to avoid recursive workflow rules?
Answer: 
Whenever you enable Re-evaluate Workflow Rules after Field Change checkbox in the Field Update of a workflow rule, due to this field update other workflow rules on the same object will be fired if the entry criteria of those workflow rules satisfied.
And , You have other workflow rules also if you enable Re-evaluate Workflow Rules after Field Change checkbox in the Field Update recursive workflow rules will come in some scenarios.
We can take two steps to avoid recursive workflow rules :
•	For the workflow Evaluation Criteria if you choose created, and any time it’s edited to subsequently meet criteria option, we can avoid recursive workflow rules.
•	If you don't enable Re-evaluate Workflow Rules after Field Change checkbox in the Field Update of a workflow rule we can avoid.

29.	What is the difference between 15 digit and 18 digit IDs in Salesforce?
Answer: 
15 digit ID in salesforce.com is case sensitive and 18 Digit Id is case-insensitive. Many applications does not support case sensitive strings, so in that case we can make use of 18 digit Id which is case in-sensitive.
15 digit Id number will have numeric digits range from (0-9), a Lowercase letter(a-z) or a Uppercase letters(A-Z). 15 digit ID in salesforce.com is case sensitive.
30.	What is the maximum size of the PDF generated on visualforce attribute renderAs ?
Answer : 15 MB
31.	What is the System.runAs() ?
Answer :
Generally, all Apex code runs in system mode, and the permissions and record sharing of the current user are not taken into account. The system method, System.runAs(), lets you write test methods that change user contexts to either an existing user or a new user. All of that user’s record sharing is then enforced. You can only use runAs in a test method. The original system context is started again after all runAs() test methods complete.
##### Example :

```js

System.runAs(u) {
// The following code runs as user 'nitish'
System.debug('Current User: ' + UserInfo.getUserName());
System.debug('Current Profile: ' + UserInfo.getProfileId()); 
}
// Run some code that checks record sharing
```
32.	What is Difference in render, rerender and renderas attributes of visualforce?
Answer :
render : It works like display property of CSS. It is used to show or hide element on visualforce page.
rerender : After Ajax which component should be refreshed – This attribute is available on commandlink, commandbutton, actionsupport .
renderas : render page as PDF, DOC and Excel. With the help of this attribute you can download the data display on visualforce page.
33.	When Group By is used, How to write or use the Where clause in SOQL ?
Answer :
We cannot use the Where clause with Group By instead we will need to use the Having Clause.
34.	 How can you lock record using SOQL so that it cannot be modified by other user.
Answer : We will need FOR UPDATE clause of SOQL.
Example :
SELECT Id FROM Contact LIMIT 2 FOR UPDATE
35.	How to get total number of Child records in Lookup relationship?
Answer: As Rollup Summary field is only supported in Master detail, we cannot use it for Lookup. 
There are following way.
1. Trigger on Child Object, which will update field in Parent record if child record is inserted, deleted or undeleted.
36.	We have a Time-Based Workflow and there is Action scheduled to be executed. If we Deactivate the workflow, Scheduled actions will be removed from queue or not?
Answer: Even after deactivation of workflow, its action will be active in queue.
37.	How to clear the Time based workflow action queue ?
Answer : Two ways to achieve this. 
•	Make criteria false for all those records. 
•	Go to Set up -> Monitoring -> Time Based Workflow and search for scheduled actions and then remove from queue.

38.	We have Time Based Workflow and there is action scheduled to be executed. Can we delete that workflow?
Answer : If a workflow have any pending time dependent action, then we cannot delete the workflow.

39.	 Explain few considerations for @Future annotation in Apex.
Answer : 
Remember that any method using the future annotation requires special consideration because the method does not necessarily execute in the same order it is called.
•	Methods with the future annotation cannot be used in Visualforce controllers in either getMethodName or setMethodName methods, nor in the constructor.
•	You cannot call a method annotated with future from a method that also has the future annotation. Nor can you call a trigger from an annotated method that calls another annotated method.
•	Method must be static
•	Cannot return anything i.e. ( Only Void )
•	Parameter to @future method can only be primitive or collection of primitive data type.
•	To test @future methods, you should use startTest and stopTest to make it synchronous inside Test class.

40.	How to capture errors after using Database DML methods in Salesforce?
Answer :

```js

List<Contact> lstContact = new List<Contact>();
Contact con = new Contact (lastName = 'Talekar', SQL_Server_Id__c='3',firstName='Nitish');
lstContact.add(con);
// add some other contacts records in contact List
Database.UpsertResult[] results = Database.upsert( lstContact, Contact.SQL_Server_Id__c.getDescribe().getSObjectField() ,false ) ;

for(Integer i=0;i<results.size();i++){
    if (!results.get(i).isSuccess()){
        Database.Error err = results.get(i).getErrors().get(0);
        System.debug('Error - '+err.getMessage() + '\nStatus Code : '+err.getStatusCode()+'\n Fields : '+err.getFields());
    }
}
```
41.	Which component in Salesforce ends with __mdt and __s ?
Answer : Custom metadata types ends with __mdt (meta data type), just like custom object or custom fields ends with __c.

When we create Geolocation field in Salesforce, lets say by name location__c then internally Salesforce creates subfields with extension __s. 
In this case location_latitude__s and location_longitude__s.

42.	Which interface needs to be implemented in Apex to be used in Flow ?
Answer : We can execute apex as well using flow by annotating it with @InvocableMethod and marking method as static.
Below is sample code

```js
Global class Flow_UpdateContactField {    
    @InvocableMethod
    public static void performUpdate(List<String> lstCSV){
        List<String> recIds = lstCSV[0].split(',');
        // 0 - ContactId, 1-field1__c
 Contact objCon = new Contact(Id=recIds[0], field1__c=recIds[1]);
 update objCon;        
    } 
}
```
43.	How to get the list of all available sobject in salesforce database using Apex (Dynamic Apex) ?
Answer :

```js
Map<String, Schema.SObjectType> m =  Schema.getGlobalDescribe();
```

44.	How to read the parameter value from the URL in Apex?
Answer :
Consider that the parameter name is AccountName then use below code snippet:

```js
String objAccountName = Apexpages.currentPage().getParameters().get('AccountName');
```

45.	What is the difference between Customer portal and Partner portal?
Answer : Traditionally Partner Portal is part of companies Partner Channel Sales efforts. It is a portal focused more on Sales force automation and the efforts of those partners that sell your products to nurture the leads you pass to them, the leads they enter in themselves and the convert to Opportunity and subsequent sale.

Customer Portal on the other hand is more focused on the Service and Support of one’s Customers.
The feature differences are that Partner Portal exposes the Leads and Opportunity objects whereas the Customer Portal does not. However, only the top tier of Partner licensing (Gold Partner licenses) exposes the Case object whereas this is standard in the Customer Portal.

46.	Explain the lead conversion process in salesforce?
Answer : When you convert a lead, the standard lead fields are automatically converted to the new account, contact, and, optionally, an opportunity using the information from the lead.
Custom lead fields are converted to custom account, contact, and opportunity fields as specified by your administrator.
All open and closed activities from the lead are attached to the account, contact, and opportunity.

47.	What are differences between workflows and approval process?
Answer : 
The key difference between workflows and approval process are as below
Workflow rules consist of single step and a single action where as approval process has multiple steps and different actions.
Workflow rules trigger automatically and the rules when triggered are not visible to the user. Approval process on the other hand, contains multiple step s each requiring a specific "I Approve or Reject" user action by the specified approvers.










48.	Tell me about Jump Start Wizard versus Standard Wizard in Salesforce?
Answer : 
The Jump Start wizard creates a one-step approval process for you in just a few minutes
The Standard Wizard is useful for complex approval processes.
Jump Start Wizard
• The jump start wizard is useful for simple approval processes with a single step.
• Use the jump start wizard if you want to create an approval process quickly by allowing Salesforce to automatically choose some default options for you.
Standard Wizard
• The standard wizard is useful for complex approval processes.
• Use it when you want to fine tune the steps in your approval process.
• The standard wizard consists of a setup wizard that allows you to define your process and another setup wizard that allows you to define each step in the process.

49.	What are the Time-Dependent Workflow – Considerations ?
Answer :
Maximum of 10 time triggers per rule
Maximum of 40 actions (10 x 4 types) per time trigger, and 80 actions per workflow rule
Workflow default user must be set up before creating time-based rules
Precision limited to hours or days.
Cannot convert leads with time-dependent actions in the Workflow Queue
Time triggers cannot be added to or removed from activated workflow rules
Not possible to create a time-dependent action associated to a rule with a trigger type of Every time the record is created or updated.

50.	What are the Time-Dependent Workflow Limitations ?
Answer :
Time triggers don’t support minutes or seconds.
Time triggers can’t reference the following:
•  DATE or DATETIME fields containing automatically derived functions, such as TODAY or NOW.
•  Formula fields that include related-object merge fields.

You can’t add or remove time triggers if:
•  The workflow rule is active.
•  The workflow rule is deactivated but has pending actions in the queue.
•  The workflow rule evaluation criteria are set to Evaluate the rule when a record is: created, and every time it’s edited.
•  The workflow rule is included in a package
51.	When the Add Time Trigger button is unavailable?
Answer :
The evaluation criteria are set to Evaluate the rule when a record is: created, and every time it’s edited.
The rule is activated.
The rule is deactivated but has pending actions in the workflow queue

52.	What are different Organization Wide Defaults? Explain each of them?
Answer :
Below are the different OWD values :
Private : 
    If the OWD for an object is set to private, then only the owner, and users above that role in role hierarchy, can view, edit and report on those records
Public Read Only :
    If the OWD for an object is set to Public Read Only, then all users can view and report on records but they cannot edit them. Only the record owner and the users above that role in the role hierarchy can edit the records
Public Read/Write :
If the OWD for an object is set to Public Read/Write, then all users can view, edit and report on all records. But only owner of the record can delete the records.

Public Read/Write/Transfer :
This is available only for Case and Lead objects
If the OWD for an object is set to Public Read/Write/Transfer then, all users can view, edit, Transfer and report on all the records but only owner of the record can delete the records

Public Full Access :
This is available only for Campaign object.
If the OWD for Campaigns are set Public Full Access then, all users can view, edit, delete and report on all records.

No Access, View Only or Use :
This is available only for Price Book object.

Controlled By Parent :
If the OWD for any object is set as Controlled By Parent, then user can perform an action on the record based on whether they can do the same on the parent record associated with it.


53.	What are differences between custom settings and custom objects?
Answer :
Custom Settings:
1. Custom settings are SOQL inexpensive
2. We can’t write triggers on custom settings
3. Fields on which we can create custom settings are restricted like picklists, lookups and formula fields can’t be created in custom settings
4. No Page layouts, record types, validation rules and workflow rules can be used on custom settings.
5. Custom Settings SOQL is faster than custom objects.

Custom Objects:
1. Custom Objects are SOQL Expensive
2. We can have triggers on custom objects
3. No restrictions on creation of fields
4. Can be used on Custom objects
5. Custom objects SOQL not fast as a custom Settings.

54.	 What are the aggregate functions supported by salesforce SOQL?
Answer :
Following aggregate functions are supported by salesforce SOQL
1. SUM()
2. MIN()
3. MAX()
4. COUNT()
5. AVG()
6. COUNT_DISTINCT()

55.	Write a sample aggregate query or explain how to write a aggregate queries?
Answer :
The return types of Aggregate functions are always an array of AggregateResult.

Sample Code

AggregateResult[] ar = [select AVG(Amount) aver from Opportunity];
Object avgAmt = ar[0].get('aver’);





56.	Write a code to find the average Amount for all your opportunities by campaign?
Answer :

```js
AggregateResult[] arList = [select CampaignId, AVG(amount) from Opportunity group by CampaignId];
for(AggregateResult ar : arList){
    System.debug('CampaignId ' + ar.get('CampaignId'));
    System.debug('Average Amount' + ar.get('expr0'));
}
```

57.	Write a syntax and structure of scheduler class?
Answer :
Sample class
```js
global class ScheduleDemo implements Schedulable{
    global void execute(SchedulableContext sc){
        BatchClass b = new BatchClass();
        database.executeBatch(b);
}
}
```

58.	What is the difference between custom controller and extension in salesforce?
Answer :
Custom Controller: A custom controller is an Apex class that implements all of the logic for a page without leveraging a standard controller. Use custom controllers when you want your Visualforce page to run entirely in system mode, which does not enforce the permissions and field-level security of the current user.
Controller extension: A controller extension is an Apex class that extends the functionality of a standard or custom controller. Use controller extensions when:
• You want to leverage the built-in functionality of a standard controller but override one or more actions, such as edit, view, save, or delete.
• You want to add new actions.
• You want to build a Visualforce page that respects user permissions. Although a controller extension class executes in system mode, if a controller extension extends a standard controller, the logic from the standard controller does not execute in system mode.



59.	Difference between with sharing and without sharing in salesforce ?
Answer :
By default, all Apex executes under the System Mode(without sharing), ignoring all CRUD, field-level, and row-level security (that is always executes using the full permissions of the current user).
with sharing:
Enforcing the User’s Permissions, Sharing rules and field-level security should apply to the current user.
For example:
public with sharing class sharingClass {
// your Code here
}
without sharing:
Not enforced the User’s Permissions, Sharing rules and field-level security.
For example:
public without sharing class noSharing {
// your Code here
}
Enforcing the current user’s sharing rules can impact: (with sharing)
SOQL and SOSL queries – A query may return fewer rows than it would operating in system context.

60.	What is Wrapper Class in Apex Salesforce ?
Answer :
Wrapper class is collections of different data type, subject etc.
In following example  we are  bind Account ,Opportunity standard object. We query and perform
business logic on the Collection of elements across unrelated objects with the custom data type.

Visual Force Page:
```js
<apex:page controller="wrapperDemoCtrl">
<apex:pageBlock title="Account From wrapper  Class">
   <apex:pageBlockTable value="{!wraccount}" var="wra">
   <apex:column value="{!wra.acc.Name}"/>
   </apex:pageBlockTable>
</apex:pageBlock>
<apex:pageBlock title="Opportunity From wrapper  Class">
   <apex:pageBlockTable value="{!wraoppn}" var="wropp">
   <apex:column value="{!wropp.op.Name}"/>
   </apex:pageBlockTable>
</apex:pageBlock>
</apex:page>
Apex Controller :

public class wrapperDemoCtrl {
    public list<wrapperClass> wraplist{get;set;}
    public list<wrapperClass> getwraccount()
          {
            list<Account>acclist=[select Id,Name from Account limit 3];
            wraplist= new list<wrapperClass>();
            for(Account acn: acclist)
            {
            wraplist.add(new wrapperClass(acn));
            }
           return wraplist;
          }
    public list<wrapperClass> getwraoppn()
        {
         list<Opportunity>opplist=[select Id,Name from Opportunity limit 3];
         wraplist= new list<wrapperClass>();
         for(Opportunity opn:opplist )
         {
         wraplist.add(new wrapperClass(opn));
         }
         return wraplist;
        }
public class wrapperClass{
        public Account acc {get;set;}
        public Opportunity op {get;set;}

        public wrapperClass(Account accn){
                 acc= accn;         
                     }
       public wrapperClass(Opportunity opn)
       {
         op=opn;
      
       }
    }
}

```


61.	How can we hard delete a record using a Apex class/by code?
Answer :
ALL ROWS key word can be used to get all the records including records in the recycle bin.
Below is the sample code to delete contact records from recycle bin

List<Contact> dContactList=[Select ID From Contact Where IsDeleted = true limit 199 ALL ROWS];
Database.emptyRecycleBin( dContactList );

62.	 What are the available Trigger Events?
Answer :
There are 6 trigger events available.
1. Insert
2. Update
3. Delete
4. Merge
5. Upsert
6. Undelete
63.	 What are the available Trigger contest variables?
Answer :
Below are the list of Trigger context variables
1. isBefore
2. IsAfter
3. isInsert
4. IsUpdate
5. isDelete
6. isUndelete
7. isExecuting
8. new
9. old
10. newMap
11. oldMap
12. Size











64.	What are the Salesforce annotations ?
Answer :
Apex annotations modify the way a method or class is used.
Below is the list of annotations supported by salesforce :
@Deprecated:
            Use the deprecated annotation to identify methods, classes, exceptions, enums, interfaces, or variables that can no longer be referenced in subsequent releases of the managed package in which they reside. This is useful when you are re-factoring code in managed packages as the requirements evolve. New subscribers cannot see the deprecated elements, while the elements continue to function for existing subscribers and API integrations.
@Future:
            Use the future annotation to identify methods that are executed asynchronously. When you specify future, the method executes when Salesforce has available resources.
            To test methods defined with the future annotation, call the class containing the method in a startTest, stopTest code block. All asynchronous calls made after the startTest method are collected by the system. When stopTest is executed, all asynchronous processes are run synchronously.
@IsTest:           
            Use the isTest annotation to define classes or individual methods that only contain code used for testing your application. The isTest annotation is similar to creating methods declared as testMethod.
@ReadOnly:           
            The @ReadOnly annotation allows you to perform unrestricted queries against the Force.com database. All other limits still apply. It's important to note that this annotation, while removing the limit of the number of returned rows for a request, blocks you from performing the following operations within the request: DML operations, calls to System.schedule, calls to methods annotated with @future, and sending emails.

@RemoteAction:           
            The RemoteAction annotation provides support for Apex methods used in Visualforce to be called via JavaScript. This process is often referred to as JavaScript remoting.

@TestVisible:           
            Use the TestVisible annotation to allow test methods to access private or protected members of another class outside the test class. These members include methods, member variables, and inner classes. This annotation enables a more permissive access level for running tests only.

Apex REST annotations:

@RestResource(urlMapping='/yourUrl'):
            The @RestResource annotation is used at the class level and enables you to expose an Apex class as a REST resource.
@HttpDelete:
            The @HttpDelete annotation is used at the method level and enables you to expose an Apex method as a REST resource. This method is called when an HTTP DELETE request is sent, and deletes the specified resource.
@HttpGet:
            The @HttpGet annotation is used at the method level and enables you to expose an Apex method as a REST resource. This method is called when an HTTP GET request is sent, and returns the specified resource.
@HttpPatch:
            The @HttpPatch annotation is used at the method level and enables you to expose an Apex method as a REST resource. This method is called when an HTTP PATCH request is sent, and updates the specified resource.
@HttpPost:
            The @HttpPost annotation is used at the method level and enables you to expose an Apex method as a REST resource. This method is called when an HTTP POST request is sent, and creates a new resource.
@HttpPut:
            The @HttpPut annotation is used at the method level and enables you to expose an Apex method as a REST resource. This method is called when an HTTP PUT request is sent, and creates or updates the specified resource.
65.	Bhswhbj
66.	Xgfcghvjh
67.	cvhjvjh











Note :-
Inline Visualforce page
