---
title: Regex
date: "2019-03-29"
template: "post"
draft: false
slug: "/posts/Regex/"
category: "Tech"
tags:
  - "Coding"
description: "The one which everyone is afraid of"
---

Regex or Regular Expressions help you perform string search. They are useful in data cleaning. Below features make it powerful —

You can search for “patterns”, not just words. To give an example of pattern — search for words which have a common suffix.
Apart from returning the search results, it can also return true-false for searches. Helpful when you search for multiple strings at the same time.
You should study the documentation for learning to use it. It is overwhelming at first to grasp it, and will take time. Just to help you start —

In python, regex is in-built. It is denoted by “re”

re.search(“String to find”, “String to search from”)

Eg — re.search(“to”, “I am going to buy a pen”)

It returns True.

This is what an advanced query will look like — re.search(“?.!*hello.*). Yes, it’s not easy.

If mastered, it can help a lot in data cleaning. All the best!