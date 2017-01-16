sa-secure-audit-rkhunter
========================
[![Build Status](https://travis-ci.org/softasap/sa-secure-audit-rkhunter.svg?branch=master)](https://travis-ci.org/softasap/sa-secure-audit-rkhunter)


Example of use: check box-example

Simple:

```YAML


     - {
         role: "sa-secure-audit-rkhunter"
       }

```


Advanced:

tool will try to install mailutils, if they are not installed. To gain more control over your system,
I would recommend configure system for mail sending in advance, rather than rely on defaults.
sa-postfix is one of the possible roles, included in box-example

```YAML

     - {
         role: "sa-postfix",
         tags: ["create", "update"]
       }
     - {
         role: "sa-secure-audit-rkhunter"
       }


```

Using rkhunter:

```bash

sudo rkhunter -c --sk

```

Idea for cronjob:

```
/usr/bin/rkhunter -c --cronjob 2>&1 | mail -s "RKhunter Scan Results" your@secure.email
```

Database update:

```
sudo rkhunter --update
```





Copyright and license
---------------------

Code licensed under the [BSD 3 clause] (https://opensource.org/licenses/BSD-3-Clause) or the [MIT License] (http://opensource.org/licenses/MIT).

Subscribe for roles updates at [FB] (https://www.facebook.com/SoftAsap/)
