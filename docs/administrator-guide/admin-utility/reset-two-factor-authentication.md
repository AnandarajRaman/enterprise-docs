---
layout: post
title:  Reset Two factor authentication for Bold Reports On-Premise
description: Learn how to reset two factor authentication in Bold Reports server application through the command line interface.
platform: Report-platform
documentation: ug
---

# Reset Two Factor Authentication

Please refer to your operating system’s documentation for resetting the Two-Factor Authentication of any user using their email address or username.

* [Windows](#windows)
* [Linux](#linux)

## Windows

1. Open the command prompt and change the directory to the admin utility location.

   ```sh
   cd C:\BoldServices\utilities\adminutils
   ```

   ![Reset-2fa-utility-cmd ](/static/assets/on-premise/images/tenant-management/admin-utility/reset2fa-path-win.png)

2. After changing the directory, please run the following command to reset Two-Factor Authentication.

   ```sh
   Syncfusion.Server.Commands.Utility.exe reset2fa -u 'user email or username here'
   ```

    ![Reset-2fa-cmd ](/static/assets/on-premise/images/tenant-management/admin-utility/reset2fa-win-cmd.png)

3. Once the Two-Factor Authentication has been reset successfully, the user can log in without Two Factor Authentication.

## Linux

1. Change the directory to the admin utility location.

   ```sh
   cd /var/www/bold-services/application/utilities/adminutils/
   ```

   ![Reset-2fa-path-cmd ](/static/assets/on-premise/images/tenant-management/admin-utility/reset2fa-path-linux.png)

2. After changing the directory, please run the following command to reset Two-Factor Authentication.

   ```sh
   ../../../dotnet/dotnet Syncfusion.Server.Commands.Utility.dll reset2fa -u 'user email or username here'
   ```

    ![Reset-2fa-cmd ](/static/assets/on-premise/images/tenant-management/admin-utility/reset2fa-cmd-linux.png)

3. Once the Two-Factor Authentication has been reset successfully, the user can log in without Two Factor Authentication.