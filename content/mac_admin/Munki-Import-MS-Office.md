+++
title = "How to import Micrsoft Office 2016 into Munki"
date = 2018-04-27T16:45:32+10:00
description = "Instructions on how to import Micrsoft Office 2016 into Munki"
weight = 20
draft = false
bref = ""
# toc = true
comments = true
+++

### Steps
1. Download the desired installer package.
2. run the following command, being sure to adjust the `<MICROSOFT_OFFICE_PACKAGE>`.pkg location at the start.
```
munkiimport ~/Downloads/<MICROSOFT_OFFICE_PACKAGE> \
--name=MSOffice2016 --catalog=testing --minimum_os_version=10.10 --developer=Microsoft --category=Productivity \
--description="Microsoft Office 2016 for Mac." \
--blocking_application="Microsoft Autoupdate" \
--blocking_application="Microsoft Outlook" \
--blocking_application="Microsoft Excel" \
--blocking_application="Microsoft PowerPoint" \
--blocking_application="Microsoft Word" \
--blocking_application="Microsoft OneNote" \
--file "/Applications/Microsoft Excel.app" \
--file "/Applications/Microsoft OneNote.app" \
--file "/Applications/Microsoft Outlook.app" \
--file "/Applications/Microsoft PowerPoint.app" \
--file "/Applications/Microsoft Word.app" \
--unattended_install
```

3. If you have troube with it constantly trying to 'update' the same package, you may need to remove the 'receipt' check from the Munki pkginfo file for the 'Microsoft AutoUpdate.app'

<br>

[Reference: demystify-office2016](https://clburlison.com/demystify-office2016/)
