# Win ScheduledTasks

## **Find a ScheduledTask By Name**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status taskname equals "foo_task"
```

## **Which Tasks Are Ready**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
```

## **Which Tasks Are Disabled**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Disabled"
```

## **Which Tasks Have ServiceAccount as LogonType**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "ServiceAccount"
```

## **Which Tasks Have an IdentityGroup as LogonType**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "Group"
```

## **Which Tasks Have an assigned Password as LogonType**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "Password"
```

## **Which Tasks Have an assigned InteractiveToken as LogonType**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "InteractiveToken"
```

## **Which Tasks Have an assigned InteractiveToken or Password as LogonType**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "InteractiveToken or Password"
```

## **Which Tasks Have an assigned InteractiveToken or Password as LogonType**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "InteractiveToken or Password"
```

## **Which Tasks Have an assigned Service For User (S4U) as LogonType**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type equals "S4U"
```


## **Which Tasks Are Run By User: SINGLE**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks username equals "jdoe"
```

## **Which Tasks Are Run By User: MANY**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks username equals "jdoe"
        OR ScheduledTasks username equals "alice"
        OR ScheduledTasks username equals "bob"
```

## **Which Tasks Run Powershell**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks taskrun contains "powershell"
```

## **Which Tasks Run Powershell From UserSpace**

```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks taskrun contains "powershell"
        AND ScheduledTasks taskrun contains "C:\Users"
```

## **Filter and Refine Result by Exluding**
```
ScheduledTasks status, logon_type, taskname, last_run, next_run_time, username, folder, taskrun
    WHERE ScheduledTasks status equals "Ready"
        AND ScheduledTasks logon_type not equals "Group"
        AND ScheduledTasks logon_type not equals "ServiceAccount"
        AND ScheduledTasks logon_type not equals "Password"
        AND ScheduledTasks logon_type not equals "InteractiveToken"
        AND ScheduledTasks logon_type not equals "InteractiveToken or Password"
        AND ScheduledTasks logon_type not equals "S4U"
```