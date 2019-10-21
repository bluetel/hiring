# Bluetel Candidate Exercise

Thanks for taking interest in a position at Bluetel! Answering this set of questions gives us a good idea about your technical and logical capabilities; as well as a couple of personal characteristics. You can be as brief or comprehensive as you wish in your answers. We don’t expect every candidate to know all the answers to these questions, so please don’t be discouraged if you don’t know the answer! Good luck!

### Question 1

Create an algorithm that prints the integers from 17 to 53. However for multiples of two print "Foo" instead of the number and for the multiples of five print "Bar". For numbers which are multiples of both two and five print "FooBar".

```
/**
 * Funtion that prints the integers from 17 to 53 except for:
 * - multiples of two: print 'Foo' instead
 * - multiples of five: print 'Bar' instead
 * - multiples of two and five: print 'FooBar' instead
 * @returns {void}
 */
function fooBar() {
	for (let i = 17; i <= 53; i++) {
		if (i % 2 === 0 && i % 5 === 0) console.log('FooBar');
		else if (i % 2 === 0) console.log('Foo');
		else if (i % 5 === 0) console.log('Bar');
		else console.log(i);
	}
}
fooBar();
```

### Question 2

In SQL database tables, why is redundant data (i.e. the same data stored in multiple tables) generally a bad thing?

> Because it can lead to data inconsistency if updating one field doesn't automatically updated the other field.

### Question 3

In SQL database tables, why might redundant data be necessary in real world applications?

> It can be used for backup/recovery of a table deleted accidentally from the database for example.

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

> I never configured Apache server but after looking the Apache's documentation quickly it looks like `DocumentRoot` should come right after `<VirtualHost>` and the its value should be double quoted.

```
Listen 33.33.33.33:443
<VirtualHost 33.33.33.33:443>
  DocumentRoot "/var/html/www.example1.com"
  ServerName www.example1.com
  SSLEngine on
  SSLCertificateFile /etc/apache2/ssl.crt/www.example1.com.crt
  SSLCertificateKeyFile /etc/apache2/ssl.key/www.example1.com.crt
</VirtualHost>

<VirtualHost 33.33.33.33:443>
  DocumentRoot "/var/html/www.example2.com"
  ServerName www.example2.com
  SSLEngine on
  SSLCertificateFile /etc/apache2/ssl.crt/www.example2.com.crt
  SSLCertificateKeyFile /etc/apache2/ssl.key/www.example2.com.crt
</VirtualHost>
```

### Question 5

In PHP, for what reasons might you initialise strings with single quotes ('')
instead of double quotes (“”)?

> I've never used `PHP` in my life. Ever. But Google/Stackoverflow are the developer's best friends, so I would say it is easier to use single quotes when you need to display some information that contains double quote since there is no need to escape the double quotes. But it looks like if you want to include variables directly inside the string you need to use double quotes.

### Question 6

In development teams multiple people are often involved in building and maintaining applications, often including the same set of files. They may be working on a single task together, or multiple tasks, and changes made by one developer may conflict with those of another. What system would
you suggest to help manage this, and why would you choose your solution in particular?

> I would suggest the team to use some _source-control management_ system such as _Git_, _Subversion_ or _Mercurial_. I would choose _Git_ because it is free and open source, almost everything is possible simply on your local machine (commits, merge branches, create branches,...) and it is distributed, every developer gets their own local repository, complete with a full history of commits. It is hugely popular making it easy to find "answer" online.

### Question 7

In an ecommerce web application you would typically have a series of prices for products stored in the system. The prices may be inclusive or exclusive of taxes, and may need to be combined for various reasons (such as producing a sum total at the end of an online checkout).

How would you programmatically manipulate those prices, and why?

> Different categories of products might have different taxes or no taxes at all, so the dabatase could have a table for product including a field for category plus a table for taxes (per category) then when displaying the final price of a product we can get the value of the tax for that category and apply it. In this away products that are free of taxes would not have any tax applied to it when buying multiple products and qw can easyly access the prices with or without taxes.

### Question 8

In an ecommerce application, with discrete levels of stock, how would you manage a situation where two customers were interested in buying the last unit of stock for an item? How would your solution ensure the greatest possibility of the item being sold?

### Question 9

Modern websites often need to take into account the form of device a visitor is viewing the site on (e.g. desktop computer, tablet, smartphone). What design pattern would you suggest to make the site work across each device?

> Responsive Web Design.

### Question 10

Explain what Object-oriented Programming is and the benefits of using an Object-oriented language.

> Object-oriented Programming is a programming paradigm based on _objects_ used to describe properties and behaviors of concrete, real things plus relations between things like companies and employees for example.
> Advantages:

- Real-world model of objects/relations
- Code reusablitlity
- Abstraction, encapsulation and inheritance of objects

### Question 11

Explain what procedural programming is and the benefits of using a procedural language.

> Procedrual programming is a programming paradigm based on a execution of sequential instructions in a linear order focusing on processes.
> Advantages:

- modularity
- general purpose programming
- easy to track the program flow

### Question 12

Explain the benefits of using an MVC Framework.

> Separation of concern since we divice the application in three main parts: **model** (business logic), **view** (presentation) and **controller** (the connection between model and view).
