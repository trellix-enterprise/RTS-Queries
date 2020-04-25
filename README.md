# MVISION EDR RTS-Queries

Welcome to the public knowledge-ground to bootstrap your expertise for hunting and thriving with MVISION EDR Real Time Search - RTS.

In this section we provide practical reasons and examples of baseline queries practitioners adopt for `learning the environment` they are defending.

We are aiming to relate our query examples with public domain resources like `SANS`, or research from individual security professionals in the community.

## Using this repo
In the code blocks, we are providing the query syntax, you can copy/paste into your Real Time Search - RTS.

Throughout the content, we build from basic to more elaborate queries.

This repo is broken down by category of collectors in each section, and the table below represents how to find/associate queries to use-cases.


### **Query Language Orientation**
The table below serves as the initial orientation of the McAfee Real Time Search (RTS) language.

Practitioners can find practical a `how-to` for MVISION Collectors and advance their needs for unique threat hunts applicable to their needs.

<br />

Category|Location|
--------|--------|
FileSystem | Queries That Support File Activity (CRUD)|
Networking | Queries That Supoport Network Flow Activity|
User Logins | Queries That Support Windows Logins|
Processes | Queries That Support Process Execution Activity|
Patches | Queries That Support HotFix Information|
Registry| Queries That Support The Presence of Info in the WinRegistry|
Services| Queries That Support The Windows Service Manager Activity|
Software| Queries That Support Software Versioning|
CVEs | Soon |
IoCs | Soon|


<br />

## Query Examples
Below you can see the format of this guide.  We will expose the question (need) in **bold** and the query used to answer the question.

### Example - Systems Management Needs

#### What Systems have MVision EDR Installed

```
HostInfo connection_status, hostname, ip, platform
```

#### What Systems are actively managed and are ONLINE

```
HostInfo connection_status, hostname, ip, platform
    WHERE HostInfo connection_status equals "Online"
```

#### What Systems are actively managed and are not a Windows PC

```
HostInfo connection_status, hostname, ip, platform
    WHERE HostInfo connection_status equals "Online"
        AND HostInfo platfom not equals "Windows"
```
<br />
<br />

### Repository Contacts
Repo Owners | Email Contact|
------------|--------------|
Carlos Diaz | carlos_diaz@mcafee.com|
Ismael Valenzuela | ismael_valenzuela@mcafee.com|
