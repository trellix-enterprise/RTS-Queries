# Networking - Sessions

## **Network Sessions By Non-System Drives or IPC$ Shares**

```sql
NetworkSessions computer, user, client, file
    WHERE NetworkSessions file not ends with "$"
```

## **Network Sessions By CIFS Share Type**

```sql
NetworkSessions computer, user, client, file
    WHERE NetworkSessions file equals "cifsshare"
```

## **Network Sessions By Specific User - SINGLE**

```sql
NetworkSessions computer, user, client, file
    WHERE NetworkSessions user equals "alice"
```

## **Network Sessions By Specific User - MANY**

```sql
NetworkSessions computer, user, client, file
    WHERE NetworkSessions user equals "alice"
        OR NetworkSessions user equals "bob"
        OR NetworkSessions user equals "frank"
```

## **Network Sessions By Source System - SINGLE**

```sql
NetworkSessions computer, user, client, file
    WHERE NetworkSessions computer equals "PC1"
```
