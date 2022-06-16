---
type: page
title: trunc
listed: false
slug: trunc
description: 
index_title: trunc
hidden: 
---draft

**trunc** truncates the input string keeping a given number of characters.

### Input

$.event.user_text = "Humpty Dumpty sat on a wall"

We will use a count of 7.

### Function

`{{ trunc <number> $.event.user_text}}`

If **number** is positive, you get that number of leading characters. If **number** is negative, you get that number of trailing characters.

### Output

For **number** = 7,

`{{ trunc 7 $.event.user_text}}`

returns the first seven characters: "Humpty "

If however, you set **number** to -7,

`{{ trunc -7 $.event.user_text}}`

returns the last seven characters:" a wall"

