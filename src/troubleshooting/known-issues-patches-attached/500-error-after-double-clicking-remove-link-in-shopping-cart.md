---
title: "500 error" after double-clicking Remove link in shopping cart
labels: 2.2.0,500 error,Magento Commerce Cloud,known issues,patch,shopping cart,troubleshooting
---

This article provides a patch for the known Magento Commerce Cloud 2.2.0 issue related to customers getting error when trying to remove twice a shopping cart item (by double-clicking the *Remove* link or by clicking it in different tabs).

## Issue

When customers double-click the *Remove* link in the shopping cart, trying to remove a product from the shopping cart, they get a blank page with the following error message: *"This page isn’t working. HTTP ERROR 500".* The same issue happens if a customer opens two browser tabs with the shopping cart page and removes the product first in one tab, then in the second one.

 <span class="wysiwyg-underline">Steps to reproduce</span> :

1. Add a product to shopping cart on the storefront.
1. Navigate to the shopping cart page.
1. Double-click the Remove link.

OR

1. Add a product to shopping cart on the storefront.
1. Navigate to the shopping cart page.
1. Open a new browser tab and navigate to the shopping cart page (same product).
1. Remove the product from the cart.
1. Open the second tab and remove the product again.

 <span class="wysiwyg-underline">Expected result</span> : The product is removed from the cart without errors.

 <span class="wysiwyg-underline">Actual result</span> : The product is removed with the error: *"This page isn’t working. HTTP ERROR 500"* error message.

## Patch

The patch is attached to this article. To download it, scroll down to the end of the article and click the file name, or click the following link:

 [Download MDVA-8623\_EE\_2.2.0\_v1.composer.patch](https://support.magento.com/hc/en-us/article_attachments/360023828792/MDVA-8623_EE_2.2.0_v1.composer.patch) 

### Compatible Magento versions:

The patch was created for:

* Magento Commerce (Cloud) 2.2.0

The patch is also compatible (but might not solve the issue) with the following Magento versions and editions:

* Magento Commerce (Cloud) versions from 2.2.1 to 2.2.5
* Magento Commerce versions from 2.2.0 to 2.2.5

## How to apply the patch

See [How to apply a composer patch provided by Magento](https://support.magento.com/hc/en-us/articles/360028367731) for instructions.

## Attached Files
