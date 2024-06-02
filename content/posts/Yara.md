---
title: "YARA basics"
subtitle: "some YARA notes"
date: 2024-05-24T01:45:48+02:00
lastmod: 2024-05-28T02:45:48+02:00
draft: false
description: "some yara notes"
author: "0x61616161"
tags: [ "yara", "notes"]
categories: ["notes"]
---

# YARA
This page is for taking some basic notes about Yara.


``With YARA you can create descriptions of malware families (or whatever you want to describe) based on textual or binary patterns. Each description, a.k.a rule, consists of a set of strings and a boolean expression which determine its logic``
[Quote from the YARA homepage](https://virustotal.github.io/yara/)

[Documentation](https://virustotal.github.io/yara/) can be found on the "read the docs" page.

[Online YARA validator](https://yaravalidator.manalyzer.org/)

Example YARA file:

``` 
rule rule_name {
meta:
    author = "Test Tester <test@example.com>, Test Company"
    type ="Unknown"
    filetype = "Win32 EXE"
    date = "2024-05-24"
    last_updated = "2024-05-24"
    version = "1.0"
    reference = "https://example.com/"
    md5 = "hash"
    
strings:
    //line comment
    $a1 = { c8 54 }
    /*comment 2 */
    $a2 = "cmd c/" ascii wide nocase
    
condition:
    ((uint16(0) == 0x5A4D)) and (filesize < 100000) and ((any of ($a*)))
}
```
## file sections
### meta
The meta section is optional and used for metadata. This is basically free text.

Example keywords:
- author
- type of malware
- filetype
- date of creation
- last_updated
- version
- reference
- hash/md5/sha512...

### strings
In this section, variables that represent strings can be defined.
Strings can be used in the conditions for matching.
Strings can have modifiers like **nocase**(not case-sensitive) or **wide** (unicode).
These variables can be normal strings or hex values. Furthermore, it is possible to use placeholders / regex.

Example keywords:
- ascii (if no modifier is used, this is the default value)
- wide
- nocase
- xor

### condition
Condition to match files against, this might use the strings defined in the strings section.


When executed, yara uses one YARA file (with potentially multiple rules inside) to match against file(s).

If condition uses $a* to match against all string variables starting with "$a", it needs to be enclosed in (), so it will be 
```
($a*)
```

## Wildcards



## YARA modules

## Efficiency

## Example conditions



