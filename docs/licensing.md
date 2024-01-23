---
layout: post
title: Bold Reports Enterprise Edition License Overview
description: This documentation explains about how the license is validated in Bold Reports Enterprise Application.
platform: report-platform
documentation: ug
---

# Enterprise License Overview

An enterprise license, including those for Bold Reports, is a type of software licensing agreement that grants a large organization the right to use the Bold Reports software product across the entire business. It allows them to use the Bold Reports software or service across the entire organization without needing to obtain individual licenses for each user or device.

**Key characteristics of an enterprise license often include:**

1. Bold Reports can be installed and used on any number of devices within the organization, without restrictions on the number of users or installations.

2. The organization can manage all licenses centrally, making it easier to track usage, renewals, and compliance.

3. Enterprise licenses often come with access to additional services, such as premium support.

4. Compared to purchasing individual licenses for each user or device, enterprise licensing offers cost efficiency. This could involve a flat fee, a pricing structure based on the organization's size, or a usage-based model.

## Types of License validation in Bold Reports:

1. [Online License Validation](#online-license-validation)

2. [Offline License Validation](#offline-license-validation)

## Online License Validation

* Online license validation is a process used by Bold Reports to verify the authenticity and legality of a Bold Reports license by connecting to the internet. It ensures that the provided Bold Reports license key or credentials are legitimate before allowing Bold Reports to operate or granting access to certain features.

* To activate your account and start the Bold Reports Enterprise Application using online license validation, use your login credentials. For more detailed instructions, please follow the [documentation](./../administrator-guide/application-startup/#activate-the-account-using-login-credentials).

### How It Works

1. When a user installs or activates Bold Reports, they are required to enter a license key or credentials for authorization.

2. Bold Reports initiates a request to its designated server over the internet, transmitting details about the license key or credentials.

3. The server checks the provided license key or credentials to verify if they are genuine, unused, and align with the authorized usage rights.

4. If the license key meets the criteria and is valid, Bold Reports is authorized to run or access various features according to the terms of the license agreement.

### Uses of an Online License Validation

1. **Anti-Piracy Measure:** Online validation helps prevent Bold Reports piracy by ensuring that only genuine and authorized license keys are accepted, reducing unauthorized usage or distribution.

2. **Ensuring Compliance:** It ensures users adhere to Bold Reports license terms and conditions, allowing Bold Reports providers to monitor and regulate authorized software use.

3. **Security Enhancement:** By validating licenses online, it adds a layer of security, allowing only legitimate users with authorized licenses to access Bold Reports, reducing the risk of unauthorized access or security breaches.

4. **Subscription Model:** It supports a subscription-based model by periodically verifying licenses to ensure that users maintain active subscriptions or licenses for continued access.

## Offline license validation

* Offline license validation, including for Bold Reports, involves authenticating the legitimacy of a Bold Reports software license without requiring an active internet connection. It verifies the validity and authenticity of a provided Bold Reports license key or credentials locally on the device without connecting to a central server or online system.

* While the default setting for the Bold Reports License mandates online license validation, if you face network limitations or any barriers hindering online license validation, you can obtain an offline license key for your subscription.

* To activate your account and start the Bold Reports Enterprise Application using offline license validation, please follow the [documentation](./../administrator-guide/application-startup/#offline-installation).

### How It Works

1. The process authenticates the license key or credentials directly on the user's device, checking their validity without requiring an internet connection.

2. Bold Reports compares the provided license key or credentials against locally stored data or cryptographic methods to ensure they are genuine and in line with the Bold Reports licensing terms.

3. If the license key or credentials for Bold Reports are valid and meet the validation criteria, Bold Reports gets authorized to run or access specific features as per the terms of the license agreement.

### Uses of an Offline License Validation

1. **Limited Internet Access:** It's beneficial in environments with limited or no internet connectivity, ensuring Bold Reports activation and usage without requiring an online connection.

2. **Secure Environments:** For highly secure environments, closed networks, or systems isolated from the internet for security reasons, offline validation ensures Bold Reports activation without compromising security.

3. **Remote Locations:** In areas with poor connectivity, offline validation allows Bold Reports usage without depending on internet availability.

4. **Confidentiality and Privacy:** It offers a layer of privacy by verifying licenses locally, without transmitting sensitive license information over the internet.

5. **Reduced Dependency:** It decreases reliance on continuous internet access for license validation, making it convenient for users operating in offline or restricted network environments.

### How to get the offline license key file

* The offline license key file( `.lic` ) can be generated from the [Downloads](https://www.boldreports.com/account/downloads) section of the Bold Reports site. Once offline license support has been activated, initiating an activation request for offline license access can be done through our [support system](https://support.boldreports.com/) or contact our sales team at (sales@syncfusion.com).For more info refer to [KB](https://support.boldreports.com/kb/article/13271/how-do-i-get-my-offline-license-key-from-our-bold-reports-account-page).

   ![Offline License](/static/assets/on-premise/images/getting-started/offline-license.png)

### Where to place the offline license key file

Place the downloaded license key file in the Bold Reports installation location. Follow the given steps:

1. The offline license file should have the name `boldreports_components_licensekey.lic`.

2. Go to the deployed location and place the license key file in the below location.

   **`{Deployed Location}`**\app_data\reporting\configuration

   Example: C:\BoldServices\app_data\reporting\configuration

   >By default, Bold Reports will be deployed on C:\BoldServices.

3. Open the config.xml file at the below location:
   `{deployment_location}\app_data\reporting\configuration\config.xml`

4. Set true to the OfflineCapable node, if the node is not available, then add the node as shown below and then save the file.
   `<OfflineCapable>true</OfflineCapable>`
   Refer to [kb](https://support.boldreports.com/kb/article/14885/enable-offline-mode-for-bold-reports-resolve-errors-when-an-internet-connections-are-not-available) for more info.
   ![Offline Capable](/static/assets/on-premise/images/getting-started/offline-capable-node.png)

5. [Restart](./../administrator-guide/faq/how-to-restart-the-bold-reports-enterprise-application/) the Bold Reports application.

   ```steps
   The license key will expire based on the validity of the subscription.

   After the expiration date, you have to renew and change the license key.
   ```

> **Note:** You can change your Bold Reports license by referring to the [documentation](./../administrator-guide/application-startup/#activate-bold-reports-license).