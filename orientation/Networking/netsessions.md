# Networking - Sessions

## **Network Sessions By Non-System Drives or IPC$ Shares**

```
NetworkSessions computer, user, client, file
    WHERE NetworkSessions file not ends with "$"
```

## **Network Sessions By CIFS Share Type**

```
NetworkSessions computer, user, client, file
    WHERE NetworkSessions file equals "cifsshare"
```

## **Network Sessions By Specific User - SINGLE**

```
NetworkSessions computer, user, client, file
    WHERE NetworkSessions user equals "alice"
```

## **Network Sessions By Specific User - MANY**

```
NetworkSessions computer, user, client, file
    WHERE NetworkSessions user equals "alice"
        OR NetworkSessions user equals "bob"
        OR NetworkSessions user equals "frank"
```

## **Network Sessions By Source System - SINGLE**

```
NetworkSessions computer, user, client, file
    WHERE NetworkSessions computer equals
```