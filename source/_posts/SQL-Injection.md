---
title: SQL Injection
date: 2020-03-23 01:43:13
tags:
---

![Sqli](https://media-exp1.licdn.com/dms/image/C5112AQEpO4Ls_OCDfA/article-cover_image-shrink_600_2000/0?e=1590624000&v=beta&t=ELJ7YKbX0Z5tMWWMnCK6n3aM0xLTMwSr7yJoOuoXH90 "Sqli")


An SQL injection is considered as a high severity vulnerability. The extent of to which the damage can be caused can solely be left to the attacker’s skill and imagination, and the existence of countermeasures, like low privilege connections to the database server, to brace such an attack.

Once compromised, a hoard of sensitive information once concealed by the database now becomes at the mercy of the attacker. Consequentially, the attacker can now steal sensitive data from the database, execute administration operations on the database (such as shutdown the DBMS), recover the content of a given file present on the DBMS file system and in some cases gain control of the operating system.

Typically, the following kind of attacks are possible once an SQL injection occurs:

The attacker can bypass the authentication to log onto the application, potentially with administrative privileges, without supplying any of the required credentials.
The attackers can comprise data integrity by altering contents of the database, deface a web page or insert malicious content into other innocuous websites
The attacker can compromise the availability of data by deleting log or audit information in a database
The attacker can jeopardize the operations of the host operating system via command execution through database