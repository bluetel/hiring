# Bluetel Candidate Exercise

Thanks for taking interest in a position at Bluetel! Answering this set of questions gives us a good idea about your technical and logical capabilities; as well as a couple of personal characteristics. You can be as brief or comprehensive as you wish in your answers. We don’t expect every candidate to know all the answers to these questions, so please don’t be discouraged if you don’t know the answer! Good luck!  

### Question 1
Create an algorithm  that prints  the integers from 17 to 53. However for multiples  of two print "Foo" instead  of the number and for the multiples of five print "Bar". For numbers which are multiples  of both two and five print "FooBar". ù
### Answer 1
This question was already included in the past questionnaire. Anyway below my algorithm:
<?php
  for($i=17;$i<54;$i++)
  {
      //check if it's a multiple of 2
      if($i%2==0)
      echo "Foo";
      //check if it's a multiple of 5
      if($i%5==0)
      echo "Bar";
      //check if it's a number that isn't a multiple of 2 and 5
      if($i%2!=0 && $i%5!=0)
      echo "$i";
      //just a line break
      echo "<br>";
  }
?>

### Question 2
In SQL database tables, why is redundant data (i.e. the same data stored in multiple tables) generally a bad thing?
### Answer 2
This question was already included in the past questionnaire because SQL is a relational database. I think that we can focus on these aspects to answer to the question:
1)having duplicated data means increase DB space and could cause a corruption data if you aren't able to update/delete all duplicated data every time
2)more data means slow queries and bad performances
3)more space means higher costs for company 

### Question 3
In SQL database tables, why might redundant data be necessary in real world applications?
### Answer 3
This question was already included in the past questionnarie. 
My answer is you can think about going against database normalization if i want to speed up complex query that involve 3,4,5 tables at same time. In this case having duplicated data can reduce JOIN between tables and improve db performances.


### Question 4
Why won't the following Apache web server configuration work correctly? Can you suggest a solution to make it work?

```
Listen 33.33.33.33:443
<VirtualHost 33.33.33.33:443>
  ServerName www.example1.com
  DocumentRoot /var/html/www.example1.com
  SSLEngine on
  SSLCertificateFile /etc/apache2/ssl.crt/www.example1.com.crt
  SSLCertificateKeyFile /etc/apache2/ssl.key/www.example1.com.crt
</VirtualHost>

<VirtualHost 33.33.33.33:443>
  ServerName www.example2.com
  DocumentRoot /var/html/www.example2.com
  SSLEngine on
  SSLCertificateFile /etc/apache2/ssl.crt/www.example2.com.crt
  SSLCertificateKeyFile /etc/apache2/ssl.key/www.example2.com.crt
</VirtualHost>
```
### Answer 4
KeyFile have wrong extension , it should be .key 

Listen 33.33.33.33:443
<VirtualHost 33.33.33.33:443>
  ServerName www.example1.com
  DocumentRoot /var/html/www.example1.com
  SSLEngine on
  SSLCertificateFile /etc/apache2/ssl.crt/www.example1.com.crt
  SSLCertificateKeyFile /etc/apache2/ssl.key/www.example1.com.key
</VirtualHost>

<VirtualHost 33.33.33.33:443>
  ServerName www.example2.com
  DocumentRoot /var/html/www.example2.com
  SSLEngine on
  SSLCertificateFile /etc/apache2/ssl.crt/www.example2.com.crt
  SSLCertificateKeyFile /etc/apache2/ssl.key/www.example2.com.key
</VirtualHost>

### Question 5
In PHP, for what reasons might you initialise strings with single quotes ('')
instead  of double quotes (“”)?
### Answer 5
The difference is that variables between single quotes aren't elaborated so if i write echo '$var' Apache will prints $var while if i write echo "$var" Apache will prints the value stored in $var. 


### Question 6
In development teams multiple people are often involved in building and maintaining applications, often including the same set of files. They may be working on a single task together, or multiple tasks, and changes made by one developer may conflict with those of another. What system would
you suggest to help manage this, and why would you choose your solution in particular?
### Answer 6
This is only a personal opinion but i think that the most productive method to tackle the problem is the Scrum method: a team works together to complete an activity and complete the job. This method does not generate conflict or competition between developers and can speed up the development process and this means more money for the company in terms of ROI.

### Question 7
In an ecommerce web application you would typically have a series of prices for products stored in the system. The prices may be inclusive or exclusive of taxes, and may need to be combined for various reasons (such as producing a sum total at the end of an online checkout).
How would you programmatically manipulate those prices, and why?
### Answer 7
Taxes aren't related to product but they are related to customer region so the best way to design our db is to create a table called region and a table called tax. In the region table i have a field called id_tax that is the field id of tax table. Software will calculate all prices at the checkout according to the customer's region (joining tax table and region table by tax.id=region.id_tax).
There is a problem: in some cases some product, as luxury product or certain food, have special tax rate and this could be different region by region. In this case our db scheme fails. I this last case i suggest to evaluate to integrate an external service such Taxjar , Avalara that can calculate taxes and manage exceptions for us. If you want to have this feature inhouse you have to link tax_rate to a category table and products should be related to category table by products.id_category field. This could be a way, maybe with other details i could design a more suitable db scheme.



### Question 8
In an ecommerce application, with discrete levels of stock, how would you manage a situation where two customers were interested in buying the last unit of stock for an item? How would your solution ensure the greatest possibility of the item being sold?
### Answer 8
In an ecommerce application customers place an order and make a payment in a second phase. I suggest to update stock quantity when payment is correctly completed because sometimes customer places order and then ask to cancel it (for example order placed by error). Anyway a good ecommerce software should notify me when a certain product is below a certain threshold in a way that i can order that product just in time to have it for the next sell. 

### Question 9
Modern websites often need to take into account the form of device a visitor is viewing the site on (e.g. desktop  computer, tablet, smartphone). What design pattern would you suggest to make the site work across each device?
### Answer 9
I suggest to use Bootstrap that combine HTML, CSS and jQuery to make responsive web pages or you can do it by yourself using viewport HTML tag.

### Question 10
Explain what Object-oriented Programming is and the benefits of using an Object-oriented language.
### Answer 10
OOP is a programming style that uses object and classes. Object can receive, send and manipulate data from other object. This way of writing code is flexible and easy to understand after development. Another benefit is represented by that software is the sum of a collection of modules that are indipendent between them. This make them easly to update, modify and test and there is no risk to generate issue in the rest of the program.  
 
### Question 11
Explain what procedural programming is and the benefits of using a procedural language.
### Answer 11
Another programming style is represented by procedural programming in which the software execute all the istructions row by row (Top Down Design) : you start with a problem , or procedure, and then systematically break the problem down into sub problems. 
Procedural programming need less memory , let you to keep track of program flow and is very simple.

### Question 12
Explain the benefits of using an MVC Framework.
### Answer 12
Model View Controller , or MVC, allows developers to speed up development process. In fact model , view and controller are indipendent between them and different developer can work at same time on these 3 components. Another benefit consists in supporting asynchronous technique that improve our app performances.  MVC returns data without applying any formatting so i can manipulate them as i want. 


