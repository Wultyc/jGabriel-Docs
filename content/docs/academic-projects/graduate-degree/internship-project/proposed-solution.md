---
title: "Proposed Solution"
date: 2020-06-11T21:19:22+01:00
github: ""
weight: 30
draft: false
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---
Several solutions were proposed with different combinations of products and services, some of them commercial, but the final choice turned out to be to build a new application in PHP with the Laravel framework using a Microsoft SQL Server database (due to the familiarity that already existed with the product). This application would run on a server provided by the company.

This application would have to correspond to a list of requirements that stands out:
- Access only on the local network
- Existence of a restricted administration area
- The implementation would have to be done in two phases:
    - The first where the existing application in the factory is completely replaced (point registration, collections, production, finished product and finished product output);
    - The second phase during which the new features would be applied incrementally;

# Structure of the new application

## Data base
The first step was to define the data model. This was based on what already existed but with some modifications that would help in the cohesion of the information with the minimum impact on performance.

## Application
The Application has been divided into two different sub-applications:
- The factory application, used by workers to make records. The routes of this application are within `` `/ Fabrica /` ``
- The administration panel, used by administrators to manage records. The routes of this application are within `` / Panel / ''

## As Stored Procedures
The option for this feature was related to the familiarity with the DaDOS Base Management System, Microsoft SQL Server. In this way, these modules could be created, updated, deleted without knowledge of PHP / Laravel to modify the application.
