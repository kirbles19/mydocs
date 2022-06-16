---
type: page
title: substr
listed: false
slug: substr
description: 
index_title: substr
hidden: 
---draft

**substr** extracts a substring from the input string. it requires a first position (starting from zero, not one) and the end position (also zero based).

## Input

`$.event.user_text = "Humpty Dumpty sat on a wall"`

## Function

`{{ substr <begin> <end> $.event.user_text}}`

## Output

Here are some example outputs depending on the combinations of **begin** and **end**.

| **begin** | **end** | **Output** | **Remark** |  | 
| ---- | ---- | ---- | ---- | ---- | 
| 7 | 13 | "Dumpty" | Valid |  | 
| 13 | 7 | Error | **begin** must be less than  **end** |  | 
| 7 | Undefined | Error | Missing **end** value |  | 
| -7 | 13 | "Humpty Dumpty" | Treats **begin** as zero |  | 
| 0 | 100 | "Humpty Dumpty sat on a wall" | Takes the actual input string and no more |  | 


