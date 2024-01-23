---
layout: post
title: Office 365 authentication in Bold Reports | Bold Reports
description: Office 365 authentication settings to let your users use their Office 365 credentials to login into the Bold Reports On-Premise Edition.
platform: Report-platform
documentation: ug
---

# Office 365 for authentication

The Bold Reports On-Premise supports importing Azure Active Directory users and allows them to do Single Sign-On (federated identity) into the Bold Reports On-Premise using their credentials. You can share or email the reports with Office 365 users and groups. The Office 365 uses the cloud-based user authentication service Azure Active Directory to manage users. So, the Report Server supports the Office 365 users and groups to be imported and sign in to it.

The Report Server supports the following functionalities from the Azure Active Directory:

* [Setup Azure Active Directory](./../../../manage-app-settings/azure-active-directory/) settings with the  Bold Reports On-Premise.

* [Import users](./../../../manage-users/users/import-users/import-azure-active-directory-users/) from the Azure Active Directory.

* [Import groups](./../../../manage-users/groups/import-groups/import-azure-active-directory-groups/) from the Active Directory.

* [Synchronize user details](./../../../manage-users/users/synchronize/synchronize-azure-active-directory-users/) with the Azure Active Directory.

* [Synchronize group details and its users](./../../../manage-users/groups/synchronize/synchronize-azure-active-directory-groups/) with the Azure Active Directory.

* [Schedule the synchronization of user and groups](./../../../manage-app-settings/synchronization-schedule/azure-active-directory-synchronization-schedule/) between the Bold Reports On-Premise and the Azure Active Directory.