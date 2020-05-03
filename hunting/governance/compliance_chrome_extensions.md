# Governance - Chrome Browser Extensions

In some cases, a SOC supports enterprise governance business units for continuous risk management needs through dedicated security monitoring techniques.

This section bootstraps a common need for the SOC to discover and confirm the density of unapproved software programs across the enterprise.

We are using an example here for the installed McAfee DLP browser extension.  Keep in mind that while the files that make up the extension can be present on the computer of the end-user,

it may notbe enabled in the Chrome browser.


## **Discover if the DLP Extension is installed**

```sql
Files created_at, last_write, name
     WHERE Files full_name contains "hddjhjcbioambdhjejhdlobijkdnbggp"
```


## **Discover Which Systems Have Extensions Installed - SINGLE**

```sql
# We search for a single target extension
#
#
HostInfo hostname
   AND Files created_at, last_write, name
      WHERE Files full_name contains "hddjhjcbioambdhjejhdlobijkdnbggp"
```

## **Discover Which Systems Have Extensions Installed - MANY**

```sql
# We search for a many target extensions
#
#
HostInfo hostname
   AND Files created_at, last_write, name
      WHERE Files full_name contains "hddjhjcbioambdhjejhdlobijkdnbggp"
         OR Files full_name contains "efaidnbmnnnibpcajpcglclefindmkaj"
         OR Files full_name contains "jlhmfgmfgeifomenelglieieghnjghma"  
```


## **Confirm A Chrome Manifest File is Present**

A chrome manifest.json file is key to the inner-workings of Chrome Extensions.

By finding and reading this file you can glean relevant details about the extensions design and structure.

```sql
HostInfo hostname
   AND Files created_at, last_write, name
      WHERE Files full_name contains "hddjhjcbioambdhjejhdlobijkdnbggp"
         OR Files full_name contains "efaidnbmnnnibpcajpcglclefindmkaj"
         OR Files full_name contains "jlhmfgmfgeifomenelglieieghnjghma"
            AND File name equals "manifest.json"
```
