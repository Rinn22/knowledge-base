---
title: After installing, images and stylesheets do not load; only text displays, no graphics
labels: 2.2.x,2.3.x,Apache,Magento Commerce,how to,images,nginx,stylesheets
---

This article describes the possible reasons and solutions for the issue where stylesheets and images do not load after installing Magento.

### Affected products and versions

* Magento Commerce 2.2.x, 2.3.x
* Magento Open Source 2.2.x, 2.3.x

## Issue

 <span class="wysiwyg-underline">Steps to reproduce</span> 

1. Install Magento.
1. Navigate to the storefront or Admin.

 <span class="wysiwyg-underline">Expected result</span> 

Styles are applied, no UI element looks like missing styles.

 <span class="wysiwyg-underline">Actual result</span> 

Styles are not applied correctly, graphics is missing.

## Cause

The path to images and stylesheets is not correct, either because of an incorrect base URL or because server rewrites (CentOS, Ubuntu) are not set up properly.

To confirm this is the case, use a web browser inspector to check the paths to static assets and verify those assets are located on the Magento file system.

Magento static assets are located under `<magento_root>/pub/static/` , within the `frontend` and `adminhtml` directories.

## Solution

The following are possible solutions depending on the software you use and the cause of the problem:

* If you are using the Apache web server, verify your [server rewrites](https://devdocs.magento.com/guides/v2.3/install-gde/prereq/apache.html#apache-help-rewrite) setting and your Magento server's base URL and try again. If you set up the Apache `AllowOverride` directive incorrectly, the static files are not served from the correct location.    
* If you are using the nginx web server, be sure to [configure a virtual host file](https://devdocs.magento.com/guides/v2.3/install-gde/prereq/nginx.html#configure-nginx-ubuntu) . The nginx virtual host file must meet the following criteria:    
    * The `include` directive must point to the sample nginx configuration file in your Magento installation directory. For example:    ```bash    include /var/www/html/magento2/nginx.conf.sample;    ```    
    * The `server_name` directive must match the base URL you specified when installing Magento. For example:    ```bash    server_name 192.186.33.10;    ```    
* If the Magento application is in [production mode](https://devdocs.magento.com/guides/v2.3/config-guide/bootstrap/magento-modes.html#production-mode) , try deploying static view files using the command [magento setup:static-content:deploy](https://devdocs.magento.com/guides/v2.3/install-gde/install/cli/install-cli-subcommands-maint.html) .    

