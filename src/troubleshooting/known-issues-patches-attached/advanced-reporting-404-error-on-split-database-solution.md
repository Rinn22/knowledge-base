---
title: Advanced Reporting 404 error on split database solution
labels: .
---

This article provides a patch for Magento Commerce 2.3.x users with the [split database solution](https://devdocs.magento.com/guides/v2.3/config-guide/multi-master/multi-master.html) that experience a 404 error when trying to use Advanced Reporting.

## [None](#affected-products-and-versions) Affected products and versions

Magento Commerce, all v2.3.x (v2.3.0 through v2.3.5-p1)

## [None](#issue) Issue

The patch fixes the issue where the wrong connection name is used to collect quotes data. Due to the wrong connection name being used, the quote data is not sent to Magento Business Intelligence (MBI) and the reports cannot be generated.

## [None](#solution) Solution

Apply the [patch](assets/MDVA-26831_EE_2.3.4_v1.composer.patch) provided in this article.

## [None](#patch) Patch

The patch is attached to this article. To download it, scroll down to the end of the article and click the file name, or click the following link:

 [MDVA-26831\_EE\_2.3.4\_v1.composer.patch](assets/MDVA-26831_EE_2.3.4_v1.composer.patch) 

## [None](#how-to-apply-the-patch) How to apply the patch

See [How to apply a composer patch provided by Magento](https://support.magento.com/hc/en-us/articles/360028367731) for instructions.

## [None](#attached-files) Attached Files
