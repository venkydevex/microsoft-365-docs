---
title: Configure alert notifications in Microsoft Defender for Endpoint
description: You can use Microsoft Defender for Endpoint to configure email notification settings for security alerts, based on severity and other criteria.
keywords: email notifications, configure alert notifications, Microsoft Defender for Endpoint, Microsoft Defender for Endpoint notifications, Microsoft Defender for Endpoint alerts, windows enterprise, windows education
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
---

# Configure alert notifications in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Applies to:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md)

> Want to experience Defender for Endpoint? [Sign up for a free trial.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-emailconfig-abovefoldlink)

You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts. This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.

If you're using [Defender for Business](../defender-business/mdb-overview.md), you can set up email notifications for specific users (not roles or groups).

> [!NOTE]
> Only users with 'Manage security settings' permissions can configure email notifications. If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.

You can set the alert severity levels that trigger notifications. You can also add or remove recipients of the email notification. New recipients get notified about alerts triggered after they're added. For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).

If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule. Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope. Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.

The email notification includes basic information about the alert and a link to the portal where you can do further investigation.

## Create rules for alert notifications
You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.

1. In the navigation pane, select **Settings** \> **Endpoints** \> **General** \> **Email notifications**.

2. Click **Add item**.

3. Specify the General information:
    - **Rule name** - Specify a name for the notification rule.
    - **Include organization name** - Specify the customer name that appears on the email notification.
    - **Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.
    - **Include device information** - Includes the device name in the email alert body.

        > [!NOTE]
        > This information might be processed by recipient mail servers that are not in the geographic location you have selected for your Defender for Endpoint data.

    - **Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups. For more information, see [Create and manage device groups](machine-groups.md). (If you're using [Defender for Business](../defender-business/mdb-overview.md), device groups do not apply.)
    - **Alert severity** - Choose the alert severity level.

4. Click **Next**.

5. Enter the recipient's email address then click **Add recipient**. You can add multiple email addresses.

6. Check that email recipients can receive the email notifications by selecting **Send test email**.

7. Click **Save notification rule**.

## Edit a notification rule

1. Select the notification rule you'd like to edit.

2. Update the General and Recipient tab information.

3. Click **Save notification rule**.

## Delete notification rule

1. Select the notification rule you'd like to delete.

2. Click **Delete**.

## Troubleshoot email notifications for alerts

This section lists various issues that you may encounter when using email notifications for alerts.

**Problem:** Intended recipients report they're not getting the notifications.

**Solution:** Make sure that the notifications aren't blocked by email filters:

1. Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder. Mark them as Not junk.
2. Check that your email security product isn't blocking the email notifications from Defender for Endpoint.
3. Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.

## Related topics

- [Update data retention settings](data-retention-settings.md)
- [Configure advanced features](advanced-features.md)
- [Configure vulnerability email notifications in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
