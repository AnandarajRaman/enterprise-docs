---
layout: post
title:  Reset a User Password – Admin Utility | Bold Reports
description: Learn how to use the command line interface to reset the current password of any user in Bold Reports Enterprise using their email address or user name.
platform: Report-platform
documentation: ug
---

# Reset Password

You can reset the current password of any user using their email address or username with this command. Please follow these steps:

* [Windows](#windows)
* [Linux](#linux)

## Windows

1. Open the command prompt and change the directory to the Admin Utility location.

   ```sh
   cd C:\BoldServices\utilities\adminutils
   ```

   ![command](/static/assets/on-premise/images/tenant-management/admin-utility/cmdforutils-1.png)

2. After changing the directory, please run the below command to reset password.

   ```sh
   Syncfusion.Server.Commands.Utility.exe reset -u 'user email or username here' -p 'new password here'
   ```

   ![reset-command](/static/assets/on-premise/images/tenant-management/admin-utility/resetcmd-1.png)

3. Once the password has been reset successfully, the user can login with the updated password.

## Linux

1. Change the directory to the admin utility location.

   ```sh
   cd /var/www/bold-services/application/utilities/adminutils/
   ```

   ![admin-utility](/static/assets/on-premise/images/tenant-management/admin-utility/admin-utility-linux.png)

2. After changing the directory, please run the following command to reset the password:

   ```sh
   ../../../dotnet/dotnet Syncfusion.Server.Commands.Utility.dll reset -u 'user email or username here' -p 'new password here'
   ```

   ![linux-reset-password](/static/assets/on-premise/images/tenant-management/admin-utility/linux-reset-password.png)

3. Once the password has been reset successfully, the user can log in with the updated password.