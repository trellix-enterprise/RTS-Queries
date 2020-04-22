# Hunting For Indicators Of Compromise - IoCs: Hashes

In some cases, a SOC approaches monitoring proactively through dedicated threat hunting expertise.

One fantastic resource to understand the increased levels of context for IOCs is the `Pyramid Of Pain` created by
security professional `David Bianco`.

Source: [Pyramid Of Pain](http://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html)


In this section we show how to use RTS to search (hunt) for IOCs in the form of file hashes

<br />

```bash
# Presence: Agent Tesla IOCs - Files

Files sha256, created_at, name
    WHERE Files sha256 equals "af0555109dfa352a7aafb70c3f63e8411b6cf8efe3398f99de55365efb34688e"
        OR Files sha256 equals "fa11c41dbec328a4b75aaf7e6b349c872948203e0109aea6ba6686780b34c85f"
        OR Files sha256 equals "1d2bae6f14d7cdeaa2ee1819d352eca0978538387ae174e52ef2228034f362c3"
        OR Files sha256 equals "51d3563c7aa0c4752bc8ce9c1d6d18b5f2d61d91358c71a4de16803c5fa1f877"
```
<br />

![image](https://user-images.githubusercontent.com/11415591/80036272-69fc8c00-84bf-11ea-8306-56225fc4ea33.png)

<br />

```bash
# Execution: Agent Tesla IOCs - ProcessExecution

ProcessHistory sha256, started_at, name, cmdline
    WHERE ProcessHistory sha256 equals "af0555109dfa352a7aafb70c3f63e8411b6cf8efe3398f99de55365efb34688e"
        OR ProcessHistory sha256 equals "fa11c41dbec328a4b75aaf7e6b349c872948203e0109aea6ba6686780b34c85f"
        OR ProcessHistory sha256 equals "1d2bae6f14d7cdeaa2ee1819d352eca0978538387ae174e52ef2228034f362c3"
        OR ProcessHistory sha256 equals "51d3563c7aa0c4752bc8ce9c1d6d18b5f2d61d91358c71a4de16803c5fa1f877"
```
<br />

```bash
# Aftermath: Agent Tesla IOCs - Registry Persistence

WinRegistry
    WHERE WinRegistry keypath equals "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run\UoOfbM"
        OR WinRegistry keypath equals "HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\StartupApproved\Run\UoOfbM"
```