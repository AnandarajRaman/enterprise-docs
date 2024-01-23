---
title:  Upgrade Linux Server in the Report Server | Syncfusion
description: Explains about how to upgrade linux server using the commands and then add it in the Bold Reports On-Premise.
keywords : create report, reportserver, web designer
---

# Upgrading Bold Reports Linux package to the Latest Version

This section explains how to upgrade Bold Reports Linux package from any version to the latest version.

1. Register and download the latest Bold Reports Linux package from [here](../../../getting-started/).

2. Download the latest Bold Reports  Linux package by running the following command.

   ```console
   sudo wget {Bold Reports Linux package link}
   ```

3. Extract the zip file.

   ```console
   sudo unzip {Bold Reports Linux package zip file}
   ```

4. Change the directory to `BoldReports_EnterpriseReporting-Linux` by running the following command.

   ```console
   cd BoldReports_EnterpriseReporting-Linux
   ```

5. Execute the following command to deploy Bold Reports in your Linux machine.

   ```console
   sudo bash install-boldreports.sh -i {upgrade} -u {user} -h {host URL}
   ```

     * **i** : Installation type - Specifies either it is a new or upgrade installation.

     * **u** : Specify the user or group that manages the service.

     * **h** : Domain or IP address of the machine with http protocol.

Example for upgrading the installation,

  ```console
  sudo bash install-boldreports.sh -i upgrade -u www-data -h http://linux.example.com
  ```

* Refer to this [link](../install-opt-library/) and install the optional client libraries, after the installation completed.

* Now, you can open the host URL in the browser and use the latest features of Bold Reports.

> NOTE: Bold Reports Linux package backup file will be available in the following location. /var/www/

## Upgrade breaking changes

> Below breaking changes is applicable only for upgrading the Bold Reports application from version v3.x to v5.1.20.

**Automatic Nginx configuration**:

* If you preferred automatic Nginx configuration during initial installation, below prompt message will be displayed and proceed with the installation by choosing **Yes**. ![Upgrade Automatic Nginx Configuration Message](/static/assets/on-premise/images/installation/upgrade-automatic-config-message.png)

* If you are choosing **No**, then please follow the below manual Nginx configuration step.

**Manual Nginx configuration**:

* If you have manually configured Nginx during initial installation, below message will be displayed. ![Upgrade Manual Nginx Configuration Message](/static/assets/on-premise/images/installation/upgrade-manual-config-message.png)

* For manual Nginx configuration, modify the default Nginx configuration file in location`/etc/nginx/sites-available`. Open it in a text editor and add the following code, like the below image.

```cmd
    location /reporting/viewer {
        proxy_pass         http://localhost:6554/reporting/viewer;
        proxy_http_version 1.1;
        proxy_set_header   Upgrade $http_upgrade;
        proxy_set_header   Connection keep-alive;
        proxy_set_header   Host $host;
        proxy_cache_bypass $http_upgrade;
        proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header   X-Forwarded-Proto $scheme;
    }
```

**Nginx configuration file code**:

![Breaking Issue](/static/assets/on-premise/images/installation/upgrade-breaking-changes.png)

Once the Nginx configuration is updated, run the `sudo nginx -t` to verify the syntax of the configuration files. If the configuration file test is successful, force the Nginx to pick up the changes by running the `sudo nginx -s reload`.