# Email Backup Strike Report Using Python

Warning: this code is provided on a best effort basis and is not in any way officially supported or sanctioned by Cohesity. The code is intentionally kept simple to retain value as example code. The code in this repository is provided as-is and the author accepts no liability for damages resulting from its use.

This script sends an HTML-formatted backup strike report to Email recipients

## Download the script

You can download the scripts using the following commands:

```bash
# download commands
curl -O https://raw.githubusercontent.com/bseltz-cohesity/scripts/master/python/strikeReport/strikeReport.py
curl -O https://raw.githubusercontent.com/bseltz-cohesity/scripts/master/python/strikeReport/pyhesity.py
chmod +x strikeReport.py
# end download commands
```

## Components

* strikeReport.py: the main powershell script
* pyhesity.py: the Cohesity REST API helper module

Place both files in a folder together and run the main script like so:

```bash
./strikeReport.py -v mycluster \
                  -u myusername \
                  -d mydomain.net \
                  -t myuser@mydomain.net \
                  -t anotheruser@mydomain.net \
                  -s 192.168.1.95 \
                  -f backupreport@mydomain.net
```

## Parameters

* -v, --vip: DNS or IP of the Cohesity cluster to connect to
* -u, --username: username to authenticate to Cohesity cluster
* -d, --domain: (optional) domain of username, defaults to local
* -s, --mailserver: SMTP gateway to forward email through
* -p, --mailport: (optional) defaults to 25
* -f, --sendfrom: email address to show in the from field
* -t, --sendto: email addresses to send report to (use repeatedly to add recipients)