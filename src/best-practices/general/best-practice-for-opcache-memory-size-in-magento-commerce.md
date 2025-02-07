---
title: Best practice for OPcache memory size in Magento Commerce
labels: .
---

For Pro environments of Magento Commerce Cloud 2.3.x it is recommended to set `opcache.memory_consumption` to at least 2GB, to avoid performance degradation.

## [None](#affected-products-and-versions) Affected products and versions

* Magento Commerce Cloud 2.3.x, Pro environments
* PHP 7.0 and later

## [None](#best-practice) Best practice

Allocate at least 2GB of memory for the [OPcache PHP module](https://www.php.net/manual/en/book.opcache.php) .

The OPcache module is configured in the `php.ini` file. To allocate 2048MB of memory, set `opcache.memory_consumption =  2048` . For more details see [Performance Best Practices - PHP Settings](https://devdocs.magento.com/guides/v2.3/performance-best-practices/software.html#php-settings) and [Configure PHP options](https://devdocs.magento.com/cloud/project/project-conf-files_magento-app.html#customize-phpini-settings) in Magento Developer Documentation.

## [None](#related-reading) Related reading

Best practices for improving Magento Commerce Cloud site performance:

* [Database best practices for Magento Commerce Cloud](https://support.magento.com/hc/en-us/articles/360041997312-Database-best-practices-for-Magento-Commerce-Cloud)
* [Most common database issues in Magento Commerce Cloud](https://support.magento.com/hc/en-us/articles/360041739651-Most-common-database-issues-in-Magento-Commerce-Cloud)
* [Indexers "Update On Schedule" optimizes Magento performance](https://support.magento.com/hc/en-us/articles/360040227191-Indexers-Update-On-Schedule-optimizes-Magento-performance-)

