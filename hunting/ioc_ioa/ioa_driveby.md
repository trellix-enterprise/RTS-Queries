# Hunting For Indicators Of Attack - IoAs: HTTP Activity

In some cases, a SOC approaches monitoring proactively through dedicated threat hunting expertise.

One fantastic resource to understand the increased levels of context for IOAs is the `Pyramid Of Pain` created by
security professional `David Bianco`.

Source: [Pyramid Of Pain](http://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html)

In this section we are applying our search (hunt) towards the `spotting of the adversary` for scenarios that include but are not limited to:

* A user is tricked to clicking on unsafe url links stemming from documents or email messages
* Or a user is unaware of unsafe code in their browser, commonly referred to as `drive-by-downloads`

<br />

```bash
# Presence: Pastebin C2 Downloaders: Non-User Initiated
#
#   By setting url_length > 255 characters
#
#       We:
#           - Focus our hunt on behavior for non-user typed urls
#           - Focus on url destinations to pastbin used by malware downloaders
#
BrowserHistory visit_count, url, browser
    WHERE BrowserHistory url_length greater than "255"
        AND BrowserHistory url contains "pastebin.com"
```


<br />

![image](https://user-images.githubusercontent.com/11415591/80038899-864ef780-84c4-11ea-975d-df87d9348c8d.png)
