# C2P-Manuals
So Toby can control the manuals in a sensible way

The manuals live on big5 in directory /home/manuals

To rebuild the manuals you run 

```
cd /home/manuals
jeykll build
```

This will recreate the site under /home/manuals/_site

The main files to edit are in _includes and are in mark down format.

NOTE to not put anything company specific into these files.

Company specific info is under each company directory

e.g:-

```root@big5 /home/manuals # more RBS/manuals/desktop/index.md 
---
title: Desktop
weight: 1
layout: default
email: rob.moir@rbs.co.uk
company: RBS
company_url: https://www.click2park.co.uk/RBS/
company_email: fpgwo1@rbos.co.uk
company_site: Gogarburn
noToc: false
showToggleButton: false
---
{% include desktop.md %}
```

So here you edit desktop.md to change the contect for all files, and within this file you use things like {{ page.company_site }}
 to reference the variables above within this doc.
 
 
