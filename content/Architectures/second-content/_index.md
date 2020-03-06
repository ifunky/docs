---
title: "Landing Zone Pattern"
date: 2019-12-04T09:16:17Z
draft: false
disableToc: false
pre: "<i class='fab fa-github'></i> "
weight: 1
---

### Overview

The landing zone is a standard pattern for segregating AWS infrastructure which results in setting up a secure, multi-account AWS environment based on AWS best practices.

## Accounts
Multiple accounts are used and we have two classifations for different types based on the intendedn purpose.


**Core Accounts**

As the name suggested these accounts are core to the organisation setup and will be built as part of the initial setup

| Name | Description |
|--|--|
| Master | Organisation master account used to manage member accounts.   Billing and other features that can be managed centrally. |
| Security | Used for automated security testing |
| Identity | This is where users are created and cross account access granted using roles and groups |
| Shared | Services used across the organisation such as AD, AMI creation etc |
| Audit | Centralised auditing and logging account - CloudTrail, Config |

**Resource Accounts**

These types of accounts are more generic in nature and can represent small isolated sandbox environments through to production workloads.

| Name | Description |
|--|--|
| Production | Customer facing and production workloads |
| Development | Development and testing account |