# Filesystem

## **What Files are in UserSpace: C:\Users**

```sql
Files create_process_pid, full_name, status
    WHERE Files dir starts with "C:\Users"
```


## **What Files are Executables in UserSpace: C:\Users**

```sql
Files create_process_pid, full_name, status
    WHERE Files dir starts with "C:\Users" 
        AND Files name ends with ".exe"
```

## **Which Powershell Scripts are in UserSpace: C:\Users**

```sql
Files create_process_pid, full_name, status
    WHERE Files dir starts with "C:\Users"
        AND Files dir contains "AppData"
            AND Files name ends with ".ps1"
```

## **What Files Hint as Google Extensions**

```sql
Files create_process_pid, full_name, status
    WHERE Files dir starts with "C:\Users"
        AND Files dir contains "AppData\Local\Google\Chrome\User Data\Default\Extensions" 
```

## **What Files are Currently Present In UserSpace: C:\Users**

```sql
Files create_process_pid, full_name, status
    WHERE Files status equals "current"
        AND Files dir starts with "C:\Users"
```

## **What Files were Deleted From UserSpace: C:\Users**

```sql
Files create_process_pid, full_name, status
    WHERE Files status equals "deleted"
        AND Files dir starts with "C:\Users"
```

## **Which Process Wrote a File By Hash - SINGLE**

```sql
Files create_process_pid, full_name, status
    WHERE Files sha256 equals "33b5995518f2df4a2d9a38f74b736ebbe562901b68f8f7b68d875b8f1d71b8b9"
```

## **Which Process Wrote a File By Hash - MANY**

```sql
Files create_process_pid, full_name, status
    WHERE Files sha256 equals "33b5995518f2df4a2d9a38f74b736ebbe562901b68f8f7b68d875b8f1d71b8b9"
        OR Files sha256 equals "b335e9c16bc51168230903c125c9c1faafed5a05a4c738c113a87502340c25dc"
        OR Files sha256 equals "b9a4f5293fecc3619d436a45a4be1ab3b90f6c9b6aef2ca13e21b5dc5b0e3da9"
```

## **Which Files Were Created After a Date**

```sql
Files create_process_pid, full_name, status
    WHERE created_at after "2020-01-01"
```

## **Which Files Were Created Before a Date**

```sql
Files create_process_pid, full_name, status
    WHERE created_at before "2020-01-01"
```

## **Which Files Were Deleted After a Date**

```sql
Files create_process_pid, full_name, status
    WHERE deleted_at after "2020-01-01"
```

## **Which Files Were Deleted Before a Date**

```sql
Files create_process_pid, full_name, status
    WHERE deleted_at before "2020-01-01"
```

## **Which Files Were Last Modified Before a Date**

```sql
Files create_process_pid, full_name, status
    WHERE last_write before "2020-01-01"
```

## **Which Files Were Last Modified After a Date**

```sql
Files create_process_pid, full_name, status
    WHERE last_write after "2020-01-01"
```
