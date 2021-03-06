---
menu:
  overview:
    parent: technology
title: Overview for assessors
weight: 50
aliases:
  - /docs/intro/security/for-assessors
  - /intro/security/for-assessors
  - /overview/security/for-assessors/
---

## How cloud.gov works

cloud.gov is a platform as a service (PaaS). This means customers provide the code for their app and we provide the infrastructure, operating system, and supporting technologies required to run the app. Three basic components undergird any cloud.gov app:

1. Hardware and infrastructure-level software, including web servers, relational database servers, DNS routing services, and other systems the customer might need.
1. A container providing the operating system and web server software (NGINX) and other basic software required to run any app. Apps are deployed into this container and isolated from other apps on the platform.
1. Software components specific to the app the customer is launching, deployed along with the customer's app. These components, called buildpacks, provide programming languages and some additional dependencies required by the app. Though it's possible for customers to use their own buildpacks, we strongly encourage customers to use the buildpacks we provide. That way customers can benefit from our security updates (see below).

cloud.gov is built specifically for government. It's based on Cloud Foundry and makes use of Amazon Web Services' GovCloud environment.


## Terminology / Overview of terms

### Organizations

Your work inside cloud.gov takes place within [organizations](http://docs.cloudfoundry.org/concepts/roles.html#orgs), or “orgs” for short. Orgs group together users for management and present a shared perimeter for services, domains and quotas.

### Spaces

Each org contains [spaces](http://docs.cloudfoundry.org/concepts/roles.html#spaces), which can contain applications. Applications in the same space share a location for app development, deployment, and maintenance. (For example, a customer may have spaces for production, staging and development, and may have multiple apps within each of those spaces.)

### Roles

As the [Cloud Foundry documentation](http://docs.cloudfoundry.org/concepts/roles.html#roles) says:

> A user can have one or more roles. The combination of these roles defines the user’s overall permissions in the org and within specific spaces in that org.

cloud.gov currently permits the following roles:

 * **Org Managers** are managers or other users who need to administer the org.
 * **Org Auditors** view but cannot edit user information and org quota usage information.
 * **Space Managers** are managers or other users who administer a space within an org.
 * **Space Developers:** are application developers or other users who manage applications and services in a space.
 * **Space Auditors:** view but cannot edit the space.


## Division of responsibilities

### Security updates

When a new security update is available for one of cloud.gov's underlying technologies, we update the relevant buildpacks. These changes don't take effect on individual apps until the apps are restaged, though. Customers know their apps best, and we prefer to minimize surprises, so the customer's dev team is responsible for restaging their own app(s). For more information, see the [app maintenance documentation](https://cloud.gov/docs/getting-started/app-maintenance/).

### Encryption

Every database service configured through cloud.gov is [encrypted at rest](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html). We use the industry standard AES-256 encryption algorithm to encrypt your data on the server that hosts your database service instance. The database service then handles authenticating access and decrypting your data, with minimal performance impact and without requiring you to modify your applications.

For details, see SC-28 in the cloud.gov SSP in our [P-ATO documentation package](https://cloud.gov/overview/security/fedramp-tracker/#how-you-can-use-this-p-ato).

### Auditing login attempts

Through multi-factor authentication and other means, the cloud.gov team verifies that people logging into cloud.gov legitimately own their accounts. But users don't log in to orgs and spaces, they log into cloud.gov itself. Accordingly, customers don't have direct access to logs of login attempts, but you can ask us to perform specific log searches on your behalf.
