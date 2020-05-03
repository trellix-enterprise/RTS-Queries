# Processes - Execution

## **Which System User Identity Executed a Program: By Process - SINGLE**

```sql
Processes user, user_id, name
    WHERE Processes name equals "svchost.exe"
```

## **Which System User Identity Executed a Program: By Process - MANY**

```sql
Processes user, user_id, name
    WHERE Processes name equals "svchost.exe"
        OR Processes name equals "cmd.exe"
        OR Processes name equals "schtasks.exe"
```

## **Which System User Identity Executed a Program: By User Identity - SINGLE**

```sql
Processes user, user_id, name
    WHERE Processes name equals "svchost.exe"
        AND Proceses user equals "alice"
```

## **Which System User Identity Executed a Program: By User Identity - MANY**

```sql
Processes user, user_id, name
    WHERE Processes name equals "svchost.exe"
        AND Proceses user equals "alice"
            OR Processes user equals "bob"
            OR Processes user equals "jane"
```

## **Who is the Parent of A Child Process - SINGLE**

```sql
Processes parentname, name, execution_mode
    WHERE Processes name equals "svchost.exe"
```

## **Who is the Parent of A Child Process - MANY**

```sql
Processes parentname, name, execution_mode
    WHERE Processes name equals "svchost.exe"
        OR Processes name equals "cmd.exe"
        OR Processes name equals "mshta.exe"
```


## **Specify - Parent Process**

```sql
Processes parentname, name, id, execution_mode
    WHERE Processes parentname not equals "services.exe"
        AND Processes name equals "svchost.exe"
```

## **What is the Process ID of The Parent**

```sql
Processes parentname, parentid, name, id, execution_mode
    WHERE Processes name equals "svchost.exe"
```

## **What is the Process ID of The Child**

```sql
Processes parentname, name, id, execution_mode
    WHERE Processes name equals "svchost.exe"
```

## **What is the Source File Location of The Parent**

```sql
Processes parentimagepath, name
    WHERE Processes name equals "svchost.exe"
```

## **What is the Source File Location of The Child**

```sql
Processes imagepath, name
    WHERE Processes name equals "svchost.exe"
```

## **What is the Process ID of The Child**

```sql
Processes parentname, name, id, execution_mode
    WHERE Processes name equals "svchost.exe"
```

## **What is the CommandLine of The Parent**

```sql
Processes parentname, parent_cmdline, name, id
    WHERE Processes name equals "svchost.exe"
        AND parent_cmdline not equals ""
```

## **What is the CommandLine of The Child**

```sql
Processes parentname, cmdline, name, id
    WHERE Processes name equals "svchost.exe"
        AND Processes cmdline not equals ""
```

## **What is the McAfee File Reputation of The Child**

```sql
Processes name, process_reputation
    WHERE Processes name equals "svchost.exe"
```

## **Specify Date of Execution AFTER**

```sql
Processes name, started_at
    WHERE Processes name equals "svchost.exe"
        AND Processes started_at after "2020-01-01"
```

## **Specify Date of Execution BEFORE**

```sql
Processes name, started_at
    WHERE Processes name equals "svchost.exe"
        AND Processes started_at before "2020-04-17"
```


## **Specify Date of Execution RANGE**
```sql
Processes name, started_at
    WHERE Processes name equals "svchost.exe"
        AND Processes started_at after "2020-04-15"
        AND Processes started_at before "2020-04-17"
```
