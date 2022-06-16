---
type: page
title: trimSuffix
listed: false
slug: trimsuffix
description: 
index_title: trimSuffix
hidden: 
---draft

**trimSuffix** removes one instance of a given character from the end of the input string. The modified string is returned as the output.

### Input

$.event.user_text = "{Humpty Dumpty sat on a wall}"

Suffix character to remove, "}".

### Function

`{{ trimSuffix "}" $`.event.user_text }}

### Output

"{Humpty Dumpty sat on a wall"

A common scenario is to use trimPrefix and trimSuffix in tandem. In the above example, you would most likely want to remove both the leading and trailing brace.

## Add these to your workflow:

1. `{{ trimAPrefix"{" $.event.user_text}}`
2. `{{ trimASuffix"}" $.event.user_text}}`

Ensure that the input to step 2 is the output from step 1.

