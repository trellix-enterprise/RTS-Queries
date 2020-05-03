# User Logins

## **Who are the active users in my enterprise**

```sql
HostInfo hostname
    AND InteractiveSessions userid, name
        WHERE InteractiveSessions userid not equals ""
            AND InteractiveSessions name not equals ""
```

## **Where has user JDOE logged-in**

```sql
HostInfo hostname
    AND InteractiveSessions userid, name
        WHERE InteractiveSessions userid equals "jdoe"
```

## **Find if a list of users logged-in to ONE Target PC**

```sql
HostInfo hostname
    AND InteractiveSessions userid, name
        WHERE HostInfo hostname equals "PC1"
            AND InteractiveSessions userid equals "jdoe"
                OR InteractiveSessions userid equals "alice" 
                OR InteractiveSessions userid equals "bob" 
```

## **Show me all Logins to ONE Target PC**

```sql
HostInfo hostname
    AND InteractiveSessions userid, name
        WHERE HostInfo hostname equals "W10-LATEST"
            AND InteractiveSessions userid not equals ""
```


## **Show me all Logins to MANY Target PCs**

```sql
HostInfo hostname
    AND InteractiveSessions userid, name
        WHERE HostInfo hostname equals "PC1"
            OR HostInfo hostname equals "PC2"
            OR HostInfo hostname equals "PC3"
```
