---
title: "Yara basics"
date: 2023-06-01T03:16:48+02:00
draft: true
---

# Yara

This page is for taking some basic notes about Yara.

Example Yara file:

``` 
rule rule_name {
meta:
    author = "Test Tester <test@example.com>, Test Company"
    type ="Unknown"
    filetype = "Win32 EXE"
    date = "2024-05-24"
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
## meta
The meta section is optional and used for metadata.

## strings
Strings can be used in the conditions for matching.
Strings can have modifiers like, **nocase**(not case sensitive) or **wide** (unicode).

## condition
