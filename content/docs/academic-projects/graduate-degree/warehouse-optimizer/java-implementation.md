---
title: "Java Implementation"
date: 2018-01-10
github: ""
weight: 3
draft: false
bookCollapseSection: true
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---

The Java implementation aimed to achieve the same results as the previous tool, but this time using AMPL for the optimization process. Here the group distinguished itself from the rest because it opted to use the public API of NEOS Server to perform the optimization.

## Principle of application
The Java application would be responsible for maintaining a list of the positions of the different product pallets. When the user requested that an optimization be made, the application would take charge of transforming the information it had stored in a format compatible with AMPL and make the connection to the NEOS server to request the resolution of the problem. When he received the answer, he presented it to the user and asked if he wanted to apply the changes. If so, it applied the changes and returned the command to the user.

## Resolution of previous problems
The structuring of this application presupposed the existence of another project carried out in another corrective unit and which the group did not have. After exposing the problem to teachers and in the absence of a base project that could be provided by teachers, the group opted for a remedy for the situation. This previous project would serve to populate the application in Java with data to be used in the optimization and having no time to do this project, the group decided to write the instructions to populate the application in the class and thus be able to fulfill the final objective. It was not the ideal solution, but taking into account the short time for the delivery of the project and not being the object of evaluation, this path ended up being chosen.
