---
layout: post
title: Installing Client Libraries in Linux | Bold Reports
description: Learn  Set up To Install Optional Library in Linux Ubuntu for the Bold Reports Enterprise Edition. Learn  Set up To Install Optional Library in Linux Ubuntu for the Bold Reports Enterprise Edition.
platform: report-platform
documentation: ug
---

# Install Optional Libraries

## Client libraries

> **Important:** Bold Reports Enterprise Edition uses client libraries such as Oracle, PostgreSQL, and MySQL to connect with their respective SQL database variants. You need to read and accept client library license to install client libraries.

1. Go to client library location. `/var/www/bold-services/clientlibrary/boldreports`

2. Here, you can see the client library consent document `consent-to-deploy-client-libraries.txt`. Read client libraries `LICENSE` details and execute the following command to install client libraries.

    ```sh
    $sudo bash install-optional.libs.sh install-optional-libs {user} postgresql,mysql,oracle
    ```

## PhantomJS

> **Important:** PhantomJS is a headless WebKit scriptable with JavaScript. This is free software or open source, and it may contain MIT, BSD, LGPL, GPL, or other similar licenses that contain third-party code. This executable file is necessary to export the data visualization report items during report schedule.

1. Before installing PhantomJS, you will need to install some required packages on your linux system . You can install all of them with the following command:

    ```sh
    sudo apt-get install build-essential chrpath libssl-dev libxft-dev libfreetype6-dev libfreetype6 libfontconfig1-dev libfontconfig1 -y
    ```

2. You will need to download the PhantomJS. You can download the latest stable version of the PhantomJS from their official website. Run the following command to download PhantomJS.

    ```sh
    sudo wget https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.1.1-linux-x86_64.tar.bz2
    ```

3. Once the download is complete, extract the downloaded archive file to desired system location:

    ```sh
    sudo tar xvjf phantomjs-2.1.1-linux-x86_64.tar.bz2 -C /usr/local/share/
    ```

4. Next, create a symlink of PhantomJS binary file to systems bin directory:

    ```sh
   sudo ln -s /usr/local/share/phantomjs-2.1.1-linux-x86_64/bin/phantomjs /usr/local/bin/
    ```

5. Verify PhantomJS installed on your system with the following command:

    ```sh
   phantomjs --version
    ```

6. You can see the following PhantomJS version

    ```sh
   2.1.1
    ```

> **Note:** PhantomJS needs some dependencies. If your distribution does not contain the dependencies, please install it. [https://phantomjs.org/download.html](https://phantomjs.org/download.html).

## Next step

* [Application Startup](./../../../application-startup/)