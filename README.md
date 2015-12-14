# uberspace_tools
#Checking disk quota and send a mail if more than treshold:

```
#!/bin/bash
CURRENT=$(du -s $HOME |sed 's/\s.*$//')
THRESHOLD=5000000

if [ "$CURRENT" -gt "$THRESHOLD" ] ; then
    mail -s 'Disk Space Alert' mail@domain.com << EOF
Your remaining free disk quota is critically low. Used: $CURRENT
EOF
fi
```
