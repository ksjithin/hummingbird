---
title: SQL Injection
date: 2020-03-23 01:43:13
tags:
---

![Sqli](https://www.getastra.com/blog/wp-content/uploads/2017/05/xsql-injection-2-650x350.png.pagespeed.ic.UdZjd3jX0J.webp "Sqli")


An SQL injection is considered as a high severity vulnerability. The extent of to which the damage can be caused can solely be left to the attacker’s skill and imagination, and the existence of countermeasures, like low privilege connections to the database server, to brace such an attack.

Once compromised, a hoard of sensitive information once concealed by the database now becomes at the mercy of the attacker. Consequentially, the attacker can now steal sensitive data from the database, execute administration operations on the database (such as shutdown the DBMS), recover the content of a given file present on the DBMS file system and in some cases gain control of the operating system.

Typically, the following kind of attacks are possible once an SQL injection occurs:

The attacker can bypass the authentication to log onto the application, potentially with administrative privileges, without supplying any of the required credentials.
The attackers can comprise data integrity by altering contents of the database, deface a web page or insert malicious content into other innocuous websites
The attacker can compromise the availability of data by deleting log or audit information in a database
The attacker can jeopardize the operations of the host operating system via command execution through database