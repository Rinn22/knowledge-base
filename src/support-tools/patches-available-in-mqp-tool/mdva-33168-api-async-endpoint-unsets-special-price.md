---
title: MDVA-33168: API async endpoint unsets special price
labels: 2.3.3,2.3.3-p1,2.3.4,2.3.4-p1,2.3.4-p2,2.3.5,2.3.5-p1,2.3.5-p2,2.3.6,2.3.6-p1,2.4.0,2.4.0-p1,2.4.1-p1,2.4.1-p2,2.4.2,MQP 1.0.20,MQP patches,Magento Commerce,Magento Commerce Cloud,Magento Quality Patches,async rest API endpoint,special price
---

The MDVA-33168 Magento patch fixes the issue where using the API async endpoint to update a product attribute unsets a special price.

This patch is available when the [Magento Quality Patch (MQP) tool](https://support.magento.com/hc/en-us/articles/360047139492) 1.0.20 is installed. The patch ID is MDVA-33168. Please note that the issue is planned to be fixed in Magento version 2.4.3.

## Affected products and versions

 **The patch is created for Magento version:** Magento Commerce Cloud 2.3.3-p1

 **Compatible with Magento versions:** Magento Commerce and Magneto Commerce Cloud 2.3.3-2.4.2

>![info]
>
>Note: the patch might become applicable to other versions with new MQP tool releases. To check if the patch is compatible with your Magento version, run `./vendor/bin/magento-patches status` .

## Issue

 <span class="wysiwyg-underline">Steps to reproduce</span> :

1. Create 2 websites with stores.
1. Go to **Stores > Configurations > Catalog > Catalog > Price > Catalog** and Set **Price Scope** = W *ebsite* .
1. Create a *text-type* product attribute. Leave all the options to default.
1. Add the attribute created to the default attribute set.
1. Create a simple product to use with a bundle product.
1. Create a bundle product with the following Example options:
    * **Enable Product** = *Yes* .
    * **Attribute Set** = *Default* .
    * **Product Name** = *bundle-1* .
    * **SKU** = *bundle-1* .
    * **Dynamic SKU** = *Yes* .
    * **Price** = *$100.00* .
    * **Tax Class** = *Taxable Goods* .
    * **Stock Status** = *In Stock* .
Under **Bundle Items** , set these Example options:
    * **Ship Bundle Items** = *Together* .
    * **Option Title** = *test* , **Input Type** = *Radio Buttons* , **Required** checkbox = *checked* .
    * **Is Default** checkbox = *unchecked* .
    * **Name** = *simple-100* .
    * **SKU** = *simple-100* .
    * **Price** = *100.00* .
    * **Price Type** = *Fixed* .
    * **Default Quantity** = *1* .
    * **User Defined** checkbox = *unchecked* .
1. Switch the scope to the non-default store, and set the special price.(Example: on the **Advanced Pricing** page, set **Special Price** = *4%* , and **Price View** = *Price Range* .)
1. Update the new attribute only in the non-default store scope, like this Example:    ```php    PUT {{base_url}}/rest/en_au/async/V1/products/{{sku}}    {        "product": {            "custom_attributes": [                {                    "attribute_code": "text_attr",                    "value": 21                                   }            ]                    }    }    ```    

 <span class="wysiwyg-underline">Expected results</span> :

Other attribute values remain the same when updating a product attribute using async rest API, as expected.

 <span class="wysiwyg-underline">Actual results</span> :

The special price that was set using async rest API under the store scope gets removed.

## Apply the patch

To apply individual patches use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Magento Quality Patches, refer to:

* [Magento Quality Patches released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check patch for Magento issue with Magento Quality Patches](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in MQP tool, refer to the [Patches available in MQP tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.