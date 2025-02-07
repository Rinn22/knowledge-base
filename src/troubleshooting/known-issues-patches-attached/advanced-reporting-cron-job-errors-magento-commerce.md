---
title: Advanced Reporting cron job errors Magento Commerce
labels: 2.3.1,2.3.4-p2,2.3.x,404,Magento Commerce,Magento Commerce Cloud,advanced reporting,known issue,patch,troubleshooting
---

This article provides patches for the Advanced Reporting cron jobs issues in Magento Commerce, which can cause a 404 error for customers trying to access Advanced Reporting.

## Affected products and versions

Magento Commerce 2.3.x

## Issue

A customer gets a 404 error when they attempt to access Advanced Reporting and there are errors in the logs associated to `analytics_collect_data job` .

## Compatible Magento versions:

The patches are compatible (but might not solve the issue) with the following Magento versions and editions:

 [MDVA-19391\_EE\_2.3.1\_COMPOSER\_v1.patch](https://support.magento.com/hc/en-us/article_attachments/360059514731/MDVA-19391_EE_2.3.1_COMPOSER_v1.patch) :Magento Commerce and Magento Commerce Cloud:

* 2.3.4-p2
* 2.3.4
* 2.3.3-p1
* 2.3.3
* 2.3.2-p2
* 2.3.2
* 2.3.1

 [MDVA-18980\_EE\_2.2.6\_COMPOSER\_v1.patch](https://support.magento.com/hc/en-us/article_attachments/360059516831/MDVA-18980_EE_2.2.6_COMPOSER_v1.patch) :Magento Commerce and Magento Commerce Cloud:

* 2.3.0
* 2.2.7
* 2.2.6
* 2.2.5
* 2.2.4
* 2.2.3
* 2.2.2

 [MDVA-15136\_EE\_2.2.6\_COMPOSER\_v1.patch](https://support.magento.com/hc/en-us/article_attachments/360059527331/MDVA-15136_EE_2.2.6_COMPOSER_v1.patch) :Magento Commerce and Magento Commerce Cloud:

* 2.3.0
* 2.2.7
* 2.2.6

## **Solution** 

To fix the issue, please apply the relevant patch attached to this article. To download it, scroll down to the end of the article and click the file name, or click the following links:

* Download [MDVA-19391\_EE\_2.3.1\_COMPOSER\_v1.patch](https://support.magento.com/hc/en-us/article_attachments/360059514731/MDVA-19391_EE_2.3.1_COMPOSER_v1.patch) 
* Download [MDVA-15136\_EE\_2.2.6\_COMPOSER\_v1.patch](https://support.magento.com/hc/en-us/article_attachments/360059527331/MDVA-15136_EE_2.2.6_COMPOSER_v1.patch) 
* Download [MDVA-18980\_EE\_2.3.1\_COMPOSER\_v1.patch](https://support.magento.com/hc/en-us/article_attachments/360059516831/MDVA-18980_EE_2.2.6_COMPOSER_v1.patch) 

To check which patch to use:

<ol><li>Review the logs by using the following command:<code>grep analytics_collect_data var/log/support_report.log var/log/support_report.log.1.gz</code>
</li><li>Depending on the error you see, select a patch using the information from the following table.<table style="width: 826px;">
<tbody>
<tr>
<td class="wysiwyg-text-align-center">
<p>Error</p>
</td>
<td class="wysiwyg-text-align-center">Patch</td>
</tr>
<tr>
<td>
<pre>report.CRITICAL: Error when running a cron job {"exception":"[object] (RuntimeException(code:
  0): Error when running a cron job at /srv/public_html/vendor/magento/module-cron/Observer/ProcessCronQueueObserver.php:327,
  TypeError(code: 0): substr_count() expects parameter 1 to be string, null given
  at /srv/public_html/vendor/magento/module-page-builder-analytics/Model/ContentTypeUsageReportProvider.php:106)"}
  []</pre>OR<pre>report.ERROR: Cron Job analytics_collect_data has an error: substr_count() expects
  parameter 1 to be string, null given. Statistics: {"sum":0,"count":1,"realmem":0,"emalloc":0,"realmem_start":224919552,"emalloc_start":216398384}
  [] []</pre>
<p> </p>
</td>
<td>Apply<a href="https://support.magento.com/hc/en-us/article_attachments/360059514731/MDVA-19391_EE_2.3.1_COMPOSER_v1.patch">MDVA-19391_EE_2.3.1_COMPOSER_v1.patch</a>, clear cache and wait 24 hours for the job to run again and try again.</td>
</tr>
<tr>
<td> 
<p><em>Failed to open file /tmp/analytics/tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../tmp/../</em></p>
</td>
<td>Apply<a href="https://support.magento.com/hc/en-us/article_attachments/360059527331/MDVA-15136_EE_2.2.6_COMPOSER_v1.patch">MDVA-15136_EE_2.2.6_COMPOSER_v1.patch</a>, clear cache and wait 24 hours for the job to run again and try again.</td>
</tr>
<tr>
<td><em>Not valid cipher</em></td>
<td>Apply<a href="https://support.magento.com/hc/en-us/article_attachments/360059516831/MDVA-18980_EE_2.2.6_COMPOSER_v1.patch">MDVA-18980_EE_2.2.6_COMPOSER_v1.patch</a>, clear cache and wait 24 hours for the job to run again and try again.</td>
</tr>
</tbody>
</table>
</li></ol>
## How to apply the patch

See [How to apply a composer patch](https://support.magento.com/hc/en-us/articles/360028367731) provided by Magento for instructions.

## Attached files
