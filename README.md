Download Link: https://assignmentchef.com/product/solved-cs3431-homework-5
<br>
You are given a database schema consisting of three relations, whose schemas are given below. You are expected to develop your own test data sets and to perform thorough testing on these data sets using Oracle. Also test your SQL statements out on the sample data that we will provide.

<strong>Product(model, manufacturer, type)</strong>

<strong>PC(model, speed, ram, hd, rd, price)</strong>

<strong>Laptop(model, speed, ram, hd, screen, price)</strong>




<strong>Problem 1. Constraints Specification in SQL</strong>




Assume no primary keys, nor foreign key constraints have been defined on this schema yet.

Write SQL DDL statements to add the constraints below whenever possible. Do not use triggers!

Please REVIEW the supplementary Integrity Constraints Slides Attached to this homework to learn about “Check” constraints.

Demonstrate that your solution works. If you cannot enforce the constraints through DDL statements explain why.




<ol>

 <li>Add a constraint to the Product table to enforce that the type of the product must either be ’PC’ or ’Laptop’.</li>

</ol>







The Result of Running the SQL Script:










<ol start="2">

 <li>Add an additional constraint that the price of any Laptop must be at least 500.</li>

</ol>










<ol start="3">

 <li>Add the constraint that a laptop with a larger model number must also have a higher price than one with a lower model number.</li>

</ol>







<ol start="4">

 <li>Add the constraint that any PC and Laptop corresponds to a model number that also exists in the Product table.</li>

</ol>




<ol start="5">

 <li>Add the constraint that in our product database table we only maintain products from at most 5 different manufacturers (so to assure that the quality we offer is high).</li>

</ol>













<strong>Problem 2. Trigger Specification in SQL </strong>

<strong> </strong>

Consider the relational schema below with primary key constraints as specified. However, the designer forgot to define any foreign keys J

<strong> </strong>

<strong>Product(model PRIMARY KEY, manufacturer, type)</strong>

<strong>PC(model PRIMARY KEY, speed, ram, hd, rd, price)</strong>

<strong>Laptop(model PRIMARY KEY, speed, ram, hd, screen, price)</strong>




Now determine how many triggers you need, what events you need to monitor, and lastly what actions are the most meaningful to take for each of the examples below. Test out your triggers, once designed, on the data set that we provide.

Turn in your script illustrating the success of your tests.




<ol>

 <li>Write one or more triggers to enforce overlap constraints, namely, to specify that when inserting a new laptop, the model number should not also appear in the PC table, and vice versa.</li>

</ol>




<ol start="2">

 <li>Write the needed triggers to enforce that whenever the prices of a Product model are being modified, that then there is a “log tuple” inserted into a special relational table (call it Product-Monitoring) that indicates the model number of the modified product listing, the type of the product (pc, printer, etc.), the old price, and the new price, the time of the modification. Note that a command such as “to char(sysdate,’dd-mm-yyyy: hh24:mi’)” could be used to produce a date value. Also, remember that to first create the product-Monitoring table with the appropriate attributes.</li>

</ol>




<ol start="3">

 <li>Write one or more triggers to enforce the constraint that at all times the Product table is consistent with the other two tables. This is an extension of the foreign key constraint semantics. So now assume here that you did not have access in your DBMS to any direct support for foreign keys. That is, if in the Product table, a product row is specified as being of PC type then its model number also appears in the corresponding PC table. Similarly, if a product is of type laptop, then its model number must also appear in the laptop table. If the type VALUE is “NULL”, then it should appear in none of the other tables. Or, vice-versa, check that any tuple that is being inserted into the Laptop or the PC table, either already exists in the Product table, or if not then you also will add it into the Product table as part of the current update.</li>

</ol>










<strong>Problem 3: View Specification in SQL</strong>

Consider a database schema consisting of three relations, whose schemas are given below (the <u>key fields are underlined</u>). Please load data into your tables and test your answers on Oracle.

Consider the following view PCPriceList defined as:







<ol>

 <li>Use the above view to find the PC with the cheapest price. Show the SQL query.</li>

</ol>

Can you delete from this view directly? Discuss. Show how!







<ol>

 <li>Can you perform an insert such as: INSERT INTO PCPriceList(model) VALUES (2005)? When yes and when no? Discuss.</li>

 <li>What about an insert such as: INSERT INTO PCPriceList (price) VALUES (1700)? Discuss.  Show what happens.</li>

 <li>Now using SQL DDL, define a second view extendedPC(manufacturer, model, speed, ram, hd, rd, price, type). This view will give every PC made by each manufacturer. Can you delete from this extendedPC view? Discuss. Show what happens.</li>

</ol>


