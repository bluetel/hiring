# Bluetel Salesforce Candidate Questionnaire

Thanks for taking interest in a position at Bluetel! Answering this set of questions gives us a good idea about your technical and logical capabilities; as well as a couple of personal characteristics. You can be as brief or comprehensive as you wish in your answers. We don’t expect every candidate to know all the answers to these questions, so please don’t be discouraged if you don’t know the answer! Good luck!  

### Question 1
Write an APEX method which loops through numbers 1 to 20 and creates an Account record for each. The Account's Name field should be set to 'Test Account ' followed by the current number. For numbers which are multiples of two set the Employees field to '10', and for multiples of five set it to '20'. If the number is a multiple of both two and five set the Employees field to '30'.

### Question 2
In a relational database, why is redundant data (i.e. the same data stored in multiple tables) generally a bad thing?

### Question 3
In a relational database, why might redundant data be necessary in real world applications?

### Question 4
In development teams, multiple people are often involved in building and maintaining a single salesforce instance. They may be working on a single task together, or multiple tasks, and changes made by one developer may conflict with those of another. What system would you suggest to help manage this, and why would you choose your solution in particular?

### Question 5

The below Salesforce Apex code may fail on any line with a `DMLException`. Modify the code to ensure that if it were to fail then no data would be saved.

```c#
Database.insert(action);
Database.update(actionPlan);
Database.update(customer);
```

### Question 6

What is the difference between `Trigger.old` and `Trigger.new`? Under which types of trigger are they each available?

### Question 7

Provide Salesforce Apex code which uses SOQL to extract the following fields from a custom object named `Visitors` into a List variable. Only records where the value of the `Company__c` field is equal to `Bluetel` should be retrieved.

- Id
- Name
- Visit_Time__c
- Visiting__c

### Question 8

The following provides one test scenario for the requirement `Insurance Requests for amounts less than $100,000 should not be submitted to the insurer, and the user should be presented with an error if they attempt to make this submission`. Summarise the minimum test cases that you would define for the <u>entire</u> requirement.

> **Given** I am completing an insurance request 
>
> **When** I specify a cover amount of less than $100,000
> **AND** I choose to submit my request
>
> **THEN** I should receive an error 
> **AND** the request should not be submitted


