---
title: Additional Images - disabling 
description: Zen Cart Additional Images - disabling 
category: images
weight: 10
---

# Turning off Additional Images
 
## Problem:

On my product pages, I'm seeing images from other products showing under my product description.  Why? How do I change this?

## Cause:

The "additional images" feature is causing this.

## Solution:

You have two options:

a) rename your images so they don't share a common filename.  Right now since you have one product with "abc.jpg" as the name, and another product with "abcde.jpg" as the name, both images will show for the "abc.jpg" product, because "abc" is common to both, and "abc" is the full filename of the main image of one of the products.  

This is explained further in the [Additional Images Tutorial](/user/images/adding_multiple_images_to_a_product).

b) or turn off all extra-image functionality by going to [Admin > Catalog > Product Types](/user/admin_pages/catalog/product_types/), 
then selecting Product General (or whatever your product type is),
then clicking *Edit Layout* and setting `Show Additional Images` to 0. 


