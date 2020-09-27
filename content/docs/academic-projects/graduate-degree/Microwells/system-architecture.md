---
title: "System Architecture"
date: 2020-06-11T16:40:57+01:00
github: ""
weight: 10
draft: false
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---

The system as a whole worked in a very simple way and was composed of three elements:
- The modules: used to read vital signs and communicate this information to the Microwells Box.
- Microwell Box: A device where the different modules could be connected. It would collect information from the modules and send it to the cloud service.
- Miocrowell Cloud: A cloud service for storing read data for future reference.
<center>
{{<figure src="/images/projetos-academicos/licenciatura/microwells/architecture.jpg">}}
</center>