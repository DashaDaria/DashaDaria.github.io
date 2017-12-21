---
layout: post
title:      "Not all .find are the same"
date:       2017-12-21 04:25:32 +0000
permalink:  not_all_find_are_the_same
---

I've been running into issues with my code when I use .find and .find_by methods in my controllers. Sometimes a simple fix from .find to .find_by  or vice versa would cause my tests to pass. Although, I thought I could use either one of the methods, it turns out the return values (if no record found: .find -> 'RecordNotFound', .find_by -> nil) differ and therefore cause the issue.

**But first, Active Record.**

Active Record provides a class method called Model.find to retrieve objects from the database. This method allows you to pass arguments into it to perform certain queries on your database without the need of writing raw SQL.

A single object can be retrieved in **3 DIFFERENT WAYS.**


1. **Model.find(primary_key, options = nil)** 
Retrieve the object corresponding to the specified primary key that matches any supplied options (if any).  Can be a specific id (1), a list of ids (1, 5, 6), or an array of ids ([5, 6, 10]). Will raise an ActiveRecord::RecordNotFound exception if no matching record is found.
```
# Find the client with primary key (id) 1.
client = Client.find(1)
=> #<Client id: 1, name: => "Dasha">
```

SQL for this looks like this: `SELECT * FROM clients WHERE (clients.id IN (1,10))`

2. **Model.first(options = nil)**
Finds the first record matched by the supplied options. Returns nil if no matching record is found. No exception will be raised. 
```
Model.find(:first, options) is equivalent to Model.first(options)
```

3.  **Model.last(options = nil)**
Finds the last record matched by the supplied options. Same return as .first.
```
Model.find(:last, options) is equivalent to Model.last(options)
```


**Find_by, **on the other hand, is a **DYNAMIC FINDER**
Finds the first record matching some conditions. For every field (also known as an attribute) you define in your table, Active Record provides a finder method. You can specify an exclamation point (!) on the end of the dynamic finders to get them to raise an ActiveRecord::RecordNotFound error if they do not return any records, otherwise, if a record is not found, will return nil.


