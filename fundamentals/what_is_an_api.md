# What is an API?

API stands for Application Programmig Interface. Broadly speaking, an API is a set of instructions, standards, protocolos or functions for a given entity.

In essence, the API provides building blocks and their documentation for developers to build something out of them, with ease and consistency.

##Types of APIs

One usually links the idea of API to the Web and Web Development ( and I hope this is the reason you are reading the book). But there are other types of API.

Operative systems for example provide an API for programmers to build programs that can use the features of the system (and not crash). This APIs often consist of functions and protocols.

An example of this is the [Jquery API](http://api.jquery.com/) which consist of basic functions you can perform in order to build your own modules.

Then we have the Web APIs. Most of the time, Web APIs act as the interface between the Users and the Data. They specify **endpoints**, or web addresses which when hit they return something.


##Why APIs?

APIs were created as a machine-machine communication mechanism, to sistematically share data between two or more systems. A well defined API makes the developer's job easier when creating complex data driven systems that communicate with other complex data driven systems.

Let's imagine for a second that the Google application you use on your phone didn't communicate with Google's Search API.
Everytime you ask for something, the program would have to invoke the same URL you invoke when you do a Google search. Then it would have to traverse through the entire HTML code, reading every node of the DOM, and according to a predefined rule, it would extract information of certain child nodes (for example, only nodes with an class attribute of "result"), process it and finally show it to you. This is known as web scraping or web harvesting.

By the way, if the source's HTML code changes, even by a little bit, the crawler could fail when extracting information. It could visit and extract wrong nodes or even just crash.

With an API, this process is rendered obsolete. An API defines a clear way for both **consuming** (asking for) and **feeding** (sending)  information. An API is also aware of the system's data model, so the developer can simply ask for a Movie, and a Movie object data will be return to her.


##JSON APIs

In this book we will focus on building a JSON API, this is one that communicates in **J**ava**S**cript **O**bject **N**otation. Why JSON? Because I like JSON, there's no other particular reason.

Other APIs communicate in XML or plain text or different protocols.
