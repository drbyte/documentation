---
title: Downloadable products - how to create? 
category: products
weight: 1
---

**<font color="#003300">NOTE: CHECK OUT THE IMPORTANT FACTS ABOUT DOWNLOAD SETTINGS, near the bottom of this article ...</font>**  

Downloads are handled as product attributes.  
So, **FIRST you should familiarize yourself with:** [setting up attributes](/user/products/attributes). 

NOTE: Download files must be loaded (usually by FTP) to your store's  /download directory before trying to link those files to products/attributes .  

## To add a Download Attribute to a product

1.  Go to **Option Names** ... and create an Option Name that is either Radiobutton or Dropdown ...  
    Call it something like:  **_Download_**
2.  Go to **Option Values Manager** and add what you want to call it ...  
    example: **_Zip File_**  
    If you have multiple choices you could have these as the Option Names you create:  
    - MS Word Zip  
    - Note Pad Zip  
    - etc.
3.  Go to **<span class="highlight">Attributes</span> Controller** and find the Product ...  
    Add the Attribute as:

1.  Option Name: Download  
    Option Value: MS Word Zip  
    Sort Order: 10  
    Filename: (enter name of file you uploaded to the  /download folder)  

2.  Option Name: Download  
    Option Value: Note Pad Zip  
    Sort Order: 20  
    Filename: (enter name of file you uploaded to the  /download folder)  

Now when shopping, the customer can choose the format.  Depending on your downloads you will want to adjust how you configure things.  

If using Radio buttons and have multiple selections, be sure to set one as a default.  

## To make multiple downloads on the same product

For each download item, you need an **Option Name**  
For each Option Name, you need one or many **Option Values** depending on the choices needed ...  

<font size="4">**Let's use an example:**</font>  
If you have 5 downloads on one Product you need 5 Option Names and 1 Option Value per name:  

<font size="4">**Option Names:**</font>  
Download 1 Option Type: Radiobutton,  Sort Order 10  
Download 2 Option Type: Radiobutton,  Sort Order 20  
Download 3 Option Type: Radiobutton,  Sort Order 30  
Download 4 Option Type: Radiobutton,  Sort Order 40  
Download 5 Option Type: Radiobutton,  Sort Order 50  

<font size="4">**Option Values**</font>  
Now ... for each Option Name you make an Option Value ...  

The most common reason for having multiple downloads on a product is that the download is big so it is broken into parts for easier access and safer downloading.  
In such a case, you just need 1 Option Value per Option Name ... this means you just have 5 downloads to go to the Product  

If you have many multiple downloads, say each Product has 5 downloads you can pattern this so the names make sense when read on the screen  

**Example for 5 Downloads it would read:**  
Download 1 of 5  
Download 2 of 5  
Download 3 of 5  
Download 4 of 5  
Download 5 of 5  

**For 3 Downloads it would read:**  
Download 1 of 3  
Download 2 of 3  
Download 3 of 3  

**Make the Option Values as needed:**  
Option Values:  
Option Name pick from dropdown Download 1  
Option Value Name: of 1  
Option Value Sort Order: 10  

Option Name pick from dropdown Download 1  
Option Value Name: of 2  
Option Value Sort Order: 20  

Option Name pick from dropdown Download 1  
Option Value Name: of 3  
Option Value Sort Order: 30  

Option Name pick from dropdown Download 1  
Option Value Name: of 4  
Option Value Sort Order: 40  

Option Name pick from dropdown Download 1  
Option Value Name: of 5  
Option Value Sort Order: 50  

Then make a set for Download 2, 3, 4, 5  

Note: when making these, only make patterns that match  
Download 3 of 1 doesn't make sense so don't make an Option Name: of 1 for the Option Name: Download 3  

<font size="4">**Adding to Products via Attributes Controller**</font>  
Now you can make the Attribute read correctly based on how many downloads ...  
Note: You may find a better pattern of text so you don't get lost in making the Attributes ...  

In Attributes Controller:  

Option Name: Download 1  
Option Value: of 5 [Download 1]  
Download filename of file already uploaded to the /download folder.  
Number of Days and Downloads  

Option Name: Download 2  
Option Value: of 5 [Download 2]  
Download filename of file already uploaded to the /download folder.  
Number of Days and Downloads  

Option Name: Download 3  
Option Value: of 5 [Download 3]  
Download filename of file already uploaded to the /download folder.  
Number of Days and Downloads  

Option Name: Download 4  
Option Value: of 5 [Download 4]  
Download filename of file already uploaded to the /download folder.  
Number of Days and Downloads  

Option Name: Download 5  
Option Value: of 5 [Download 5]  
Download filename of file already uploaded to the /download folder.  
Number of Days and Downloads  

Don't worry on the Sort Order as you set the defaults when these were made ...  

When done adding the Downloads ... just click on the Update Sort order button and all will sort nicely ...  

==========================  

### Another way of looking at it:

**1\. Options Names Manager ...**  

Add an Option Name: Downloads (could have called this anything)  
Option Type: Radiobutton or Dropdown  

**2\. Option Values Manager ...**  
Add an Option Value:  
Option Name: Downloads (from dropdown)  
Option Value: PDF  
Default Sort Order: 10  

**3\. Attributes Controller ...**  

Find Product ...  
Pick from Option Name dropdown: Downloads  
Pick from Option Value dropdown: PDF [DOWNLOAD]  
Enter the filename: test.zip or whatever  
Enter the number of days  
Enter the number of download attempts  
Set as Default  
Set Sort Order (if needed or after adding you can run the Update Sort Orders)  

Click Insert ...  

If the file is already uploaded to the /download folder (and it needs to be), then you should see a green dot next to the filename ...  

Now just test and make sure from add to cart to checkout to download that all is working for you.  

## Additional Notes about Downloads and Shipping Costs

Downloads **know** there are no shipping costs automatically due to the fact that you added a Download filename to the Attribute.  
Thus, Downloads **should NOT** be marked as Always Free Shipping, and **should NOT** be marked as Virtual Products.  

## File Permissions for Downloads

Files for download (ie: all the files in the "download" folder) should be marked as read-only. Setting to 644 should be sufficient.  
The "download" folder itself is typically set to 755, which is the normal default permissions setting for folders.  
If you are using download-by-redirect, then your "pub" folder needs to be read-write, typically 777 (or 755 on some hosts).  

## Important Facts about Download Settings

1.  Downloads are NOT Virtual Products so use:  
    _Product is Virtual: No, Shipping Address Required  

    _
2.  Downloads are NOT Always Free Shipping so use:  
    _Always Free Shipping: No, Normal Shipping Rules  

    _
3.  Downloads in an order by itself will never see the checkout_shipping page ... if you do then your Product is setup wrong for Downloads  

4.  If not on a Windows server, meaning Linux/Unix, /pub should be writable (usually 777 or 755 depending on the host server) and Redirect should be ON  
    If you cannot use Redirect ON, ask your hosting site why they cannot follow the symbolic link between the /download and /pub directories  

5.  If on a Windows server, /pub does NOT need to be writable/777 since you do not use this directory because symlinks typically don't work on Windows servers, and Redirect is OFF since Redirect requires symlink support.  

6.  Download filenames should not use special characters, spaces, etc  

7.  Download files should be zipped for best results and best compatibility for most customers and most browsers.  

8.  Download files should be loaded to the /download directory  

9.  On the Admin->Catalog->Attributes Controller you should see a green dot next to the filename of the Download itself

**ALSO:** See the Related Article about [Download Delivery Methods](/user/products/download_delivery_methods). 
