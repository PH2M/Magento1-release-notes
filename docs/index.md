Magento Open Source 1.9.4.5 Release Notes
-----------------------------------------

This version (or patch SUPEE-11314, which applies to older versions of Magento) provides resolution of multiple critical security issues. These security enhancements help close cross-site scripting, arbitrary code execution, and sensitive data disclosure vulnerabilities as well as other security issues.

Magento Open Source 1.9.4.4 Release Notes
-----------------------------------------

This version (or patch SUPEE-11295, which applies to older versions of Magento) provides resolution of multiple critical security issues and functional fixes. These security enhancements help close cross-site scripting, arbitrary code execution, and sensitive data disclosure vulnerabilities as well as other security issues.

### Fixed issues and enhancements

*   The **Disable** button present when you run the compiler from **Admin** > **System** > **Tools** > **Compiler** is now enabled as expected. Previously, when you clicked the **Disable** button, it did not change state.

Magento Open Source 1.9.4.3 Release Notes
-----------------------------------------

This version (or patch SUPEE-11219, which applies to older versions of Magento) provides resolution of multiple critical security issues and functional fixes. These security enhancements help close cross-site scripting, arbitrary code execution, and sensitive data disclosure vulnerabilities as well as other security issues.

### Fixed issues and enhancements

*   WebserviceX has been removed from the Magento 1.x code base.
*   This release adds two new currency services for currency rate import: [CurrencyConverterAPI](https://web.archive.org/web/20200513111617/https://www.currencyconverterapi.com/) and [FixerIO](https://web.archive.org/web/20200513111617/https://fixer.io/)

### Known issue

This release includes a fix for a security vulnerability that potentially allowed changes to protected store settings. As a result, extensions or customizations that depend on saving configuration fields that are not defined in `system.xml` files may no longer work correctly.

Magento Open Source 1.9.4.2 Release Notes
-----------------------------------------

This version (or patch SUPEE-11155, which applies to older versions of Magento) provides resolution of multiple critical security issues and functional fixes. These security enhancements help close cross-site scripting, arbitrary code execution, and sensitive data disclosure vulnerabilities as well as other security issues.

**Note**: We are aware of the incompatibilities between patch SUPEE-11155 and the PHP 7.2 support patch and are currently working on a new version of SUPEE-11155 that resolves these incompatibilities. See [Security Patch SUPEE-11555 - Possible issues?](https://web.archive.org/web/20200513111617/https://magento.stackexchange.com/questions/279571/security-patch-supee-11155-possible-issues) for a community-driven discussion on issues and solutions related to this SUPEE. Check these release notes and the [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security) for updates on the availability on the new patch.

### Fixed issues and enhancements

*   The Magento logging feature now works as expected after the SUPEE-11086 patch is installed. Previously, after application of this patch, Magento could only write only to a file that already existed on the server, and did not create new log files.
*   Magento 1.14.4.0 and the PHP7.2 support patch now include the same files as expected. The previous version of the patch did not include the following three files, which were included in Magento 1.14.4.0. Magento 1.14.4.0: `lib/phpseclib/PHP/Compat/Function/array_fill.php`, `lib/phpseclib/PHP/Compat/Function/bcpowmod.php`, and `lib/phpseclib/PHP/Compat/Function/str_split.php`.

### Known issues

The extensive security enhancements we’ve included to this release have resulted in the following changes to Magento behavior:

*   You can no longer upload files with the extension `.swf` to the WYSIWYG editor.
*   Third-party checkout extensions and closed security cases will either not work securely or will not work at all.
*   The Authorize.net Direct Post module  has been enhanced to support the replacement of Authorize.net’s MD5-based hash with a (SHA-512) signature key. Authorize.net will no longer support implementations using the MD5-based hash as of June 28, 2019. You will need to update your signature key after upgrading to this version of Magento. For information about updating your signature key, see the Get a New Signature Key discussion in the [Update Authorize.Net Direct Post from MD5 to SHA-512](https://web.archive.org/web/20200513111617/https://support.magento.com/hc/en-us/articles/360024368392) help article. Note that although this help article describes how to install the earlier patch, merchants upgrading to this release of Magento are not applying the patch and should consult only the Get a New Signature Key discussion. If you’ve applied the patch to your Magento installation while running an earlier version of Magento, uninstall the Update Authorize.Net Direct Post from MD5 to SHA-512 patch before upgrading to this release.
*   You can no longer preview JavaScript in a newsletter template in the Admin.
*   Sitemap names cannot exceed 32 characters.

Magento Open Source 1.9.4.1 Release Notes
-----------------------------------------

This version (or patch SUPEE-11086, which applies to older versions of Magento) provides resolution of multiple critical security issues and functional fixes. These security enhancements help close cross-site scripting, arbitrary code execution, and sensitive data disclosure vulnerabilities as well as other security issues.

**Note**: Magento’s implementation of the Authorize.Net Direct Post payment method currently uses MD5-based hash for all M1 and M2 installations. As of June 28, 2019, Authorize.Net will stop supporting MD5-based hash usage.

This will result in Magento merchants not being able to use Authorize.Net Direct Post to process payments. To avoid disruption and to continue processing payments, merchants must apply a patch provided by Magento and add a Signature Key (SHA-512) in the Magento Admin configuration settings. Magento released this patch in late February to address this issue on pre-2.3.1 installations of Magento. See [Update Authorize.Net Direct Post from MD5 to SHA-512](https://web.archive.org/web/20200513111617/https://support.magento.com/hc/en-us/articles/360024368392).

Information about the deprecation of Authorize.Net Direct Post can be found in [Authorize.net Direct Post (Deprecated)](https://web.archive.org/web/20200513111617/https://docs.magento.com/m2/ce/user_guide/payment/authorize-net-direct-post.html).

### Fixed issues and enhancements

*   Google Image Charts has been deprecated and replaced by [Image-Charts](https://web.archive.org/web/20200513111617/https://www.image-charts.com/) for dashboard charts.
*   Layered navigation now works as expected when full page cache and block caching are enabled. Previously, you could not clear layered navigation filters when these features were enabled.
*   Errors caused by problematic PHP error logging have been resolved. Previously, Magento displayed excessive and unnecessary 404 errors.
*   Magento now displays the following message when an invalid character is used, `Attribute code is invalid. Please use only letters (a-z), numbers (0-9) or underscore(_) in this field, first character should be a letter. Do not use "event" for an attribute code`. Previously, Magento did not flag invalid attribute codes.
*   You can now add to the cart products with custom options for which the **custom option** checkbox has not been checked. Previously, Magento did not add the product to the cart, and displayed this message, `Cannot add the item to shopping cart`.
*   URL redirects for products now work as expected. Previously, when you selected a product from the Category page and Add URL Redirect has been enabled, Magento redirected users to URL Redirect Information and threw this error, `exception 'Mage_Core_Exception' with message 'Invalid block type: Mage_Adminhtml_Block_Empty_Edit_Form' in app/Mage.php:580`
*   Magento now displays payment information during the confirmation step of check out and successfully processes an order when inline translation is enabled. Previously, Magento did not display this payment information during check out, and the order was not completed.
*   You can now create a staging website when development mode is enabled. Previously, Magento threw an error after you added a website from System > Content Staging > Staging Websites.
*   You can now successfully delete a website by clicking **Delete Website** as expected. Previously, when you clicked this button, Magento threw a fatal error.
*   You can now add a banner by clicking **Add Banner** from the Admin. Previously, Magento threw an error when you clicked this button.
*   Magento no longer throws an `Undefined index: is_recurring` error when when you try to save a product when deploying Magento with development mode enabled.

### Known issue

*   If there were any custom widgets created by usage of helper methods in layout updates, they will no longer work.

Magento Open Source 1.9.4.0 Release Notes
-----------------------------------------

This version (or patch SUPEE-10975, which applies to older versions of Magento) provides resolution of multiple critical security issues and functional fixes. These critical security issues include remote code execution (RCE), cross-site scripting (XSS), and cross-site request forgery (CSRF) issues. This release also provides support for PHP 7.2.

Note that after updating to this release, third-party modules that depend upon Magento core backup functionality will no longer work. Alternatively, you can use one of these two methods to enable database backups:

*   Change **false** to **true** in the **config** > **modules** > **Mage\_Backup** > **active** setting of `app/etc/modules/Mage_All.xml`.
*   From the Admin, change the **System** > **Configuration** > **Advanced** > **Disable  Modules Output** > **Mage\_Backup** from **disabled** to **enabled**.

### Fixed issues and enhancements

*   This release provides support for PHP 7.2.
*   We’ve removed the CC module. As a result, third-party modules that depend upon either the `ccsave` method or the `xmlconnect` method will not work as expected. Third-party themes that implement `ccsave` will not work as expected, either.
*   The Magento logo has been updated throughout the code base.
*   The **Continue** button now works as expected on the Payments step of checkout when paying with the PayPal payment method.
*   Google Tag Manager now logs sales information in Google Analytics as expected.
*   The product export CSV file now contains columns for super attributes.
*   Magento no longer throws an error when a customer accesses their shopping cart after items in their cart have been removed due to a timeout. Previously, Magento displayed this error, \`Notice: Undefined variable: freePackageValue in /var/www/dev/htdocs/app/code/core/Mage/Shipping/Model/Carrier/Tablerate.php on line 130\`.
*   Clicking on a configurable product’s swatch on the product list page now updates product price as expected.
*   Customers can now successfully add a grouped product to their shopping cart when category permissions are enabled. Previously, Magento did not add the product to the cart, but instead displayed a descriptive error message.
*   Magento no longer displays incorrect prices on the storefront after a failure of the enterprise refresh index.
*   We’ve resolved issues in the indexing locking mechanism that previously resulted in Magento throwing an exception after indexing completed.
*   Magento no longer throws a fatal error when a merchant uses an already reserved word to name a product attribute.
*   Magento now adds the correct sales tax to orders being shipped to U.S. addresses that use zip codes with the optional four-digit suffix (for example, 73365-1234). Previously, the Tax rule triggered a failure if the U.S. zip code that had this optional four-digit suffix.
*   Magento now displays all products on a production website that were edited by a role-restricted user on the associated staging website.
*   We’ve resolved an issue that caused Target Rules to throw an exception when a customer opened a product view page.

Magento Open Source 1.9.3.10 Release Notes
------------------------------------------

This version (or patch SUPEE-10888, which applies to older versions of Magento) provides resolution of multiple critical security issues. These critical security issues include remote cross-site scripting and cross-site request forgery issues. We recommend upgrading your Magento store to this latest version. See [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-10888) for a comprehensive discussion of these issues.

**Note:** With this release, Magento is announcing the following support policy: For Magento Open Source 1.5 to 1.9, Magento will provide software security patches through June 2020 to ensure those sites remain secure and compliant. Visit our [information page](https://web.archive.org/web/20200513111617/https://info2.magento.com/M1OpenSource.html) for more details about our software maintenance policy and other considerations for your business.

### Known issue

You cannot re-send the password for new customers who created their account during checkout.

Magento Open Source 1.9.3.9 Release Notes
-----------------------------------------

This version (or patch SUPEE-10752, which applies to older versions of Magento) provides resolution of multiple critical security issues. These critical security issues include remote code execution, cross-site scripting, and cross-site request forgery issues. We recommend upgrading your Magento store to this latest version. See [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-10752) for a comprehensive discussion of these issues.

### Fixed issues and enhancements

*   Magento no longer performs unnecessary write operations on the `core_url_rewrite` table.
*   Customers can now successfully register during checkout without being unexpectedly logged out.
*   Incorrect escaping in the `cron.sh` file no longer prevents cron jobs from running in parallel as expected.
*   Magento now cleans session data as expected after a customer logs out.

### Known issue

If your custom code or extension is using `Zend/Filter/PregReplace.php` with the modifier `e`, it will now return an error due to possible RCE issues. See [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-10752) for more information.

Magento Open Source 1.9.3.8 Release Notes
-----------------------------------------

This version (or patch SUPEE-10570, which applies to older versions of Magento) provides resolution of multiple critical security issues. These critical security issues include authenticated Admin user remote code execution, unauthorized data leaks, and cross-site request forgery (CSRF) vulnerabilities. We recommend upgrading your Magento store to this latest version. See [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-10570) for a comprehensive discussion of these issues.

### Fixed issues and enhancements

*   Changed Magento Admin to support recent USPS shipping changes. On February 23, 2018, USPS removed APIs that support the creation of shipping labels without postage. In response, we’ve removed this functionality from the Magento Admin. Consequently, you cannot create and print shipping labels that do not have postage applied.  
*   Updated copyright to 2018.

### Known issues

These two known issues are associated with the use of HTML tags within a product’s SKU attribute:

*   If you try to import products that contain HTML tags in the SKU attribute, Magento displays this error at the data validation stage (that is, when you click **Check data**):  `Invalid value in SKU column. HTML tags are not allowed`.
*   If you try to create or edit a product in the Admin panel and the product’s SKU attribute value contains HTML tags, Magento throws this error when you try to save the product: `HTML tags are not allowed in SKU attribute`.

Magento Open Source 1.9.3.7 Release Notes
-----------------------------------------

This patch (SUPEE-10415) provides resolution of multiple critical security issues. These critical security issues include remote code execution, cross-site scripting, and cross-site request forgery issues. We recommend upgrading your Magento store to this latest version. See [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-10415) for a comprehensive discussion of these issues.

### Fixed issues

*   Magento no longer displays the “Invalid Secret Key. Please refresh the page." message when a user loads the Admin.
*   The one-page checkout page now displays the following message when a customer checks out an order for which no amount is due: **No payment information required**. Magento versions prior to 1.14.3.3 included this message, but it was missing from v1.14.3.3.
*   We’ve fixed a typo in the patch header information. (`autocomplete="new-pawwsord"` is now `autocomplete="new-password"`.)

### Known issue

**Issue:** Magento displays a "404: Page Not Found" error from the `errors/` directory after upgrading to SUPEE-10415. This issue occurs only in Magento installations that run certain third-party extensions.

**Description:** Magento is not properly logging PHP warnings that occur early during page initialization. Instead, of logging the error and continuing operation, Magento generates a 404 page. (Previously, Magento logged these warnings in the system.log file, and execution would continue as usual.)

**Workaround:** Confirm that there are no PHP warnings generated by any of the extensions or customizations.

### Notes

*   We no longer support custom file extensions for `Mage::log()`. Supported file extensions include `.log`, `.txt`, `.html`, `.csv`. For more information, navigate to **Developers > Log Settings** from the Admin. Magento displays this comment: **Logging from Mage::log(). File is located in /var/log. Allowed file extensions: log, txt, html, csv.**
*   Passwords for new users are now limited to 256 characters. If a new user enters a password that exceeds 256 characters, Magento displays this message: **Please enter a password with at most 256 characters**.

Magento Open Source 1.9.3.6 Release Notes
-----------------------------------------

This patch (SUPEE-10266) provides resolution of multiple critical security issues and several functional fixes. These critical security issues include remote code execution, cross-site scripting, and cross-site request forgery issues. We recommend upgrading your Magento store to this latest version. See [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-10266) for a comprehensive discussion of these issues.

*   We’ve also fixed an issue where uploaded images were twice their original size after you applied SUPEE-9767 v2.

Magento Open Source 1.9.3.5 Release Notes
-----------------------------------------

We have skipped release 1.9.3.5.

Magento Open Source 1.9.3.4 Release Notes
-----------------------------------------

This patch addresses both security and functional issues discovered when using the `SUPEE-9767` patch. We recommend upgrading your Magento store to this latest version.

Here are your upgrade options:

*   Upgrade to Magento Open Source 1.9.3.4. You don’t need to revert any patches or install SUPEE-9767 version 2 as version 2 is already included in the Open Source 1.9.3.4 release.
*   If you’ve already installed SUPEE-9767 version 1, you can either:
    *   Upgrade to Magento Open Source 1.9.3.4, or
    *   revert SUPEE-9767 version 1, then install SUPEE-9767 version 2.
*   If you haven’t installed SUPEE-9767 version 1, you can either:
    *   Upgrade to Magento Open Source 1.9.3.4, or
    *   install SUPEE-9767 version 2.

See [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-9767) for a comprehensive discussion of these security issues.

This release also provides support for the following functional issues:

### General fixes

*   We’ve restored missing `strip_tags` functionality in the checkout JavaScript.
*   We’ve changed how Magento validates form keys during the generic five-step checkout process. Previously, customer registration failed during standard checkout processing if form key authentication was enabled.
*   Magento now displays the `Allow_symlinks` message in the Admin message area as expected.
*   Magento now preserves the background transparency of uploaded images as expected. Previously, transparency was lost after the image was uploaded, resulting in an unusable image.
*   You can now use Checkout with Multiple Addresses when checkout form validation is enabled.

### Installation

*   The Allow symlinks option is now disabled during installation or upgrade processes. Previously, when you changed the Allow symlinks setting to true in the database before upgrading and then installing the patch, this option remained enabled, but you could no longer access it from the Admin panel.

This patch is available from [Magento Tech Resources](https://web.archive.org/web/20200513111617/https://magento.com/tech-resources/download).

Magento Open Source 1.9.3.3 Release Notes
-----------------------------------------

This patch provides resolution of multiple critical security issues. These critical issues include remote code execution for authenticated Admin users, access control bypass, and cross-site request forgery issues. See [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-9767) for a comprehensive discussion of these issues.

This release also provides support for the following issue:

Support for PayPal's update to its Instant Payment Notification (IPN) server URL. PayPal provides more information about this feature in [IPN Verification Postback to HTTPS Microsite](https://web.archive.org/web/20200513111617/https://www.paypal-knowledge.com/infocenter/index?page=content&widgetview=true&id=FAQ1916&viewlocale=en_US). This update is essential for retaining uninterrupted service after June 30.

`SUPEE-8167`, an older patch that also contains this fix, was added on May 8, 2017, and is available from [Magento Tech Resources](https://web.archive.org/web/20200513111617/https://magento.com/tech-resources/download).

### Known Issues

This patch/release has known issues. Please see [SUPEE-9767](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-9767) for updates.

**Note:** Before applying this patch or updating to this release, disable the **Symlinks** setting in **System > Configuration > Advanced > Developer > Enable Symlinks**. If the **Symlinks** setting is enabled, it will override your configuration file settings. If that override occurs, you will need to directly modify the database to change those settings.

Magento Open Source 1.9.3.2 Release Notes
-----------------------------------------

This patch addresses the following issues:

*   Removal of vulnerability with the Zend framework `Zend_Mail` library. For more information, see [Magento Security Center](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-9652).
*   Updated the copyright year to 2017.

Magento Open Source 1.9.3.1 Release Notes
-----------------------------------------

This patch addresses the following issues:

*   We restored the old tax calculation algorithm for shipping charges. The patch to apply new calculation will be available on request.
*   Resolved an issue with setting the session lifetime to 0.
*   The monthly cron job that cleans up the table that contains IP addresses and passwords runs properly.
*   All configurable product images are imported.
*   You no longer get an exception due to an undefined `addCrumbs()` method call.
*   Resolved the error `Notice: Undefined index: session_expire_timestamp` when accessing the storefront.
*   Values for drop-down label values are saved correctly.
*   The "Price as configured" for bundle products displays correctly in the shopping cart.
*   Auto-generated passwords are sent to new customers as expected.
*   The method `Mage_Api_Model_Server_Handler_Abstract::processingMethodResult()` accepts scalar and array values.
*   The default MySQL Full-Text search works as expected; it no longer returns all products.
*   Prevented a potential [Cross-Site Request Forgery (CSRF)](https://web.archive.org/web/20200513111617/https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html) vulnerability by changing the form key when a customer signs out of the storefront.
*   Catalog price rules return the correct price.
*   Indexers now update all products instead of skipping the last product updated.

![note](/web/20200513111617im_/https://devdocs.magento.com/guides/m1x/images/icon-note.png)**Note**: You currently _cannot_ upgrade to this version using Magento Connect Manager. We expect to resolve this issue soon.

Magento Open Source 1.9.3.0 Release Notes
-----------------------------------------

See the following sections for information about this release:

*   [Highlights](#ce19-1930-highlights)
*   [Security Enhancements](#ce19-1930security)
*   [Check for `.swf` Files After Upgrade](#ce19-1930security-upgrade)
[](#ce19-1930security-upgrade)*   [](#ce19-1930security-upgrade)[Backward-Incompatible Changes](#ce19-1930back)
*   [Fixes](#ce19-1930fixes)

### Highlights

Magento Open Source 1.9.3 delivers more than 120 quality improvements, as well as support for PHP 5.6 in addition to PHP 5.4 and 5.5.

### Security Enhancements

We addressed the following security issues in this release:

*   [General security enhancements](#ce19-1930security-general)
*   [Password enhancements](#ce19-1930security-pwd)

#### General security enhancements

For more information about these security enhancements, see [our Security Center article](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-8788).

Patches for major security issues in earlier versions of the Magento software are available on the [Magento download page (look for `SUPEE-8788`.)](https://web.archive.org/web/20200513111617/https://www.magentocommerce.com/download)

[](https://web.archive.org/web/20200513111617/https://www.magentocommerce.com/download)

[See](https://web.archive.org/web/20200513111617/https://www.magentocommerce.com/download) [How to Apply the SUPEE-8788 Patch](/web/20200513111617/https://devdocs.magento.com/guides/m1x/other/ht_install-patches.html#apply-8788)

.

*   Resolved a potential SQL injection (Zend Framework issue)
*   Resolved a cache poisoning issue
*   We now provide better protection against path exploits.
*   Resolved a potential [cross-site scripting (XSS)](https://web.archive.org/web/20200513111617/https://www.owasp.org/index.php/XSS) vulnerability when adding a category.
*   Resolved a potential XSS vulnerability that affected the Magento server's request URI.
*   Resolved a potential XSS vulnerability in invitations.
*   You can no longer cause out-of-memory errors on the Magento server by flooding it with images that have incorrect dimensions.
*   The Magento Admin Panel login page now renders in HTTPS if you configured the Magento server for HTTPS.
*   We added the [`nosniff` header](https://web.archive.org/web/20200513111617/https://www.owasp.org/index.php/List_of_useful_HTTP_headers) to our `.htaccess` files.
*   Magento no longer uses Adobe Flash for uploads.
*   Fixed several potential issues indicated by static code scans.
*   Resolved a potential man-in-the-middle vulnerability.
*   Resolved a potential PHP security vulnerability.
*   An administrative user is no longer able to create a potential security vulnerability that used the block cache.
*   Resolved a potential [cross-site request forgery (CSRF)](https://web.archive.org/web/20200513111617/https://wiki.owasp.org/index.php/Cross-Site_Request_Forgery_%28CSRF%29) vulnerability involving the wishlist.
*   Resolved a potential remote code execution exploit.
*   It is no longer possible to log in to a store as an existing customer using only an e-mail address.

#### Password enhancements

*   A user can reset a password only after receiving an e-mail. In addition, we introduced the following configuration settings:
    *   Limit the number of forgotten password requests from one IP address to five times per hour.
    *   Limit the number of forgotten password requests from one e-mail address to five times per 24 hours.
    *   Limit the number of forgotten password requests to no more than once ever 10 minutes per e-mail address.
*   The forgot password link expires after the first use or two hours (by default).
*   When a user changes their e-mail address, they are required to provide their password and to acknowledge the change from the previous address.
*   We now ignore leading and trailing spaces in a user's password.
*   The new customer e-mail now includes the customer's password.
*   Resetting a password using a password recovery e-mail succeeds.

### Check for `.swf` Files After Upgrade

If you upgraded to Magento Open Source 1.9.3 after applying the [SUPEE-8788 patch](https://web.archive.org/web/20200513111617/https://magento.com/security/patches/supee-8788), make sure the following files have been deleted:

skin/adminhtml/default/default/media/flex.swf
skin/adminhtml/default/default/media/uploader.swf
skin/adminhtml/default/default/media/uploaderSingle.swf

If the files are present, delete them to avoid a potential security exploit. As of Magento Open Source 1.9.0.0, we no longer distribute `.swf` files with the Magento software.

### Backward-Incompatible Changes

The following backward-incompatible changes were made in this release:

`Mage_Adminhtml_Block_Cms_Wysiwyg_Images_Content_Uploader`: Parent class was removed.

`Mage_Uploader_Model_Config_Abstract`: Overrides the magic method `__call` and its behavior can be inconsistent. For example:

\->setData('underscore\_key', 1)
->getUnderscoreKey() //null

### Fixes

The following sections discuss other fixes in this release:

*   [Tax Calculation Fixes](#ce19-1930tax)
*   [Shopping cart and checkout fixes](#ce19-1930fixes-cart)
*   [Catalog fixes](#ce19-1930fixes-cat)
*   [Price rule fixes](#ce19-1930fixes-price)
*   [Configurable swatches fixes](#ce19-1930fixes-swatch)
*   [Import/export fixes](#ce19-1930fixes-import)
*   [Indexer fixes](#ce19-1930fixes-index)
*   [Other fixes](#ce19-1930fixes-other)

#### Tax Calculation Fixes

*   The subtotal including tax on an invoice is calculated correctly.

#### Shopping cart and checkout fixes

*   One product displays one time in a cart even if the product was added once as a guest and another time as a logged-in user.
*   Bundled products now display properly in the mini cart as well as the shopping cart.
*   Moving a configurable product to a shopping cart in the Admin Panel functions normally.
*   Shipping discount coupons are now based correctly on a customer's shipping address.
*   First Class Mail letter now displays as a shipping option in the shopping cart.
*   You can now pay for a product using both store credit and reward points.
*   An exception no longer displays when a customer uses a gift card in an invalid transaction (such as an incorrect payment card number).
*   We added validation so a special price must be less than the actual price.
*   Exceptions no longer display when a customer checks out.
*   Fixed a programming issue that prevented serializing and unserializing values in the shopping cart.
*   Magento recovers from payment processor unavailability properly; the customer is charged and the item is shipped.
*   You can no longer order an empty product; that is, a product with no options.

#### Catalog fixes

*   A configurable product with decimal quantity less 1 now displays the proper quantity in the catalog.
*   Configurable products are now sorted by attribute, not by product ID.
*   Errors no longer display when you use `Mage_Catalog_Block_Product_List` on a product detail page.
*   Removed the undefined variable `where` from `app/code/core/Mage/CatalogSearch/Model/Resource/Fulltext.php`.

#### Price rule fixes

*   A catalog price rule that targets a bundled product by percentage calculates the price properly.
*   A shopping cart price rule that includes tax now calculates properly.
*   With the flat product catalog enabled, a catalog price rule with multi-select attributes works properly.
*   Errors no longer display when two users add a product at the same time. Magento thanks Babenko eCommerce for contributing this fix.
*   You can now add configurable products to the shopping cart after configuring a shopping cart rule.

#### Configurable swatches fixes

*   Fixed a memory leak in the configurable swatches module.
*   Configurable swatches for out-of-stock products now display consistently in layered navigation, the category view page, and the product view page.
*   Configurable swatches work properly even if there is no image (before the fix, a JavaScript error was thrown).
*   Resolved performance issues.
*   Swatch images for configurable products display properly.

#### Import/export fixes

*   We bundled the following fixes in a patch:
    *   Exporting a large number of products no longer results in an out-of-memory error.
    *   You can import into multiple stores if some stores are set to be replaced.
    *   Re-importing customers that have a multi-select attribute preserves the attribute.
    *   File uploads are processed properly.
    *   Fixed broken help links in the Magento Admin Panel.
*   Importing products no longer consumes an excessive amount of memory.
*   Coupon reports exported as `.csv` now display the correct totals.

#### Indexer fixes

*   With flat category tables enabled, reindexing no longer removes the category class tag.
*   Resolved errors with the Product Flat Index not completely indexing a large number of changes.
*   All indexes now reindex when set to update when scheduled.
*   Improved performance of the category indexers. Magento thanks Vaimo for contributing this fix.
*   Categories saved with a `/` character as the suffix display properly.

#### Other fixes

*   Applied United States Postal Service API changes for [January 17, 2016](https://web.archive.org/web/20200513111617/https://www.usps.com/business/web-tools-apis/documentation-updates.htm).
*   Default variable values now save normally.
*   The WYSIWYG editor handles XHTML tags like `cellpadding` and `cellspacing` properly.
*   The configuration setting **Allow HTML Tags on Frontend** is honored.
*   Orders created using the Magento Admin now display on the Orders and Returns page on the storefront.
*   The option to merge Cascading Stylesheets (CSS) and JavaScript now works properly with a responsive web design (RWD) theme.
*   On a mobile device when the Magento storefront uses an RWD theme, the Filter bar displays one time only.
*   The Magento Connect Manager downloader's `.htaccess` file is no longer overwritten when the downloader component is updated.
*   The configuration cache is no longer corrupted under heavy load.
*   Order update e-mails are sent only once.
*   A SOAP API call to `/api/soap/?wsdl` returns normally.
*   A value that contains special characters is handled without errors by the SOAP API.
*   Fixed the untranslatable `base/default/template/sales/guest/form.phtml` template.
*   Magento now stores two-digit birth years properly (for example, `80` is stored as `1980`).
*   HTTP 200 (OK) status codes are returned for pages after a session expires.
*   You can view a disabled product without errors if compilation is enabled.
*   A Value Added Tax (VAT) ID now validates properly. If the customer specifies an invalid ID, the customer is notified they will be charged VAT tax.
*   Listing shipments no longer displays an exception.
*   You can filter associated products for a group product without errors.
*   When you manage product attributes, selecting an action from **Actions** works properly.
*   You can now add a configurable product by SKU to an order using the Admin Panel.
*   You can now save a product's weight attribute.
*   Using a Portable Network Graphics (`.png`) image on a CMS page no longer results in a `HEADERS_ALREADY_SENT` message to be logged.
*   Fixed an exception related to an unknown database table.
*   Fixed an issue with JavaScript merging.
*   You can now print 10 or more shipping labels without issues.
*   A PHP notice no longer occurs when you log the Magento Admin Panel IP address in the event log.
*   A SQL error no longer displays when you create a new floating point product attribute programmatically.
*   Added a missing image to the codebase.
*   The expression `Mage::getModel('core/variable')->addValuesToResult()` returning a collection with column `plain_value` and `html_value` now returns a collection with columns `plain_value` and `html_value`.
*   Payment no longer results in the exception `ERR (3): Notice: Undefined offset: 1 in app/code/core/Mage/Sales/Model/Order.php on line 1258`.
*   The correct telephone number displays in transactional e-mails. We changed the variable `phone` to `store_phone`. Magento thanks Classy Llama Studios for contributing this fix.
*   The Google sitemap now lists store URLs properly.
*   Implemented search query caching, which speeds up search results.
*   After a customer submits an order, the following error should not display: `SQLSTATE[23000]: Integrity constraint violation: 1062 Duplicate entry 'ECO0000148' for key 'UNQ_SALES_FLAT_ORDER_INCREMENT_ID'`.
*   With flat category enabled, you no longer see errors due to an undefined method call.
*   Case-sensitive variations of URL rewrites work as expected.
*   Resolved a JavaScript syntax error in `bundle.js`.
*   The cron-related error `Warning: shell_exec() has been disabled for security reasons...` has been resolved. Magento thanks Stefan Hagspiel for reporting this issue.
*   cron no longer runs multiple times unnecessarily.
*   Cached static blocks now display properly.

Magento Open Source 1.9.0.1 Release Notes
-----------------------------------------

Magento Open Source 1.9.0.1 resolved the following issues:

*   Customers can no longer apply a coupon from an inactive shopping cart price rule to a purchase.
*   Customers using a smartphone or other small viewport can expand subcategories in the web store that uses the new responsive theme.

Recent Patches
--------------

We'd like to draw your attention to several new patches that were recently posted to the Partner Portal and Support Center. These patches deliver important improvements, such as enabling several concurrent administrators to work with the product catalog, and to make it easier to install community-created translation packages.

Details about the patches follow. To install patches, see [How to Get Patches For Magento Commerce](#ce19-patches-how-to-get).

*   [General Magento Connect Patches](#ce19-patches-connect-general)
*   [Magento Install Page Displays After SOAP v2 Index Page Refresh](#ce19-patches-soap)
*   [How to Get Patches For Magento EE](#ce19-patches-how-to-get)

![note](/web/20200513111617im_/https://devdocs.magento.com/guides/m1x/images/icon-note.png)**Note**: Some of the patches discussed in this section have `EE_1.14.0.1` in the name. These patches were all tested against Open Source 1.9.x as well.

### General Magento Connect Patches

_Patch name_: SUPEE-3941

*   When you install a community-created translation package, the translation provided by the package overwrites any existing translations for the same items. This enables you to more easily install packages with translations.
*   To improve security, Magento Connect now uses HTTPS by default to download extensions, rather than FTP.
*   Extension developers can now create an extensions with a dash character in the name. Merchants can install those extensions without issues.
*   Magento administrators who attempt to install an extension with insufficient file system privileges are now informed. Typically, the Magento Admin Panel runs as the web server user. If this user has insufficient privileges to the _your Magento install dir_`/app/code/community` directory structure, the Magento administrator sees an error message in the Magento Connect Manager.  
    To set file system permissions appropriately, see [After You Install Magento: Recommended File System Ownership and Privileges](/web/20200513111617/https://devdocs.magento.com/guides/m1x/install/installer-privileges_after.html#extensions).

### Magento Install Page Displays After SOAP v2 Index Page Refresh

_Patch name_: SUPEE-3762. Refreshing the SOAP v2 index page (`http://_your-magento-host-name_/index.php/api/v2_soap/index/`) results in all administrators and customers viewing the Magento installation page.

### How to Get Patches For Magento Open Source

This section discusses how to get patches referenced in these Release Notes.

To get patches for Magento Open Source:

1.  Log in to [www.magentocommerce.com/download](https://web.archive.org/web/20200513111617/http://www.magentocommerce.com/download).
2.  In the left pane, click **Downloads**.
3.  Scroll down to the Magento Open Source Patches section.
4.  Follow the prompts on your screen to download a patch for your version of Magento Open Source.
5.  Apply the patch as discussed in [How to Apply and Revert Magento Patches](/web/20200513111617/https://devdocs.magento.com/guides/m1x/other/ht_install-patches.html).

Magento Open Source 1.9.0.0 Release Notes
-----------------------------------------

See the following sections for information about changes in this release:

*   [Highlights](#ce19-1900-highlights)
*   [Security Enhancements](#ce19-1900security)
*   [Changes](#ce19-1900-changes)
*   [Tax Calculation Fixes](#ce19-1900tax)
*   [Fixes](#ce19-1900fixes)

### Highlights

This section lists the key new features in Magento Open Source 1.9. For more information about these new features, see the [Magento User Guide](https://web.archive.org/web/20200513111617/http://www.magentocommerce.com/resources/magento-user-guide).

*   The default theme in Magento Open Source 1.9 uses [Responsive Web Design](https://web.archive.org/web/20200513111617/https://en.wikipedia.org/wiki/Responsive_web_design) principles to provide a better experience for users of mobile devices in particular. Benefits include:
    *   You can get a tablet and smart phone friendly responsive site in about half the time as before, speeding time to market and freeing up resources for other projects.
    *   Your responsive site makes you better able to participate in the fast growing mobile commerce space, gives you the ability to more easily adapt to new opportunities, and is less expensive to maintain. A responsive site also offers potential search engine optimization (SEO) benefits because it uses Google's preferred approach to mobile-optimizing sites.
*   Cross-border trade: (Also referred to as _pricing consistency_.) We support European Union (EU) merchants operating across regions and geographies who want to show their customers a single price. Pricing is clean and uncluttered regardless of tax structures and rates that vary from country to country.  
    To enable cross-border trade in the Admin Panel, click **System** > **Configuration** > SALES > **Tax** > **Calculation Settings**, option **Enable Cross Border Trade**.
*   Supports [PHP 5.4](https://web.archive.org/web/20200513111617/http://www.php.net/manual/en/migration54.changes.php). For more information, see [the PHP changelog](https://web.archive.org/web/20200513111617/http://php.net/ChangeLog-5.php#5.4.0).
*   The Zend Framework has been upgraded to [version 1.12.3](https://web.archive.org/web/20200513111617/http://framework.zend.com/changelog/1.12.3/)
*   Checkout improvements:
    
    *   You can capture up to 18% more sales by providing customers access to financing using the Bill Me Later service at no additional cost to you.
    *   You can offer your customers a smoother, more streamlined PayPal Express Checkout experience, which tries alternative payment options when a customer's credit card is rejected
    *   Improve the PayPal Express checkout experience by eliminating the following steps in the checkout process:
        *   The order review page can be enabled or disabled
        *   Eliminate the necessity of clicking **Update Order** before **Place Order**
    
    (_Conversion_ means helping customers stay interested and complete their purchases.)
    
    ### Security Enhancements
    
    *   Addressed a potential cross-site scripting (XSS) vulnerability while creating configurable product variants.
    *   Addressed a potential security issue that could result in displaying information about a different order to a customer.
    *   Users can no longer change the currency if the payment method PayPal Website Payments Standard is used.
    *   Removed an `.swf` file from the Magento distribution because of security issues.
    *   Improved file system security.
    *   Enhanced the security of action URLs, such as billing agreements.
    *   Addressed a potential session fixation vulnerability during checkout.
    *   Improved the security of the Magento randomness function.
    
    ### Changes
    
    *   A default setting for configurable and bundled products has changed. When you create a configurable or bundled product in the Admin Panel, click **Manage** > **Products**. Create a new configurable or bundled product and click the **Design** tab. The default option for **Display Product Options In** has changed to **Product Info Column**.
    *   The Google Websites Optimizer has been disabled because it has been deprecated by Google. (In earlier Magento Commerce versions, this option was available in the Admin Panel at **System** > **Configuration** > SALES > **Google API** > **Google Website Optimizer**).
    *   Two new options to prevent ["clickjacking"](https://web.archive.org/web/20200513111617/http://en.wikipedia.org/wiki/Clickjacking) if you run Magento in a `frame` or `iframe`:
        *   Enable frames only in the same domain.
        *   Enable frames.
        
        ![important](/web/20200513111617im_/https://devdocs.magento.com/guides/m1x/images/icon-important.png)**Important**: For security reasons, Magento strongly recommends against running the Magento software in a frame.
        
        The options are available in the Admin Panel at **System** > **Configuration** > ADVANCED > **Admin** > **Security** and are named **Allow Magento Backend to run in frame** and **Allow Magento Frontend to run in frame**.
        
        Enabling the option causes the [`X-Frame-Options`](https://web.archive.org/web/20200513111617/https://developer.mozilla.org/en-US/docs/HTTP/X-Frame-Options) request header to be sent.
        
    *   FedEx changed their endpoints for sandbox and production to the following:
        
        *   Production: https://ws.fedex.com/web-services
        *   Sandbox: https://wsbeta.fedex.com/web-services
        
        Because of these changes, Magento cannot retrieve shipping rate information or print shipping labels for FedEx unless this fix is applied.
        
    *   Open Source 1.9 includes a fix that prevented some Discover credit cards from validating properly. The issue was that certain Discover credit card number ranges were not recognized as being valid. As a result of the fix, all Discover cards should validate properly.
        
        ![important](/web/20200513111617im_/https://devdocs.magento.com/guides/m1x/images/icon-important.png)**Important**: This is _not_ a security threat. No data has been compromised or misused. It affects only the ability to validate certain credit card number ranges as valid Discover card numbers.
        
    *   The default values for two configuration options changed. Both options can be found in the Admin Panel under **System** > **Configuration** > CATALOG > **Catalog** > **Frontend**. The new default values follow:
        *   **Products per Page on Grid Allowed Values** is now **12, 24, 36**.
        *   **Products per Page on Grid Default Value** is now **12**.
    *   On the New Rule page for shopping cart price rules (**Rule Information** tab page), explanatory text **Usage limit enforced for logged in customers only** was added to the **Uses per customer field**. This is to avoid confusion encountered by some Magento merchants.
    *   Changes to PayPal Express checkout:
        
        *   Changes to both **Proceed to Checkout** and to **Pay With PayPal**:
            *   Customers cannot edit their billing address on the PayPal site—in fact, the billing address does not display on the PayPal site.
            *   Magento Open Source uses the customer's PayPal address information, not the address information stored in Magento Open Source. The customer does not need to enter Magento Open Source or Commerce address information.
            *   When the customer is redirected to the PayPal site, they can click **Change** next to their payment method to change it.
            
            The Magento administrator can set billing address information in the Admin Panel as follows: **System** > **Configuration** > SALES > **Payment Methods**. For any payment method that includes Express Checkout, in Basic Settings, set the value of the **Require Customer's Billing Address** list.
            
        
        *   Changes to **Pay With PayPal** only:
            *   If the Magento administrator does not require the customer's billing address, the customer's billing address is set to the customer's PayPal _shipping_ address.
            *   If Magento requires the customer's billing address, the customer's billing address is set to the customer's PayPal _billing_ address.
            *   On the PayPal site, the customer can click **Change** next to their shipping address to change it. The customer can choose any shipping address configured with PayPal.
            *   Because the customer's configured address in Magento is not used, the customer's shipping address stored in PayPal is never changed.
        
        *   Changes to **Proceed to Checkout** only:
            *   No **Change** link displays next to a customer's shipping address on the PayPal site.
            *   In the event of a shipping address mismatch between Magento and PayPal, the following message displays when the customer attempts to pay using PayPal:  
                
                The address you entered on _store-name_ is different than your PayPal preferred shipping address. 
                Return to _store-name_ if you'd like to change the shipping address
                
                The user can select the **Use as preferred shipping address** checkbox to instruct PayPal to change their shipping address.
        
        ### Tax Calculation Fixes
        
        *   Fixed price and dynamic price bundled products where the price is configured to include tax display prices correctly regardless of tax settings. (For example, customer's default tax rate is different from the origin tax rate.)
        *   Resolved a one-cent rounding issue when Fixed Product Tax (FPT) is enabled and the option **Apply Discount to FPT** is set to **Yes**. (These options are available in the Admin Panel by going to **System** > **Configuration** > SALES > **Tax** > **Fixed Product Taxes**.)
        *   Resolved issues with calculating the credit memo amount when FPT is discounted and the customer purchases more than one item.
        
        ### Fixes
        
        Fixes in this release can be divided into the following categories:
        
        *   [Web Store and Shopping Cart Fixes](#ce19-1900fixes-webstore)
        *   [Promotional Price Rule Fixes](#ce19-1900fixes-price-rules)
        *   [Administrative Ordering, Invoicing, Credit Memo Fixes](#ce19-1900fixes-adminpanel)
        *   [Import Fixes](#ce19-1900fixes-importexport)
        *   [Payment Method Fixes](#ce19-1900fixes-payment)
        *   [Other Fixes](#ce19-1900fixes-other)
        
        #### Web Store and Shopping Cart Fixes
        
        *   A customer can update quantities of items in their mini shopping cart from their My Account page.
        *   The Minimum Advertised Price pop-up works properly in the web store. When the customer clicks **Click for price**, the price displays as expected.
        *   The "customer since" date is correct.
        *   Switching stores when viewing a product with store-scoped URL keys works as expected.
        *   Setting **System** > **Configuration** > CATALOG > **Inventory**, option **Display Out of Stock Products** to **Yes** no longer causes all products to appear as out of stock.
        *   Entering accented characters in the zip code field during checkout results in a validation error instead of an exception message.
        *   Gift card codes are sent only after an item is purchased.
        *   A customer who attempts to log in as another customer with incorrect credentials is denied.
        *   Resolved issues with applying a 100% discount to an order.
        *   Customers are no longer redirected to the home page when they have permission to view a category.
        *   Discount amount displays correctly for products with custom options.
        *   Issues with placing PayPal Payments Advanced or PayPal Payflow Link orders using Internet Explorer 9 have been resolved.
        
        #### Promotional Price Rule Fixes
        
        The following fixes relate to administering and using shopping cart price rules and catalog price rules:
        
        *   Shopping cart price rules apply properly to grouped products.
        *   Two catalog price rules applied to the same product work properly.
        *   The setting **Stop Further Rules Processing** is honored.
        *   A user with read-only privileges in the Admin Panel cannot save changes to a price rule.
        *   Applying a shopping cart price rule does not display an exception.
        *   Coupon codes apply only to products eligible for the price rule.
        
        #### Administrative Ordering, Invoicing, Credit Memo Fixes
        
        *   An administrative user with access to only one website from which a product was deleted no longer sees a stack trace when attempting to create an RMA for that product. In other words, after a customer placed an order for a product on Website1, an administrator with privileges to all websites removes the product. Later, when an administrator with access to only Website1 attempts to create an RMA for the deleted product, that administrator no longer sees an error message; instead, they see an expected `Access Denied` message.
        *   Resolved an issue with incorrectly calculating the amount of an invoice when some items were discounted by a shopping cart price rule.
        *   Credit memo amount is calculated correctly when processing a partial invoice with a discount.
        *   Making comments in a credit memo no longer returns items to stock. (Prerequisite: an administrator set **System** > **Configuration** > CATALOG > **Inventory** > **Product Stock Options**, option **Automatically Return Credit Memo Item to Stock** set to **Yes**.)
        
        #### Import Fixes
        
        *   A product with a custom attribute set imports successfully.
        
        #### Payment Method Fixes
        
        *   If guest checkout is disabled, a customer must log in to check out with PayPal Express.
        *   Eliminated errors in the logs when an administrator clicks **System** > **Configuration** > SALES > **Payment Methods**.
        *   You can now use New Zealand dollars as the base currency with the eWAY Direct payment bridge.
        *   Store credit is applied correctly when using Website Payments Pro Hosted Solution.
        *   If the merchant country is Germany (DE), disabled guest checkout for the express checkout method and PayPal Website Payments Standard.
        
        #### Other Fixes
        
        *   Categories on the web store now display with spaces between category names for cached and non-cached pages.
        *   A customer can now initiate a return from the web store.
        *   An administrative user can subscribe to low stock RSS feeds without errors.
        *   Category URLs work as expected, regardless of the setting of **Create Custom Redirect for old URL** for the category's URL key.
        *   Setting `allow_url_fopen = Off` in `php.ini` has no effect on the CMS WYSIWYG editor.
        *   No fatal error displays when a role-restricted user previews a newsletter in the Admin Panel.
        *   Google Sitemap files now include the `.html` suffix for category and product URLs.
        *   Customers can use advanced search on your web store if Magento EE is configured to use the default MySQL Fulltext search engine and the server uses MySQL 5.6.
        *   A role-restricted user can preview a newsletter in the Admin Panel to which the user has privileges.
        *   After synchronizing media files with the database, `media/customer/.htaccess` is present with the correct data. (Prerequisite: an administrator set **System** > **Configuration** > ADVANCED > **System** > **Storage Configuration for Media** set to **Database**).
        *   cron now restarts indexers if they previously failed to run.
        *   You can save changes to a category that has more than 1,000 products.
        *   Deactivating one of several banners no longer causes exceptions in `system.log`.
        *   Resolved issues with the WSDL cache.
        *   Improved the efficiency of product searches.
        *   Resolved issues with the DHL International shipping method.
        *   Resolved 404 (Not Found) errors in layered navigation.
        *   Resolved a SQL error when attempting to assign a bundled product to another website.
        *   Rules-based product relations perform as expected after being saved.
        *   Resolved an issue with sending duplicate `Content-Type` headers when using `mod_fastcgi` with the Apache web server.
        
        Open Source Software Licensing Agreements
        -----------------------------------------
        
        Some versions of Magento Open Source use open source software licensing. Following are license agreements for that software.
        
        **Touch punch**: This code is dual licensed under the MIT or GPL Version 2 licenses and is therefore free to use, modify and/or distribute, but if you include Touch Punch in other software packages or plugins, please include an attribution to the original software and a link to this [Touch Punch website](https://web.archive.org/web/20200513111617/http://touchpunch.furf.com/).