## Server Side Dynamic Pages

An Instagram clone implemented with server-side dynamic pages. 

In this project, we build an interactive website using server-side dynamic pages. Reuse the templates from project 1, rendering them on-demand when a user loads a page. New features include creating, updating, and deleting users, posts, comments, and likes.

The learning goals of this project include server-side dynamic pages, CRUD (Create, Read, Update, Delete), sessions, and basic SQL database usage.

### Schema

Update schema.sql, which will create 5 tables: users, posts, following, comments and likes. The following list describes the tables and columns:

> Users table
>> username, at most 20 chars, primary key <br/>
>> fullname, at most 40 chars <br/>
>> email, at most 40 chars <br/>
>> filename, at most 64 chars <br/>
>> password, at most 256 chars <br/>
>> created, DATETIME type, automatically set by SQL engine to current date/time. <br/>

> Posts table
>> postid, integer, primary key <br/>
>> filename, at most 64 chars <br/>
>> owner, at most 20 chars, foreign key to users <br/>
>> created, DATETIME type, automatically set by SQL engine to current date/time. <br/>
>> NOTE: rows are automatically removed and updated (read about CASCADE).  <br/>

> Following table
>> username1, at most 20 chars, foreign key to users <br/>
>> username2, at most 20 chars, foreign key to users <br/>
>> The tuple (username1, username2) form a primary key <br/>
>> created, DATETIME type, automatically set by SQL engine to current date/time. <br/>
>> NOTE: rows are automatically removed and updated (read about CASCADE). <br/>

> Comments table
>> commentid, integer, primary key <br/>
>> owner, at most 20 chars, foreign key to users table <br/>
>> postid, integer, foreign key to posts table <br/>
>> text, at most 1024 chars <br/>
>> created, DATETIME type, automatically set by SQL engine to current date/time. <br/>
>> NOTE: rows are automatically removed and updated (read about CASCADE). <br/>

> Likes table
>> owner, at most 20 chars, foreign key to users <br/>
>> postid, integer, foreign key to posts <br/>
>> created, DATETIME type, automatically set by SQL engine to current date/time. <br/>
>> The tuple (owner, postid) form a primary key <br/>
>> NOTE: rows are automatically removed and updated (read about CASCADE). <br/>

To clarify for the following table, username1 follows username2. <br/>

### URLs

> /  <br/>
> /u/<user_url_slug>/  <br/>
> /u/<user_url_slug>/followers/  <br/>
> /u/<user_url_slug>/following/  <br/>
> /p/<postid_url_slug>/  <br/>
> /explore/  <br/>
> /accounts/login/  <br/>
> /accounts/logout/ Immediately redirects to /accounts/login/ <br/>
> /accounts/create/  <br/>
> /accounts/delete/  <br/>
> /accounts/edit/  <br/>
> /accounts/password/  <br/>

#### Screenshots

<img src="insta_01.png" width="600" height="460">

<img src="insta_02.png" width="600" height="380">
