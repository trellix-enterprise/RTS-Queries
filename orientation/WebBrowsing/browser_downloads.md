# Browser Downloads

## **Which Browsers are used in my environment**

```
BrowserDownload browser
```

## **Prevalence -  Downloads by MimeType**

```
BrowsewrDonload mime_type, total_bytes
```

## **Prevalence -  Downloads by Binary Type**

```
BrowserDownload mime_type, file_path
    WHERE BrowserDownload mime_type contains "octet-stream"
```

## **Prevalence -  Downloads by Zip Archive Type**

```
BrowserDownload mime_type, file_path
    WHERE BrowserDownload mime_type equals "application/zip"
```

## **Prevalence -  Downloads by MANY Compressed Archive Type**

```
BrowserDownload mime_type, file_path
    WHERE BrowserDownload mime_type equals "application/zip"
        OR BrowserDownload mime_type equals "application/x-zip-compressed"
        OR BrowserDownload mime_type equals "application/x-tar"
```

## **Prevalence -  Websites Offering Downloads of Binary Type**

```
BrowserDownload site_url, mime_type
    WHERE BrowserDownload mime_type contains "octet-stream"
```

### **Specify SINGLE Target Website**

```
BrowserDownload site_url, mime_type
    WHERE BrowserDownload mime_type contains "octet-stream"
        AND BrowserDownload site_url contains "github.com"
```

### **Specify MANY Target Websites**

```
BrowserDownload site_url, mime_type
    WHERE BrowserDownload mime_type contains "octet-stream"
        AND BrowserDownload site_url contains "github.com"
            OR BrowserDownload site_url contains "drive.google.com"
            OR BrowserDownload site_url contains "super.com"
```

### **Specify SINGLE Target Filename**

```
BrowserDownload site_url, mime_type, file_path
    WHERE BrowserDownload mime_type contains "octet-stream"
        AND BrowserDownload file_path contains "zoom.exe"
```

### **Specify MANY Target Filenames**

```
BrowserDownload site_url, mime_type, file_path
    WHERE BrowserDownload mime_type contains "octet-stream"
        AND BrowserDownload file_path contains "foo.exe"
            OR BrowserDownload file_path contains "bar.exe"
            OR BrowserDownload file_path contains "baz.exe"
```

## **Prevalence -  Downloads By Web Referrer and Web Provider**

```
BrowserDownload referrer, site_url
    WHERE BrowserDownload referrer not equals ""
        AND BrowserDownload site_url not equals ""
```

### **Specify Download By Referrer To Provider Combination**

```
BrowserDownload referrer, site_url
    WHERE BrowserDownload referrer contains "evil_foo.com"
        AND BrowserDownload site_url not equals "drive.google.com"
```