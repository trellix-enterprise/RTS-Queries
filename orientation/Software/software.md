# Software Installed & Version Info

## **What Software Is Installed**

```
Software installdate, publisher, version, displayname, displayname
```

## **Which Software Version Am I running - By Program SINGLE**

```
Software installdate, publisher, version, displayname
    WHERE Software displayname contains "zoom"
```

## **Which Software Version Am I running - By Program MANY**

```
Software installdate, publisher, version, displayname
    WHERE Software displayname contains "zoom"
        OR Software displayname contains "google"
        OR Software displayname contains "adobe"
```

## **Which Software Version Am I running - By Version SINGLE**

```
Software installdate, publisher, version, displayname
    WHERE Software displayname contains "zoom"
        AND Software version not equals "4.6"
```

## **Which Software Version Am I running - By Version MANY**

```
Software installdate, publisher, version, displayname
    WHERE Software displayname contains "zoom"
        AND Software version not equals "4.6"
        AND Software version not equals "4.5"
        AND Software version not equals "4.1"
```