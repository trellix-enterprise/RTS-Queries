# Win Patches

## **What Patches Are Installed**
```
InstalledUpdates hotfix_id, install_date, installed_by, description
```

## **Which Patches Are Security Updates**
```sql
InstalledUpdates hotfix_id, install_date, installed_by, description
    WHERE InstalledUpdates description equals "Security Update"
```

## **Which Patches Are HotFix Updates**
```sql
InstalledUpdates hotfix_id, install_date, installed_by, description
    WHERE InstalledUpdates description equals "HotFix"
```

## **Which Patches Were Not Installed by NT AUTHORITY**

```sql
InstalledUpdates hotfix_id, install_date, installed_by, description
    WHERE InstalledUpdates installed_by not equals "NT AUTHORITY/SYSTEM"
        AND InstalledUpdates installed_by not equals ""
```

## **Specify - Patch by KB Number**
```sql
InstalledUpdates hotfix_id, install_date, installed_by, description
    WHERE InstalledUpdates hotfix_id equals "KB3097992"
```

## **Specify - Patch by Date Installed**

```sql
InstalledUpdates hotfix_id, install_date, installed_by, description
    WHERE InstalledUpdates installed_date after "2018-03-01"
```

## **Specify - Track a Patch After a Response Date**

```
# WannaCry Example of Patches from:
https://support.microsoft.com/en-us/help/4023262/how-to-verify-that-ms17-010-is-installed
```

```sql
InstalledUpdates hotfix_id, install_date, installed_by, description     
    WHERE InstalledUpdates install_date after "2018-03-01"
        AND InstalledUpdates hotfix_id ends with "KB4012212"
            OR InstalledUpdates hotfix_id ends with "KB4012215"
            OR InstalledUpdates hotfix_id ends with "KB4012218"
            OR InstalledUpdates hotfix_id ends with "KB4015549"
```
