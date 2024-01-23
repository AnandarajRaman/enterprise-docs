---
layout: post
title:  Reset User Password – Admin Utility for v2.4 | Bold Reports
description: Learn how to use the command line interface to reset the password of any user in Bold Reports Enterprise of v2.4 or earlier using their email address.
platform: report-platform
documentation: ug
---

# Reset Password for Bold Reports version 2.4 or older

You can reset the current password of any user using their email address with this command. Please follow these steps:

* Open the command prompt and change the directory to the admin utility location.

   ```sh
   cd C:\Bold Reports\Utilities\AdminUtils
   ```

   ![command](/static/assets/on-premise/images/tenant-management/admin-utility/displaycmd.png)

* After changing the directory, please run the following command to reset the password.

   ```sh
   AdminUtils.exe reset -u 'user email here' -p 'new password here'
   ```

   ![reset-command](/static/assets/on-premise/images/tenant-management/admin-utility/resetcmd.png)

* Once, the password has been successfully reset, the user can login with the new password.
