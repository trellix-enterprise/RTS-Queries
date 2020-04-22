# **Governance - Software Compliance**

In some cases, a SOC supports enterprise governance business units for continuous risk management needs through dedicated security monitoring techniques.

This section bootstraps a common need for the SOC to discover and confirm the density of unapproved software programs across the enterprise.

We are using an example here for the installed versions of the Zoom web conferencing software

## **Step 1- Discover Number of Systems & Versions of the Target Software**

```
HostInfo hostname
    AND Software installdate, publisher, version, displayname
        WHERE Software displayname contains "zoom"
```
<br />

![image](https://user-images.githubusercontent.com/11415591/80023381-71199f00-84ab-11ea-825a-ea4296af218f.png)

<br/>

## **Step 2 - Discover Source Locations Used To Download The Target Software**

```
HostInfo hostname
    AND BrowserDownload referrer, site_url, mime_type, browser, user_profile
        WHERE BrowserDownload file_path contains "zoom"
```
<br />

![image](https://user-images.githubusercontent.com/11415591/80024106-8a6f1b00-84ac-11ea-8e44-cb5f88f16c7a.png)

<br/>

## **Step 3 - Get Some Hashes, Might Be Good for App Control**

```
HostInfo hostname
    AND Files create_process_pid, full_name, status
        WHERE Files dir starts with "C:\Users"
            AND Files full_name equals "zoom.exe"
```
<br />

![image](https://user-images.githubusercontent.com/11415591/80027088-30bd1f80-84b1-11ea-93a3-f51fb6540a48.png)

<br />

## **Bonus - Export To CSV**
Enable other teams that take response actions by exporting the data


![image](https://user-images.githubusercontent.com/11415591/80028646-6fec7000-84b3-11ea-9c29-bb032139df49.png)