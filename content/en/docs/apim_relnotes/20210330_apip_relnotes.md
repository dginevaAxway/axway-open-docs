---
title: API Portal 7.7 March 2021 Release Notes
linkTitle: API Portal March 2021
weight: 95
date: 2021-01-06
---
## Summary

API Portal provides an API consumer-facing interface that you can customize to match your corporate brand. API Portal is a layered product linked to API Manager, and requires both API Manager and API Gateway. For more information, see the API Gateway and API Manager documentation.

## Installation

API Portal is available as a software installation or a virtualized deployment in a Docker container. For more information, see the following options:

* If you are installing API Portal for the first time using this update, see [Install API Portal](/docs/apim_installation/apiportal_install/)
* If you are already using API Portal (7.5.x, 7.6.x, 7.7.x) and want to install this update, see [Upgrade API Portal](/docs/apim_installation/apiportal_install/upgrade_automatic/)
* If you want to deploy API Portal in Docker containers, see [Deploy API Portal in containers](/docs/apim_installation/apiportal_docker/docker_portal_upgrade/)
* If you are already using API Portal in Docker containers and you want to install this update, see [Upgrade API Portal in Docker containers](/docs/apim_installation/apiportal_docker/docker_portal_upgrade/)

## New features and enhancements

### placeholder 1

placeholder text

For more information, see:

* [some reference 1](/docs/placeholder)
* [some reference 2](/docs/placeholder)

### placeholder 2

placeholder text

For more information, see:

* [some reference 1](/docs/placeholder)
* [some reference 2](/docs/placeholder)

## Limitations of this update

This update has the following limitations:

* API Portal 7.7.20210330 is compatible with API Gateway and API Manager 7.7.20210330 only.
* To upgrade from earlier versions (for example, 7.5.5, 7.6.2) you must first upgrade to API Portal 7.7. For more information see [API Portal single version upgrade](/docs/apim_installation/apiportal_install/upgrade_automatic/#upgrade-from-api-portal-7-6-2) to upgrade versions incrementally.
* You can use the [cumulative upgrade script](/docs/apim_installation/apiportal_install/upgrade_automatic/#upgrade-api-portal-using-the-cumulative-upgrade-script) to upgrade directly from earlier versions (for example, 7.5.5, 7.6.2) to API Portal [7.7 November](/docs/apim_relnotes/20201130_apip_relnotes/), then apply this update package to update your API Portal to the March 21 release.
* This update is not available as a virtual appliance or as a managed service on Axway Cloud.

## Important changes

<!-- It is important, especially when upgrading from an earlier version, to be aware of the following changes in the behavior or operation of the product in this update.. -->

There are no major changes in this update.

## Deprecated features

<!-- As part of our software development life cycle we constantly review our API Management offering. In this update, the following capabilities have been deprecated. -->

No features were deprecated in this release.

## Removed features

<!-- To stay current and align our offerings with customer demand and best practices, Axway might discontinue support for some capabilities. As part of this review, the following features have been removed: -->

No capabilities have been removed in this update.

## Fixed issues

This version of API Portal includes:

* Fixes from all 7.5.5, 7.6.2, and 7.7 service packs released prior to this version. For details of all the service pack fixes included, see the corresponding *SP Readme* attached to each service pack on [Axway Support](https://support.axway.com).
* Fixes from all 7.7 updates released prior to this version. For details of all the update fixes included, see the corresponding [release note](/docs/apim_relnotes/) for each 7.7 update.

### Fixed security vulnerabilities

| Internal ID | Case ID | CVE Identifier | Description                                                                                                                      |
| ----------- | ------- | -------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| IAP-4003    |         |                | **Issue**: Swagger IO is using vulnerable version of marked library. **Resolution**: Marked library is upgraded to safe version. |
| IAP-3842    |         |                | **Issue**: API Portal is using vulnerable version of Axios library. **Resolution**: Axios library is upgraded to safe version.   |

### Other fixed issues

| Internal ID | Case ID | Description                                                                                                                                                                                                                                                                                   |
| ----------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IAP-2927    |         | Issue: Resolution:                                                                                                                                                                                                                                                                            |
| IAP-3858    |         | **Issue**: User doesn't get redirected to the "redirect after login" after accepting privacy policy. **Resolution**: User gets redirected to the "redirect after login" after accepting privacy policy.                                                                                       |
| IAP-3940    | 1228612 | **Issue**: API description is not shown on API Catalog. **Resolution**: API summary is shown as description by default.                                                                                                                                                                       |
| IAP-3949    | 1229842 | **Issue**: When hide tags from API Catalog page they are not hidden in create / edit application pages. **Resolution**: New configuration is added for applications which allows to hide tags from applications pages.                                                                        |
| IAP-4000    |         | **Issue**: While creating application from an API Details page we see a list of all available organisations, to some of which the API is not connected. **Resolution**: Now when an application is being created from an API we see a list of the organizations to which the API is assigned. |
| IAP-4002    | 1231371 | **Issue**: The documentation was not clear on what resources are recommended for use for Docker artifacts released before November. **Resolution**: All documentation sections has been updated to point latest docker artifacts recommended for production.                                  |
| IAP-4033    |         | **Issue**: Redirect after login option in JAI is not working when multiple languages are installed. **Resolution**: Redirect after login option in JAI works for multiple-languages API Portal instances.                                                                                     |
| IAP-4055    | 1232846 | **Issue**: PHP CLI version is checked from the context of the user who is running the installation while it's used in the context of the Apache user. **Resolution**: Run updatescript.php by the user who is doing the installation.                                                         |

## Known issues

The following are known issues for this update.

### When Multi Manager feature is configured, API Portal users are no longer able to login

After a recent bug fix in API Manager (RDAPI-20021), the `Authenticate to Master` policy is no longer working after upgrading from releases earlier than [API Portal July 2020](/docs/apim_relnotes/20200730_apip_relnotes/). To fix this, perform the following steps:

1. Open all slave managers configurations in Policy Studio, and click to **Edit** the `AuthenticateToMaster` policy.
2. Click the **Login to Master** (Connect to URL) filter, and enter `Accept: */*` for the **Request Protocol Header**.
3. Click the **Enter** key twice to create two blank lines after `Accept: */*`.

Alternatively you can take the updated `AuthenticateToMaster` policy and apply again your configurations.

Related Issue:IAP-3435

### Page layout and alignment for Arabic language

Changing the API Portal language to Arabic (or any other right to left language) results in issues with page layout and alignment on the API Portal Home and Pricing pages, and some buttons are not visible. As a workaround, you can turn on the development mode in JAI. Follow these steps:

1. Log in to Joomla! Admin Interface (JAI).
2. In the JAI top navigation bar, click **Extensions > Templates**.
3. Click your template style (for example, `purity_III * Default`) to open it.
4. Click the **General** tab.
5. Change **Development Mode** to `ON`.
6. Click **Save** and click **Close** to close the template style.

Related Issue: IAP-308

## Documentation

This section describes documentation enhancements and related documentation.

### Documentation enhancements

There are no major changes in this update.

### Related documentation

To find all available documentation for this product version:

1. Go to [Manuals on the Axway Documentation portal](https://docs.axway.com/bundle).
2. In the left pane Filters list, select your product or product version.

Customers with active support contracts need to log in to access restricted content.

The following reference documents are also available:

* [Supported Platforms](https://docs.axway.com/bundle/Axway_Products_SupportedPlatforms_allOS_en) - Lists the different operating systems, databases, browsers, and thick client platforms supported by each Axway product.
* [Interoperability Matrix](https://docs.axway.com/bundle/Axway_Products_InteroperabilityMatrix_allOS_en) - Provides product version and interoperability information for Axway products.

## Support services

The Axway Global Support team provides worldwide 24 x 7 support for customers with active support agreements.

Email [support@axway.com](mailto:support@axway.com) or visit [Axway Support](https://support.axway.com/).

See [Get help with API Gateway](/docs/apim_administration/apigtw_admin/trblshoot_get_help/) for the information that you should be prepared to provide when you contact Axway Support.