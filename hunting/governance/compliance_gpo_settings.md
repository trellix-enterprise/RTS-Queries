# **Governance - Configuration Settings Compliance**

In some cases, a SOC supports enterprise governance business units for continuous risk management needs through the applied monitoring techniques.

This section bootstraps a common need for the SOC to discover and confirm the density of unapproved software programs across the enterprise.

We are using an example here for the validation of Windows Registry Settings to confirm a countermeasure is in effect - as intended.

<br />

## **Confirming Enterprise Powershell Settings**

Here we want to find machines that have the `unrestricted` execution policy set. This is a weakness the company would like to avoid.

```sql
WinRegistry 
    WHERE WinRegistry keypath equals "HKLM\SOFTWARE\Wow6432Node\Policies\Microsoft\Windows\PowerShell"
        AND WinRegistry valuedata equals "Unrestricted"
```
<br />


![image](https://user-images.githubusercontent.com/11415591/80029874-6c59e880-84b5-11ea-846e-5957769e4899.png)

<br/>

## **Bonus - Take Action**

![image](https://user-images.githubusercontent.com/11415591/80030495-41bc5f80-84b6-11ea-981f-43b1bb6922da.png)
