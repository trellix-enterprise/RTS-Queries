# Networking - DNSCache

## **Which Entries Are For A Domain Hostname - SINGLE**
```sql
    DnsCache hostname, ipaddress
        WHERE DnsCacache hostname equals "foo.com"
```

## **Which Entries Are For A Domain Hostname - MANY**
```sql
    DnsCache hostname, ipaddress
        WHERE DnsCacache hostname equals "foo.com"
            OR DnsCache hostname equals "bar.com"
            OR DnsCache hostname equals "baz.com"
```

## **Which Entries Are For A Domain IP - SINGLE**
```sql
    DnsCache hostname, ipaddress
        WHERE DnsCacache hostname equals "1.1.1.1"
```

## **Which Entries Are For A Domain IP - MANY**
```sql
    DnsCache hostname, ipaddress
        WHERE DnsCacache hostname equals "1.1.1.1"
            OR DnsCache hostname equals "2.2.2.2"
            OR DnsCache hostname equals "3.3.3.3"
```
