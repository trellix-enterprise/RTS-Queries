# Win Services

## **Which Have Services Startup: Manual**

```
Services startuptype, name, user, status
    WHERE Services startuptype equals "Manual"
```

## **Which Have Services Startup: Automatic**

```
Services startuptype, name, user, status
    WHERE Services startuptype equals "Automatic"
```

## **Which Services Are Running**

```
Services startuptype, name, user, status
    WHERE Services status equals "Running"
```

## **Which Services Are NOT Running**

```
Services startuptype, name, user, status
    WHERE Services status equals "Stopped"
```

## **Which Services Running as Non-System Identities**

```
Services startuptype, name, user, status
    WHERE Services status equals "Running"
        AND Services user not equals "LocalService"
        AND Services user not equals "LocalSystem"
        AND Services user not contains "NT AUTHORITY\"
        AND Services user not contains "NT Service\"
```