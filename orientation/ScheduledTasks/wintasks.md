# Win ScheduledTasks

## **Find a ScheduledTask By Name**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status taskname equals "foo_task"
```

## **Which Tasks Are Ready**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
```

## **Which Tasks Are Disabled**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Disabled"
```

## **Which Tasks Have ServiceAccount as LogonType**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "ServiceAccount"
```

## **Which Tasks Have an IdentityGroup as LogonType**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "Group"
```

## **Which Tasks Have an assigned Password as LogonType**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "Password"
```

## **Which Tasks Have an assigned InteractiveToken as LogonType**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "InteractiveToken"
```

## **Which Tasks Have an assigned InteractiveToken or Password as LogonType**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "InteractiveToken or Password"
```

## **Which Tasks Have an assigned InteractiveToken or Password as LogonType**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "InteractiveToken or Password"
```

## **Which Tasks Have an assigned Service For User (S4U) as LogonType**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "S4U"
```


## **Which Tasks Are Run By User: SINGLE**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks username equals "jdoe"
```

## **Which Tasks Are Run By User: MANY**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks username equals "jdoe"
        OR ScheduledTasks username equals "alice"
        OR ScheduledTasks username equals "bob"
```

## **Which Tasks Run Powershell**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks taskrun contains "powershell"
```

## **Which Tasks Run Powershell From UserSpace**

```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks taskrun contains "powershell"
        AND ScheduledTasks taskrun contains "C:\Users"
```

## **Filter and Refine Result by Exluding**
```sql
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type not equals "Group"
        AND ScheduledTasks logon_type not equals "ServiceAccount"
        AND ScheduledTasks logon_type not equals "Password"
        AND ScheduledTasks logon_type not equals "InteractiveToken"
        AND ScheduledTasks logon_type not equals "InteractiveToken or Password"
        AND ScheduledTasks logon_type not equals "S4U"
```
