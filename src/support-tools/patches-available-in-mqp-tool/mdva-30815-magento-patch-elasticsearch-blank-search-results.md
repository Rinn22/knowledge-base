---
title: MDVA-30815 Magento patch: Elasticsearch blank search results
labels: 2.3.2,2.3.2-p2,2.3.3,2.3.3-p1,MQP 1.0.7,MQP patches,Magento Commerce,Magento Commerce Cloud,category,elasticsearch,products,products per page,support tools
---

The MDVA-30815 patch fixes the issue where Elasticsearch displays a blank page when the search results' limiter options are changed. This patch is available when the [Magento Quality Patch (MQP) tool](https://support.magento.com/hc/en-us/articles/360047139492) v.1.0.7 is installed. Please note that the issue was fixed in Magento version 2.3.5.

## Affected products and versions

* The patch was designed for Magento Commerce Cloud 2.3.3.
* The patch is also compatible with the following Magento versions: Magento Commerce and Magento Commerce Cloud 2.3.2 - 2.3.3-p1.

>![info]
>
>Note: The patch might become applicable to other versions with new MQP tool releases. To check if the patch is compatible with your Magento version, run `./vendor/bin/magento-patches status` .

## Issue

When using Elasticsearch if you change the search results' limiter options, Magento displays a blank page.

 <span class="wysiwyg-underline">Prerequisites</span> 

Elasticsearch is enabled **.** Go to **STORES** > **Settings** > **Configuration** > **Catalog** > **Catalog Search** . <span class="wysiwyg-underline">Steps to reproduce</span> 

1. Go to your site.
1. Search for a product on the main search field.
1. After the search result pages display, click on the last page in the search result pages.
1. Select **Show xx per page** from the limiter option. Make sure that this is a different search results number limit than currently configured.

 <span class="wysiwyg-underline">Expected result:</span> 

The page displays with the configured number of product results.

 <span class="wysiwyg-underline">Actual result:</span> 

Blank page displays. This error can also be seen in the `var/report` : *\`"0":"SQLSTATE\[42000\]: Syntax error or access violation: 1064 You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near'\`* 

## Apply the patch

For instructions on how to apply an MQP patch, use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Software Update Guide > Apply patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Magento Quality Patches, refer to:

* [Magento Quality Patches released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check if patch is available for your Magento issue using Magento Quality Patches](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in MQP tool, refer to the [Patches available in MQP tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.