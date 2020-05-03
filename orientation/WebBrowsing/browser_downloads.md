# Browser Downloads

## **Which Browsers are used in my environment**

```
BrowserDownload browser
```

## **Prevalence -  Downloads by MimeType**

```sql
BrowsewrDonload mime_type, total_bytes
```

## **Prevalence -  Downloads by Binary Type**

```sql
BrowserDownload mime_type, file_path
    WHERE BrowserDownload mime_type contains "octet-stream"
```

## **Prevalence -  Downloads by Zip Archive Type**

```sql
BrowserDownload mime_type, file_path
    WHERE BrowserDownload mime_type equals "application/zip"
```

## **Prevalence -  Downloads by MANY Compressed Archive Type**

```sql
BrowserDownload mime_type, file_path
    WHERE BrowserDownload mime_type equals "application/zip"
        OR BrowserDownload mime_type equals "application/x-zip-compressed"
        OR BrowserDownload mime_type equals "application/x-tar"
```

## **Prevalence -  Websites Offering Downloads of Binary Type**

```sql
BrowserDownload site_url, mime_type
    WHERE BrowserDownload mime_type contains "octet-stream"
```

### **Specify SINGLE Target Website**

```sql
BrowserDownload site_url, mime_type
    WHERE BrowserDownload mime_type contains "octet-stream"
        AND BrowserDownload site_url contains "github.com"
```

### **Specify MANY Target Websites**

```sql
BrowserDownload site_url, mime_type
    WHERE BrowserDownload mime_type contains "octet-stream"
        AND BrowserDownload site_url contains "github.com"
            OR BrowserDownload site_url contains "drive.google.com"
            OR BrowserDownload site_url contains "super.com"
```

### **Specify SINGLE Target Filename**

```sql
BrowserDownload site_url, mime_type, file_path
    WHERE BrowserDownload mime_type contains "octet-stream"
        AND BrowserDownload file_path contains "zoom.exe"
```

### **Specify MANY Target Filenames**

```sql
BrowserDownload site_url, mime_type, file_path
    WHERE BrowserDownload mime_type contains "octet-stream"
        AND BrowserDownload file_path contains "foo.exe"
            OR BrowserDownload file_path contains "bar.exe"
            OR BrowserDownload file_path contains "baz.exe"
```

## **Prevalence -  Downloads By Web Referrer and Web Provider**

```sql
BrowserDownload referrer, site_url
    WHERE BrowserDownload referrer not equals ""
        AND BrowserDownload site_url not equals ""
```

### **Specify Download By Referrer To Provider Combination**

```sql
BrowserDownload referrer, site_url
    WHERE BrowserDownload referrer contains "evil_foo.com"
        AND BrowserDownload site_url not equals "drive.google.com"
```
