### authenticated_sql_injection_helpdeskz

Proof of concept for authenticated SQL injection in HelpDeskZ version v1.0.2 or earlier. No CVE has been assigned to this vulnerability.

Tested on [HTB: Help](https://app.hackthebox.com/machines/Help)

### Installation

Clone the GitHub repository and install python requirements:

```sh
git clone https://github.com/jsec02/poc.git \
    && cd poc/authenticated_sql_injection_helpdeskz \
    && pip install -r requirements.txt --break-system-packages
```

### Usage

This exploit requires the authenticated user to submit a ticket with a valid attachment and obtain the ticket and attachment ID's beforehand.

```
usage: sqli.py [-h] --url URL --email EMAIL --password PASSWORD
               --ticket TICKET --attachment ATTACHMENT

options:
  -h, --help            show this help message and exit
  --url URL             Base URL for HelpDeskZ.
  --email EMAIL         The email to authenticate with.
  --password PASSWORD   The password to authenticate with.
  --ticket TICKET       The ID of a ticket with an attachment.
  --attachment ATTACHMENT
                        The ID of a valid attachment.
```

### Example

```sh
python exploit.py --url http://10.10.10.10. --email email@email.com --password password --ticket 1 --attachment 1
```
