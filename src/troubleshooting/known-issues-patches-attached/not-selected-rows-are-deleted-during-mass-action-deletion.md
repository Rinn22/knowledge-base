---
title: Not selected rows are deleted during mass action deletion
labels: 2.2.3,Magento Commerce Cloud,deleted customers,deleted products,known issues,mass update,patch,troubleshooting
---

This article provides a patch for the known Magento Сommerce Cloud 2.2.3 issue related to having not selected records being deleted when a bulk deletion is performed in a grid in Magento Admin.

## Issue

In Magento Admin, if you select customer or client records to be deleted, filter the grid, and then select the **Delete** action, all records are deleted.

 <span class="wysiwyg-underline">Steps to reproduce (with Products grid for an example)</span> :

1. Navigate to **Catalog** > **Products** in Magento Admin.
1. Select a product or multiple products.
1. Select Delete from the Actions drop-down menu.

 <span class="wysiwyg-underline">Expected result</span> : Only selected products are deleted.

 <span class="wysiwyg-underline">Actual result</span> : Some other products are deleted as well.

## Patch

The patch is attached to this article. To download it, scroll down to the end of the article and click the file name, or click the following link:

 [Download MDVA-10600\_EE\_2.2.3\_v1.composer.patch](https://support.magento.com/hc/en-us/article_attachments/360025343891/MDVA-10600_EE_2.2.3_v1.composer.patch) 

### Compatible Magento versions:

The patch was created for:

* Magento Commerce Cloud 2.2.3

The patch is also compatible (but might not solve the issue) with the following Magento versions and editions:

* Magento Commerce 2.1.8-2.1.14
* Magento Commerce 2.2.0-2.2.2, 2.2.4-2.2.5
* Magento Commerce Cloud 2.2.4-2.2.5

## How to apply the patch

See [How to apply a composer patch provided by Magento](https://support.magento.com/hc/en-us/articles/360028367731) for instructions.

## Attached Files
