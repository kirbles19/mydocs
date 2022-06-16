---
type: page
title: trimAll
listed: false
slug: trimall
description: 
index_title: trimAll
hidden: 
---draft

**trimAll** removes a given character from the beginning and end of the input string and returns the modified string as the output.

## Input

$.event.user_text = "### Log Header ###" 

Remove the "#" characters from the beginning and end of the string.

### Function

`{{ trimAll "#" $.event.user_text}}`

### Output

" Log Header "

