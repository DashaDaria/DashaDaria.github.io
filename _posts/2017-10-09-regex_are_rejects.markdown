---
layout: post
title:      "Regex are Rejects"
date:       2017-10-09 03:10:50 -0400
permalink:  regex_are_rejects
---


Regular Expressions (regex) are defined as a special text string for identifying patterns. This is very useful when you need to:

1. Search through strings and blocks of text for specific patterns
2. Validate Data
3. Rename a large amount of files
4. Find records in a database

Regex are tricky - and hence the saying by Jamie Zawinski, a world class hacker: 
"Some people, when confronted with a problem, think "I know, I'll use regular expressions." Now they have two problems."

One of the reasons, regex have a bad rep (not by all, some coders are expert users) is due to the inexperience of its use. Regex is a great tool but must be used with caution, as not every problem calls regex for a solution and the more complex you get into your regex the more instability you bring into your codebase. 

As a beginner, the best way to go about using regex, is to keep it simple. Do not overcompicate your selection and start out by using the basics:

1. Simple text matching: `/any_text_you_want_to_match/`
2. Metacharacters: 
![](https://i.imgur.com/RptlgIK.png)
3. Only specific characters: `/[aeiou]/`
4. Ranges: `[0-9]` or `/[a-j]/`
5. Best tool for practice: http://rubular.com/

Other tools to look into are the methods that are available with regex:

1. Match: returns the first item in your string that matches a given Regular Expression as a MatchData object, used as a boolean, indicating the existence of the pattern in the given string:
```
"some_string".match(/regex selection/)
=> #<MatchData "regex selection"> 
```
2. Scan: returns an array of all items in your string that match a given Regular Expression:
```
"The rain in Spain lies mainly in the plain".scan(/\w+ain/)
=> ["rain", "Spain", "main", "plain"]
```
3. Grep: returns an array of matching items from an array


