# Basic Concepts

####In which we discover concepts that will help us communicating back and forth through the web. Also API architecture.

In this chapter we will be using the command line tool **cURL** (here forth, **curl**), to sample some of the concepts that will showed in the current chapter.

If by any chance, your machine does not have curl installed, you can do it by running

~~~
sudo apt-get install curl
~~~
on Debian-based operative systems, or

~~~
sudo yum install curl
~~~

on Fedora or CentOS.

To perform an http request with curl, you do

~~~
curl URI_ADDRESS
~~~

where `URI_ADDRESS` stands for a web address. For example

~~~
curl https://xkcd.com
~~~

will return

~~~
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" type="text/css" href="/s/b0dcca.css" title="Default"/>
<title>xkcd: Fundamental Forces</title>
<meta http-equiv="X-UA-Compatible" content="IE=edge"/>
<link rel="shortcut icon" href="/s/919f27.ico" type="image/x-icon"/>
<link rel="icon" href="/s/919f27.ico" type="image/x-icon"/>
<link rel="alternate" type="application/atom+xml" title="Atom 1.0" href="/atom.xml"/>
<link rel="alternate" type="application/rss+xml" title="RSS 2.0" href="/rss.xml"/>
....
~~~

This is the HTML text for the [xkcd comic page](https://xkcd.com).

curl supports many different parameters, some of which we will be using as we dive further into the book. You can read the curl manual by running `man curl`.
