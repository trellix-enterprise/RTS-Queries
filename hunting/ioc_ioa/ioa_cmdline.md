# Hunting For Indicators Of Attack - IoAs: Process Execution CommandLine Syntax

In some cases, a SOC approaches monitoring proactively through dedicated threat hunting expertise.

One fantastic resource to understand the increased levels of context for IOCs is the `Pyramid Of Pain` created by
security professional `David Bianco`.

Source: [Pyramid Of Pain](http://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html)

In this section we are applying our search (hunt) towards the `spotting of the adversary` for scenarios that include but are not limited to:

* The commands run by an adversary leave trails of the type usage or intent they had 
* Or some specific software has unique commandline parameters that can be used to identify their presence

```sql
# Presence: Mimikatz Cli - IoA
#
#   When `mimikatz` is compiled by someone, they may introduce code changes.
#   If they run `mimikatz` from disk, and not an in-memory payload, we can use the CLI params.
#
#   Therefore, hunting for it with hashes may not provide results, let's see if the commandline
#   parameters can be found.
#
#       We:
#           - Focus our hunt on the parameters
#
CommandLineHistory command_line
    WHERE CommandLineHistory command_line contains "SEKURLSA::"
        OR CommandLineHistory command_line contains "CRYPTO::"
        OR CommandLineHistory command_line contains "KERBEROS::"
        OR CommandLineHistory command_line contains "LSADUMP::"
        OR CommandLineHistory command_line contains "TOKEN::"
        OR CommandLineHistory command_line contains "MISC::"
```

## **Clean Result - Good Job!**

With the below results, plus running initial hash based hunts, we begin to feel more confident that so far the presence of mimikatz is low.

![image](https://user-images.githubusercontent.com/11415591/80040594-6ae5eb80-84c8-11ea-9b62-158f51557c47.png)

<br />

# IoA - Commonly Observed Syntax for Powershell Precursors


```sql
# Presence: Powershell ShortHand Syntax
#
#   Powershell has short-hand syntax for its language to ease the use.
#   A short-hand is different than a powershell `alias`.
#
#   A short-hand can be identified as:
#       -iex    shorthand for the commandlet Invoke-Expresion
#
#   Therefore, by hunting for commandline usage, we can save ourselves work and explore how
#   that language is being used, and possibly if present, where it occurred.
#
#       We:
#           - Focus our hunt on the parameters
#
ProcessHistory parent_cmdline
    WHERE ProcessHistory parent_cmdline contains "-exec bypass -e"
        OR ProcessHistory parent_cmdline contains "-NoP -NonI -W Hidden -E"
        OR ProcessHistory parent_cmdline contains "-noni -nop -w hidden -e"
        OR ProcessHistory parent_cmdline contains "-nop -w hidden -e"
        OR ProcessHistory parent_cmdline contains "-nop -w hidden -encodedcommand"
        OR ProcessHistory parent_cmdline contains "-w hidden -en"
        OR ProcessHistory parent_cmdline contains "-nop -w hidden -exec bypass -enc"
        OR ProcessHistory parent_cmdline contains "-nop -exec bypass encodedcommand"
        OR ProcessHistory parent_cmdline contains "-nop -sta -w 1 -enc"
        OR ProcessHistory parent_cmdline contains "-nop -w hidden -exec bypass -enc"
```
<br />

![image](https://user-images.githubusercontent.com/11415591/80042026-f745dd80-84cb-11ea-9830-2720a234ba60.png)

<br/>

## Alternatively - CommanLineHistory Collector

The `CommandLineHistory` collector gives you the ability to access historical data across your enterprise beyond 30 days.

<br />

```sql
CommandLineHistory command_line
    WHERE CommandLineHistory command_line contains "-exec bypass -e"
        OR CommandLineHistory command_line contains "-NoP -NonI -W Hidden -E"
        OR CommandLineHistory command_line contains "-noni -nop -w hidden -e"
        OR CommandLineHistory command_line contains "-nop -w hidden -e"
        OR CommandLineHistory command_line contains "-nop -w hidden -encodedcommand"
        OR CommandLineHistory command_line contains "-w hidden -en"
        OR CommandLineHistory command_line contains "-nop -w hidden -exec bypass -enc"
        OR CommandLineHistory command_line contains "-nop -exec bypass encodedcommand"
        OR CommandLineHistory command_line contains "-nop -sta -w 1 -enc"
        OR CommandLineHistory command_line contains  "-nop -w hidden -exec bypass -enc"
```
