---
layout: post
title: System and Mail Notifications | Report Server | Syncfusion
description: Configure system and mail notifications to notify the users when any comment added on reports in the Bold Reports On-Premise.
platform: report-platform
documentation: ug
---

# Notifications

You can configure the notifications settings to notify the users when any comment is added to the reports in the Bold Reports On-Premise. Notifications can be configured by both the System Administrator and user.

To change the notification **Settings**, click the Setting option in the Report Server left-side panel and navigate to the **Notification** tab as shown in the following image.
![Notification settings page](/static/assets/on-premise/images/notifications/notifications-settings.png)

## Admin notification settings

Configure how the users receive notifications for the report comments from the admin notification settings page.
![Admin notification settings](/static/assets/on-premise/images/notifications/admin-notifications-settings.png)

### System notifications

To view the system notifications, click on the `Notification` icon in the Report Server left-side panel as shown in the following image.
![System notifications](/static/assets/on-premise/images/notifications/system-notifications.png)

### Mail notifications

Enabling the mail notifications option will notify the users through email for comments, permissions, schedules, views, user(s) and group(s) (manual and schedule) synchronization and user account activation.

### Auto watch comments of created items

Enabling this will send notifications for comments on all the items created by users.

### Auto watch comments of accessible items

Enabling this will send notifications for comments on all the items that are accessed by users.

### Report schedule notification

Enabling and disabling report schedule button we can restrict the mail receiving for scheduled report

### User schedule notification

Enabling and disabling user schedule button we can restrict the mail receiving for admin users

The following are the default and allowable notification settings configuration.

### Default settings

This is the default settings applied to users when users are added to the Report Server. Users can change switch from this setting and make their own or inherit this setting at anytime in their profile edit page.

### Allow/restrict settings

This is the master settings for the Report Server. Enabling or disabling any setting, will enable or disable it in the Report Server. This will override the default and user settings.

## User notification settings

Configure how the current user receive notifications for comments from the user notification settings page. Users can navigate to this page from the profile edit page as shown in the following image.

![User notification settings](/static/assets/on-premise/images/notifications/user-notifications-settings-navigation.png)

Refer to the following image for changing the notification settings for the current user.

![User notification settings options](/static/assets/on-premise/images/notifications/user-notifications-settings.png)

Settings can be enabled, disabled, or inherited from the global settings that is the default settings of the Report Server.

### Specific watch

Apart from auto watch of created and accessible item settings, users can also watch an item specifically.

![Report Specific watch](/static/assets/on-premise/images/notifications/report-specific-notifications.png)

Users can toggle between watch and unwatch for a report comment at anytime.