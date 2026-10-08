## Version 8.8.0 – Released: October 7th, 2026

[New Feature]
* Added support for FedEx Hold at Location on the WooCommerce Block Checkout (previously available on Classic Checkout only). Customers can now search for and select a FedEx pickup location directly from the Block Checkout page, with the shipping rate updating automatically for the selected location.
* Added a setting to customize the label shown above the Hold at Location field, available on both Classic and Block Checkout (defaults to "FedEx Hold at Location" when left blank).
* Added a "Leave a Review" reminder that appears on the WordPress Dashboard, Plugins page, and Orders page a few weeks after activation, inviting you to review the plugin on the PluginHive site.

[Improvement]
* Rate quote transients that never expired, left over from earlier versions with no cache expiry time set, are now removed automatically on update to improve site load time.
* The Date of Connection on the registration screen now shows in your site's timezone.
* Corrected missing and broken translations across plugin settings, admin notices, buttons, and order-page metaboxes for all supported languages, and hardened output handling on the My Account return-label page.
* Improved diagnostic logging for FedEx account registration to help identify and resolve connection issues faster.

[Bug Fix]
* Fixed label generation failing on WPML stores when an order was placed in a different checkout language and its packages were created automatically.
* Fixed re-registering a FedEx account showing as successful while the new account details were not saved in the plugin settings.
* Fixed a display issue where the Box Packing settings buttons could wrap onto a second line.
* Added a safeguard to prevent a rare fatal error that could occur if a plugin file was temporarily unavailable during a site update.

## Version 8.7.2 – Released: September 10th, 2026

[New Feature]
* Added a “Notify on Connection Lost” setting (under Advanced → Troubleshooting) for stores using a REST-connected FedEx account. It detects when the account’s connection stops authenticating — for example, when a token expires or is revoked — and emails the recipient configured under WooCommerce → Settings → Emails → FedEx Connection Lost, so the account can be reconnected right away instead of only finding out after FedEx services have already stopped working.
* Added automatic refreshing of the Effective Address on the Edit Order screen whenever the shipping address is changed and order is updated, so rates and services are calculated against the updated effective address rather than the one recorded at order placement.
* Added a “Show only for FedEx methods” setting under Hold at Location (visible only when Hold at Location is enabled) so the Hold at Location option no longer appears for non-FedEx shipping methods at Classic Checkout.

[Improvement]
* The diagnostic report sent with a support ticket now includes all FedEx log files, not just the debug log, so support has full context without needing to request additional logs separately.

[Bug Fix]
* Fixed an issue where stale Effective Address data could remain in the checkout session after the shipping address no longer qualified for validation, which could cause incorrect rates to be shown and, in some cases, the wrong address to be used when generating shipping labels.
* Fixed a fatal error during shipping rate calculation that could occur when another active plugin recalculated cart totals before the FedEx plugin had fully initialized.
* Fixed an issue where the plugin’s custom shipping fields on the product edit page could be hidden when WooCommerce Subscriptions was active.

## Version 8.7.1 – Released: August 6th, 2026

[New Feature]
* Added support for FedEx's new Extra Small Box packaging option, including eligibility for FedEx One Rate flat-rate pricing.

[Bug Fix]
* Fixed PHP warnings and broken page redirects that occurred when Hold at Location was enabled without completing FedEx account registration.
* Fixed a layout issue in the FedEx Shipment Tracking box on the Order Edit page caused by a recent WooCommerce update.
* Fixed international shipments from Puerto Rico or US Virgin Islands origin stores being rejected by FedEx for missing export compliance information.

[Compatibility]
* Confirmed compatibility with PHP 8.4.
* Confirmed compatibility with WooCommerce 11.0.

## Version 8.7.0 – Released: July 23rd, 2026

[New Feature]
* Added a Customs Duties Payer option on the Edit Order page for international shipments — choose Sender, Recipient, or Third Party for a single order without changing your store-wide setting.
* Added integration with the WooCommerce PayPal Payments plugin to automatically share FedEx tracking details with PayPal.

[Improvement]
* Added an Integrations tab in the FedEx settings to manage third-party plugin integrations.
* Added input validation and sanitization for customer-entered address fields sent to FedEx (rate quotes, address validation, labels, and Hold at Location).
* Added a filter "ph_fedex_preserve_dimension_order" that lets merchants keep their product's exact dimension order (instead of the default largest-to-smallest sorting) when generating rates and labels.

[Bug Fix]
* Fixed a duplicate confirmation message that appeared when saving WordPress settings pages while the FedEx plugin was active.

## Version 8.6.2 – Released: July 11th, 2026

[Improvement]
* Added an automatic one-time cleanup that fixes products with a Dangerous Goods Type of Hazardous Materials or Battery that were left with an incorrect Accessibility setting, so they can ship without being rejected by FedEx.

## Version 8.6.1 – Released: July 7th, 2026

[New Feature]
* Added support for new regulatory compliance requirements when shipping with FedEx — CPSC (US Consumer Product Safety Commission) and EU De Minimis (European Union).
* Added a new setting where you can choose which regulatory compliance codes apply to your store, on the International Forms tab.
* Added new product fields (for both simple products and product variations) to enter product identification details, which only appear once a compliance code is selected.
* Shipments to the US will now automatically include the CPSC compliance information; shipments to EU countries will automatically include the EU De Minimis information; other destinations are unaffected.

## Version 8.6.0 – Released: June 30th, 2026

[New Feature]
* Added support for Dangerous Goods and Hazardous Materials shipments with FedEx RESTful APIs.
* Added support for Excepted Quantities and Biological Substances Category B shipments with FedEx RESTful APIs.
* Added FedEx Ground Hazmat Close Out – OP-950 and Manifest document generation for eligible Ground hazmat orders, with a dedicated admin page to view and download close-out documents.
* Added Standalone Battery option on the product settings page for battery-type dangerous goods shipments.
* Added Dangerous Goods Additional Handling option – available as a global setting and as a per-order override on the Edit Order page for orders containing hazmat products.
* Added support for Dangerous Goods Shipper's Declaration document.

[Improvement]
* Broker Select Option settings for Customs Duties separated into dedicated fields for easier configuration.
* Enforced 0.1 as the minimum package weight across all packing methods.

## Version 8.5.0 – Released: June 18th, 2026

[New Feature]
* FedEx One Rate can now be enabled or disabled per order from the Edit Order page, letting you override the global One Rate setting for a single US domestic shipment packed in a FedEx Standard Box, for both rate calculation and label creation.
* Introduced Box Selection on the Order Edit page: change the FedEx box for any package before shipping, with the selection applied to both rate calculation and label creation.

## Version 8.4.0 – Released: June 10th, 2026

[New Feature]
* Set Purpose of Shipment, Comments, and Special Instructions per order from the order page — overriding the global Commercial Invoice defaults for international shipments
* Importer of Record for international shipments: send a dedicated importer of record to FedEx, either a fixed global importer or the customer's billing address, for smoother business-customer customs clearance
* Customer Tax ID (VAT / EORI / TIN) collection at checkout (Classic & Block) — sent to FedEx as the Consignee and SOLD TO Tax ID, with SOLD TO now using the customer's billing Tax ID

[Improvement]
* Relocated the 'Use Order Currency for Commercial Invoice' option to the Advanced settings tab and extended its functionality with a per-order override on the edit order page, giving merchants granular control over declared value currency on a per-shipment basis

[Bug Fix]
* SOLD TO Tax ID mismatch — SOLD TO (billing) party now sends the customer's billing Tax ID, not the shipper's global TIN
* Fixed incorrect currency conversion rounding that caused declared value to exceed customs value, resulting in failed shipping rate and label generation requests.

## Version 8.3.2 – Released: June 4th, 2026

[Bug Fix]
* Network Super Admins on WordPress Multisite can now perform all shipment related actions on WooCommerce subsites without any issues.

[Improvement]
* Express pickup date now automatically advances to the next working day when the scheduled ready time has already passed, preventing pickup request failures.
* Registration details are now stored independently, ensuring they are always preserved even when a stale settings page is saved after registration is completed in another tab.

## Version 8.3.1 – Released: May 21st, 2026

[Improvement]
* Hardened to meet Wordfence security scan standards, ensuring uninterrupted printing of shipping labels, return labels, and commercial invoices across all order types.

## Version 8.3.0 – Released: May 19th, 2026

[New Feature]
* Duties & Taxes rate calculation now supported in the FedEx REST integration, bringing it to parity with the legacy SOAP integration.

[Improvement]
* Improved keyboard accessibility on the order edit page. The "+Add Package" and "Start Tracking" buttons can now be reached and activated using the Tab, Enter, and Space keys.
* Upgraded the internal PDF library for bulk label and commercial invoice printing. Faster and more reliable generation.
* Improved compatibility with WooCommerce Product Bundles, supporting a wider range of bundle configurations.

[Bug Fix]
* Label generation now shows a clear admin notice when an order contains a deleted product, instead of failing silently.
* Exclude Tax setting was not being respected in Price Value modes, causing tax to be included in the FedEx declared/insured value and shipments to be rejected by FedEx.
* FedEx Ground Economy (SmartPost) rates were incorrectly appearing for multi-package shipments at checkout via the REST integration.
* ETD is now automatically skipped for UK domestic shipments when enabled globally, fixing label generation failures.
* Customer Reference Type and Value fields on the Edit Order page were resetting to global settings after a failed label attempt, causing cleared selections to be sent to FedEx instead of being treated as no reference.

## Version 8.2.5 – Released: Apr 29th, 2026

[Improvement]
* Added token support for the Customer Reference Value field — use {order_number} or {order_id} to dynamically populate the reference value on shipment creation. Default value set to {order_number}.

[Bug Fix]
* Shipment tracking now correctly uses the FedEx Track by Tracking Number endpoint for all shipments, resolving tracking failures on single-piece shipments.

## Version 8.2.4 – Released: Apr 15th, 2026

[Improvement]
* Set the company name character limit to 35 characters to avoid label failure
* Replaced transient-based storage with wp_options for auth token and internal endpoints. Caching plugins like Object Cache Pro, Redis and others were serving stale data, causing intermittent Unauthorized errors. This ensures consistent data across all caching setups
* Compatibility for FedEx REST with WooCommerce Multi Warehouse Shipping with FedEx in v1.3.8

[Bug Fix]
* Bulk and automatic label generation will now populate INV (invoice number) and REF (customer reference number) fields in shipping label

## Version 8.2.3 – Released: Mar 27th, 2026

[Improvement]
* Compatibility for PHP v7.4 on handling transient data by replacing usage of the match() function with the switch() function

## Version 8.2.2- Released: Mar 26th, 2026

[New Feature]
* Added a setting to allow merchants to display guaranteed or non-guaranteed FedEx Freight services at checkout.
* Added support for FedEx Freight Bill-to-Account, allowing freight charges to be billed to a specified FedEx account.

[Improvement]
* UK to UK shipments are now processed with customs details to support shipping labels.
* The plugin now gives an option to switch from or to FedEx Comprehensive Rates based on the "Best Shipping Rates" setting.
* Enhanced bearer token retrieval and management to ensure stable and efficient API authentication with FedEx, particularly for environments with object caching enabled.
* Improved transient caching behaviour to ensure compatibility and consistent performance on sites with object caching enabled.

[Bug Fix]
* Resolved a fatal error during plugin update checks by adding robust validation to safely handle empty or unexpected API responses from the update server.

## Version 8.2.1- Released: Mar 5th, 2026

[Improvement]
* Removed passing of residential value under recipient details when Freight Direct is enabled
* Implemented transient-based caching for the license pages

[Bug Fix]
* Fixed International Priority service not being considered with auto label generation when either origin or destination country is Puerto Rico

## Version 8.2.0- Released: Feb 20th, 2026

[Improvement]
* FedEx Address Validation is now used for shipping cost calculations & label printing.
* The plugin now enables shipping rates and defaults it to the FedEx Account Rates on fresh installation.

[Bug Fix]
* Edits made to the package during label generation are now preserved in case of any API failures.

## Version 8.1.9- Released: Feb 2nd, 2026

[Improvement]
* Support for Fedex Freight Priority and Fedex Freight Economy services with Freight Direct.

## Version 8.1.8- Released: Jan 21st, 2026

[Improvement]
* Added account number field for the international ground pickup request via REST API.
* Removed encoding of document upload via REST API.

[Bug Fix]
* Fixed Ajax Add to Cart button loading indefinitely.

## Version 8.1.7- Released: Jan 17th, 2026

[Improvement]
* Included Freight Direct data for freight rate fetching.
* Privilege restriction notice is now shown only within wp-admin pages.

## Version 8.1.6- Released: Dec 30th, 2025

[New Feature]
* Automatically Optimize Packaging for Best Shipping Rates.

[Bug Fix]
* For USMCA Certificate of Origin the Origin Criterion is now set to "Criterion A" by default.

## Version 8.1.5- Released: Dec 9th, 2025

[Bug Fix]
* Fixed REST API handling to ensure correct display of Saturday Delivery services based on merchant settings.

## Version 8.1.4- Released: Nov 21st, 2025

[Improvement]
* Support for printing additional documents like USMCA, Pro Forma Invoice, NAFTA, etc. for ETD shipments.
* Temporarily suspended Accessibility Type option for hazmat products with FedEx Express Freight
* Introduced region-based services list within the plugin settings for different shipping zones

## Version 8.1.3- Released: Oct 30th, 2025

[New Feature]
* Added Origin Criterion field (For USMCA certificate) for WooCommerce products.
* Added Accessibility Type for Hazardous Materials for WooCommerce products.

[Improvement]
* Support for Custom Description, Origin Criterion, Accessibility Type for Hazardous Materials at WooCommerce product variation level.

## Version 8.1.2- Released: Oct 11th, 2025

[Improvement]
* Added compatibility for new PH Shipping Class-Based Packing for FedEx add-on.

## Version 8.1.1- Released: Oct 11th, 2025

[Bug Fix]
* FedEx Standard Boxes not being identified when a product is packed in them.

## Version 8.1.0 – Released: Sep 30th, 2025

[New Feature]
* Added FedEx Shipping Rates under WooCommerce Shipping Zones.

[Improvement]
* Enhanced WordPress Security Configuration Compliance.

## Version 8.0.2 – Released: Aug 13th, 2025

[Improvement]
* Added support for uploading documents to orders saved in both HPOS and WP Post tables via REST API
* Compatibility with PH Delivery Date Picker for FedEx Add-on

## Version 8.0.1 – Released: Aug 4th, 2025

[Improvement]
* Address Validation for RESTful API.

## Version 8.0.0 – Released: July 29th, 2025

[New Feature]
* Introduced RESTful API integration (Beta release).
* Enabled switching between SOAP and REST connections via the revamped registration page.
* Added new REST-specific setting: Customer Reference Type.
* Added new REST-specific setting: Customer Reference Value.
* Added new REST-specific setting: Block Insight Visibility.
* Enabled document uploads (pre- and post-shipment) for international orders using REST connection.

[Improvement]
* Compatibility with WooCommerce v10.0.4.
* Compatibility with WordPress v6.8.2.
* Compatibility with FOX – Currency Switcher Professional for WooCommerce v1.4.3.1.
* Enhanced validation checks across all plugin settings.
* Renamed "FedEx SmartPost" to "FedEx Ground® Economy" to reflect updated FedEx terminology.
* Introduced an "Extensions" section highlighting supported and complementary plugins.
* Added quick-access banner on the settings page linking to helpful resources.
* Redesigned action icons to improve clarity on the WooCommerce Orders page.

[Requirement]
* Requires WooCommerce v8.6.2 or higher.

[Deprecated]
* C.O.D. Feature (deprecated by FedEx).

## Version 7.1.8 – Released: May 14th, 2025

[Improvement]
* Compatibility with WooCommerce v.9.8.5.
* Compatibility with WordPress v.6.8.1.
* Improved the process for Plugin License Activation.

## Version 7.1.7 – Released: April 14th, 2025

[Improvement]
* Packages will revert to Your Packaging from FedEx Standard Boxes while generating labels for FedEx Ground shipments.
* Restricted sending Commodity Details for only FedEx international shipments.
* Live FedEx rates disabled while handling pre-packed products with missing weight and dimensions.
* Improved compatibility with WooCommerce Multilingual & Multi currency plugin by WPML.

## Version 7.1.6 – Released: Mar 12th, 2025

[New Feature]
* Added option to enable/disable Cleanup shipment details functionality.

[Bug Fix]
* Fixed shipment creation when the Exclude Tax option is enabled.

## Version 7.1.5 – Released: Feb 12th, 2025

[New Feature]
* Max Quantity Limit for FedEx Standard Boxes & Boxes with Custom Weight and Dimensions.

## Version 7.1.4 – Released: Feb 7th, 2025

[New Feature]
* FedEx Priority Express and FedEx Priority services for Chile.
* New Hold at Location type: FedEx Authorised Ship Center.

[Improvement]
* Label Printing for shipments from the US to Ireland.
* Standardised minimum shipment weight for shipping as 0.01 lbs AND 0.01 kgs.
* Deprecated COD option for shipments within and to US.
* Total Insured Value now displays in the Commercial Invoice.
* Standardised insurance value for FedEx Ground® Economy service as $100.

[Bug Fix]
* Fixed UI when 'Advanced Shipment Tracking for WooCommerce' is activated.

## Version 7.1.3 – Released: Nov 21st, 2024

[New Feature]
* Added Cleanup FedEx Shipment Details functionality.

[Improvement]
* Added hook to get estimate delivery date 'ph_fedex_get_estimate_delivery_for_order'.
* Compatibility with the Kadence WooCommerce Email Designer Plugin.

## Version 7.1.2 – Released: Oct 17th, 2024

[New Feature]
* Added support for FedEx Ground rate and FedEx Express One Rate together at cart, checkout and edit order page

[Improvement]
* Added Order Number and Order ID tag in the email subject.
* Added Purpose of Shipment for US-based shipments.
* Added custom scaling option for displaying labels in the browser with PNG format.
* Improved flow for Shipper's Email ID in case of the Return Shipment.
* Added support for handling special character in the shipper's address.

[Bug Fix]
* Case related to Extreme Length and Over Length.
* Fixed Default Recipient Phone Number.

## Version 7.1.1 – Released: Sep 16th, 2024

[Improvement]
* Added a configurable cache expiration limit for shipping rates to improve performance with cached rates

[Bug Fix]
* Saving Hold at Location address in order meta field
* Calculate insurance based on discounted product prices with tax

## Version 7.1.0 – Released: Aug 22nd, 2024

[Improvement]
* Support for Liability Coverage Type options for FedEx Freight shipments
* Support for customizing events to send Tracking Email Notifications by FedEx

## Version 7.0.9 – Released: July 17th, 2024

[New Feature]
* Introduced the "Country of Manufacture" field at the product variation level
* "Non-Stackable" option supported for FedEx Freight
* Estimated delivery date feature for WooCommerce Blocks cart and checkout page

[Improvement]
* Improved the migration process for HPOS
* Removed unsupported data masking on shipping labels
* License expiration notification added

## Version 7.0.8- Released: July 10th, 2024

[Bug Fix]
* Case related FedEx Account registration with renewed license keys

## Version 7.0.7- Released: June 14th, 2024

[New Feature]
* Added FedEx Freight Direct option

[Improvement]
* Updated Currency Units for South Korean Won and New Taiwan Dollar

## Version 7.0.6- Released: April 24th, 2024

[New Feature]
* Added Compatible with Jersey: Ship to Jersey hassle-free with our latest plugin update

## Version 7.0.5- Released: April 12th, 2024

[New Feature]
* Added new services for Switzerland.

[Bug Fix]
* Fixed Rate & Label Issue for Renewed Plugin License Keys.

## Version 7.0.4- Released: March 15th, 2024

[New Feature]
* Added EXTREME_LENGTH check for freight shipments.
* Added State mapper for pickup for Canada and Mexico countries.
* Added New Services for UK and EU Countries.

## Version 7.0.3- Released: Feb 15th, 2024

[Bug Fix]
* Send Shipping Label to Vendors via Email.

## Version 7.0.2- Released: Feb 8th, 2024

[Improvement]
* Box Packing Compatibility with Freight Shipments.
* Setting Carrier to "None" in FedEx Tracking Window now saves tracking numbers.

## Version 7.0.1- Released: Feb 2nd, 2024

[Bug Fix]
* Fixed Package Details (weight & dimensions) and Tracking Details getting saved inaccurately while editing orders manually.

## Version 7.0.0- Released: Jan 24th, 2024

[New Feature]
* Compatibility with WooCommerce High-performance order storage (HPOS).

## Version 6.1.0- Released: Jan 3rd, 2024

[Improvement]
* Compatibility with PHP 8.2.
* Added "Encode Uploaded Document" option for commercial invoice signature and company logo.

[Bug Fix]
* Accurately display the Total Invoice Value on the AWB label.

## Version 6.0.9 – Released: Dec 15th, 2023

[Improvement]
* Compatibility with WooCommerce 8.4.0

## Version 6.0.8 – Released: Dec 4th, 2023

[Improvement]
* Support for FedEx® Priority and FedEx® Priority Express for European and AMEA regions.
* Support for FedEx® Regional Economy and FedEx® Regional Economy Freight for AMEA region.

## Version 6.0.7 – Released: Nov 13th, 2023

[Bug Fix]
* Resolved authentication failure occurring during image uploads.

## Version 6.0.6 – Released: Nov 6th, 2023

[Improvement]
* Added Minimum Order Amount option for Insurance.

## Version 6.0.5 – Released: Oct 25th, 2023

[Improvement]
* Added pickup date to order table.

## Version 6.0.4 – Released: Sept 7th, 2023

[Improvement]
* Support for FedEx Ground Economy rates for single package.
* Support for FedEx Ground Economy label generation for multi-piece shipments.

## Version 6.0.3 – Released: July 27th, 2023

[New Feature]
* Added Custom Declared Value for product variations.

## Version 6.0.2 – Released: July 20th, 2023

[New Feature]
* Support for Commercial Invoice on Return Shipments.
* Support for Customs Declaration Statement on the Commercial Invoice for Non-US shippers

## Version 6.0.1 – Released: July 4th, 2023

[New Feature]
* Option to re-register FedEx Account
* Added new service Regional Economy Freight for EU Countries.

[Improvement]
* Added support for API History Table.
* Support for special characters.
* Added Booking Confirmation Number to support INTERNATIONAL ECONOMY FREIGHT and INTERNATIONAL PRIORITY FREIGHT labels.

[Bug Fix]
* Label Generation for FedEx Ground Home Delivery.

## Version 6.0.0 – Released: June 12th, 2023

[New Feature]
* FedEx Compatible Solution: Seamless FedEx Account Integration.
* Migration to FedEx RESTful APIs.

## Version 5.2.6 – Released: May 16th, 2023

[Bug Fix]
* Fixed issue with Bulk Action options not loading in Italian Language Translation.
* Fixed Select Service not selecting default or customer-selected services for manual packages.

## Version 5.2.5 – Released: Apr 27th, 2023

[Improvement]
* Updated Compatibility with Nu-soap Method.

## Version 5.2.4 – Released: Apr 18th, 2023

[Bug Fix]
* Case related to image upload on use of NUSOAP.
* Fixed rounding-up issue for package weight.

## Version 5.2.3 – Released: March 30th, 2023

[Improvement]
* Display HAL at checkout based on "Method Available" Countries

[Bug Fix]
* Fixed Freight rates not returned for Hazardous Products

## Version 5.2.2- Released: March 22nd, 2023

[Bug Fix]
* Case related to product weight round-off before package generation.

## Version 5.2.1- Released: March 7th, 2023

[Improvement]
* Added FedEx Ground services option under Default Service for International Shipment
* Translation support for German, French, Spanish, and Italian

## Version 5.2.0- Released: Feb 7th, 2023

[Improvement]
* Support for Saturday delivery with FedEx one rate.
* Return label will be sent through email upon generation.

## Version 5.1.9 – Released: Jan 13th, 2023

[Improvement]
* Added HS Tariff Number option for product variation
* Improved Stack First Packing Method

## Version 5.1.8 – Released: Dec 23rd, 2022

[Improvement]
* Enhanced pickup request for International Ground Services.

## Version 5.1.7 – Released: Dec 15th, 2022

[Improvement]
* FTR Exemption or AES Citation support for Hongkong, Belgium, China, France and Virgin Islands.

## Version 5.1.6 – Released: Dec 9th, 2022

[New Feature]
* Support for auto-printing ZPL shipping labels via Email

[Improvement]
* Third-party shipping for multiple warehouses
* Support for Unassembled Composite Products

[Bug Fix]
* Fixed – Box name displayed incorrectly on Edit Order Page

## Version 5.1.5 – Released: Nov 29th, 2022

[Improvement]
* Added option under plugin settings to add Default Recipient Phone number

## Version 5.1.4 – Released: Nov 4th, 2022

[Bug Fix]
* PHP warning on a fresh install.

## Version 5.1.3 – Released: Oct 21st, 2022

[New Feature]
* Added Option to skip Product from Rate and Label.
* Added Small Quantity Exception DG Type in Edit Product page under FedEx Shipping Details
* Changed Special Service select option to Alcohol Check box in Edit Product under FedEx Shipping Details
* Added Skipping Signature Option for Freight Services

## Version 5.1.2 – Released: Oct 14th, 2022

[Improvement]
* Support for HAZARDOUS_MATERIALS in Freight shipment.
* FEDEX_REGIONAL_ECONOMY support for Poland origin.
* Added Order Id in the diagnostic report.

## Version 5.1.1 – Released: September 26th, 2022

[Bug Fix]
* Case related to saving Print Label Size data in the plugin settings page.
* Case related to saving dangerous goods details under product level.

## Version 5.1.0 – Released: September 2nd, 2022

[New Feature]
* Added Stack First Packing Algorithm.

[Bug Fix]
* Case related to Dangerous Goods data passing in the label request for non-DG products.

## Version 5.0.9 – Released: August 25th, 2022

[Improvement]
* Added option under plugin settings to send shipping notifications to both Shipper and Recipient.

## Version 5.0.8 – Released: August 22nd, 2022

[New Feature]
* Added option under plugin settings to set up Hold At Location Attributes.
* Added functionality to reset boxes.

[Improvement]
* Label Size filter based on selected Image Type.

## Version 5.0.7 – Released: August 4th, 2022

[Improvement]
* Conversion of box weight and dimension based on plugin Dimension/Weight Unit settings.
* Added support for FEDEX_REGIONAL_ECONOMY service.
* Added filter hook to modify button name and button tooltips on the edit order page.

## Version 5.0.6 – Released: June 28th, 2022

[Bug Fix]
* Case related to FedEx standard boxes for non-US shipments.

[Improvement]
* Added Terms Of Sale option under plugin settings and in order level.

## Version 5.0.5 – Released: June 8th, 2022

[Improvement]
* Freight Class under plugin settings is made compatible with PHP 8.

## Version 5.0.4 – Released: Apr 13th, 2022

[Improvement]
* Added 'INTERNATIONAL_PRIORITY' service for shipments with Puerto Rico as Origin Country.

## Version 5.0.3 – Released: Apr 8th, 2022

[New Feature]
* Added 'INTERNATIONAL_PRIORITY' service for shipments with Puerto Rico as Destination Country.

## Version 5.0.2 – Released: March 25th, 2022

[Improvement]
* Pickup will be requested for the next working day once the current time crosses the Pickup Start time.

## Version 5.0.1 – Released: March 18th, 2022

[New Feature]
* Added Bulk Print Option for Commercial Invoice

## Version 5.0.0 – Released: March 9th, 2022

[Improvement]
* Deprecated FedEx "INTERNATIONAL_PRIORITY" service

[Bug Fix]
* Case related to <html> and <body> tags getting omitted from Email Format settings
* Case related to FedEx Live Tracking URL

## Version 4.9.9 – Released: March 2nd, 2022

[Improvement]
* Added support for shipments containing Batteries
* Updates Dangerous Goods options – Limited Quantity Commodities, Hazardous Materials, Battery, ORM-D

## Version 4.9.8 – Released: February 14th, 2022

[Improvement]
* Introduced PDF option to Bulk Print Shipping Labels

[Bug Fix]
* Case related to Hold at Location option not displayed on Checkout & Edit Order Page

## Version 4.9.7 – Released: January 7th, 2022

[Improvement]
* Introduced Packaging algorithm "Based on Volume Used * Item Count"
* Introduced Special service – "Third Party Consignee"
* Option to hide shipper information from shipping label

## Version 4.9.6 – Released: Dec 31st, 2021

[Improvement]
* Added new services "FedEx International Priority® Express" and "FedEx International Priority®" for EU & AMEA countries
* Added new address fields for Alternate Return Address
* Added support for Special service – 'Alcohol' in Rate Request

[Bug Fix]
* Case related to FedExOneRate in case of Return Shipment

## Version 4.9.5 – Released: Dec 9th, 2021

[Bug Fix]
* Case related to calculation of shipping rates in edit order page with "Hold at Location" enabled

## Version 4.9.4 – Released: Nov 26th, 2021

[New Feature]
* Feature to show real-time tracking updates to the store owner
* Introduced a new service "FedEx International Connect Plus"

[Bug Fix]
* Case related to the generation of multiple labels for a single order with ETD
* Handled the case related to Shipping time adjustment and Cut off time

## Version 4.9.3 – Released: Nov 10th, 2021

[Bug Fix]
* Shipping labels will be sent as an attachment in the Email for "Send Shipping Label To" option
* Critical error when accessing the plugin settings page

## Version 4.9.2 – Released: Oct 26th, 2021

[Improvement]
* Saturday Delivery support for shipments requested on Thursday

## Version 4.9.1 – Released: Sept 23rd, 2021

[Bug Fix]
* Redirecting to Page not Found when clicking on Calculate Cost option on Edit Order Page

## Version 4.9.0 – Released: Sept 3rd, 2021

[Bug Fix]
* Issue related to Bulk Label Generation
* Updated FedEx Shipment Tracking URL

## Version 4.8.9 – Released: Aug 26th, 2021

[New Feature]
* Introduced Home Delivery Premium services
* Introduced "USMCA Commercial Invoice Certificate Of Origin"

[Improvement]
* Option to hide shipping data on the label
* Compatibility with Print Invoice and Delivery Notes plugin

[Bug Fix]
* Issue related to SmartPost hub

## Version 4.8.8 – Released: Aug 9th, 2021

[Improvement]
* Compatibility with PHP v.8

## Version 4.8.7 – Released: July 28th, 2021

[Improvement]
* Added Third-Party Option for Custom Duties Payer
* Option to include "Document Content" Type for International Shipments
* Option to add 'Comments' for Commercial Invoice
* UI Improvements – Plugin Settings Page

## Version 4.8.6 – Released: July 21st, 2021

[Improvement]
* Hidden 'FedEx Hold at Location' option at checkout for Virtual products
* Added FedEx Tracking under Actions Column in WooCommerce Orders Page
* Option to edit number of packages for cost calculation in Order edit Page
* Included signature option for cost calculation in edit order page

## Version 4.8.5 – Released: June 30th, 2021

[Bug Fix]
* Fixed Delivery Signature Issue in case of Bulk Label and Vendor Label Generation

## Version 4.8.4 – Released: June 17th, 2021

[Improvement]
* Added Box Names for packages in Edit Order Page
* Added New HAL Location : FedEx_OnSite

[Bug Fix]
* Fixed: Signature not reflecting for Bulk and Auto Label Generation

## Version 4.8.3 – Released: June 11th, 2021

[New Feature]
* Compatibility with WooCommerce Composite Products

[Improvement]
* Improved Hold At Location (HAL is requested based on the service selected in plugin settings)

[Bug Fix]
* Return Shipment compatibility with latest WSDL for orders whose Forward shipment is created using older WSDLs

## Version 4.8.2 – Released: June 1st, 2021

[New Feature]
* Implemented Option to generate Pro Forma Invoice
* Saturday Delivery support for Automatic Label and Bulk Label Generation

[Improvement]
* Added Option Trigger Automatic Label Generation when- Payment is Confirmed/Order is placed successfully

[Bug Fix]
* Customs Value will default to ProductPrice when the Declared value field is not configured in the Edit Product Page

## Version 4.8.1 – Released: May 24th, 2021

[New Feature]
* Added Option to select Shipping Quote Type

## Version 4.8.0 – Released: May 11th, 2021

[New Feature]
* Added Signature Option at Product Level (Both Simple and Variable Products)
* Added Option to select Signature at Edit Order Page before Label Creation

[Improvement]
* Added Export Details for Canadian Return Shipments

[Bug Fix]
* Fixed Bulk Label Printing Error
* Fixed conflict of FedEx One Rates with Hold at Location

## Version 4.7.9 – Released: April 29th, 2021

[New Feature]
* Option to generate United States-Mexico-Canada Agreement(USMCA) certificate

[Improvement]
* Integrated with latest FedEx API — Following WSDL file updates:
WSDL: Rates 31, Shipping 28, Pickup 23, Location 12, Address Validation 4, Upload Document Service 19

## Version 4.7.8 – Released: April 16th, 2021

[Improvement]
* Option to display labels in browser for individual orders (Applicable only for PNG Labels)
* Introduced ETD option on Edit Order Page

## Version 4.7.7 – Released: April 14th, 2021

[Improvement]
* Now select whether you want to display the discounted price, original product price, or the declared value to be printed on the commercial invoice

## Version 4.7.6 – Released: April 06th, 2021

[Improvement]
* FedEx Freight shipping rate calculation for different freight classes

## Version 4.7.5 – Released: March 15th, 2021

[Improvement]
* Clear shipping label data from WooCommerce orders after voiding shipment
* Improved shipping for orders containing multiple packages
* FedEx Standard Box support for Brazil

[Bug Fix]
* Rounded minimum package dimensions to 1

## Version 4.7.4 – Released: March 05th, 2021

[Improvement]
* FedEx Ground shipping service for Canada to US shipments
* FedEx 25 Kg and 10 Kg box for international FedEx shipments

[Bug Fix]
* Automatically printing shipping labels by clicking in Generate Packages option

## Version 4.7.3 – Released: February 26th, 2021

[Improvement]
* Packing for prepacked & normal packages together while using Weight based Parcel Packing method

## Version 4.7.2 – Released: February 15th, 2021

[Improvement]
* HS Tariff Code supported for product variations while calculating shipping rates

## Version 4.7.1 – Released: December 22nd, 2020

[Improvement]
* Calculate shipping rates based on weight-based packaging
* Enable or disable all the FedEx shipping services with one click

## Version 4.7.0 – Released: December 10th, 2020

[New Feature]
* Added support for CSB-V Shipments for India

## Version 4.6.9 – Released: November 28th, 2020

[Improvement]
* Option to specify payment terms for FedEx commercial invoice
* Generate package & shipping labels for products without weight & dimensions for domestic orders
* FedEx rates can be calculated for a manually generated package from the WooCommerce orders page
* Added settings related to the commercial invoice under Commercial Invoice Tab in plugin settings

## Version 4.6.8 – Released: November 13th, 2020

[Improvement]
* Added option for Working days(Applicable for rates, labels, and pickups)
* Added option for Special Instructions
* Discontinued Saturday Pickup option(will be handled using "Working days" option)

[Bug Fix]
* FedEx Standard Box related issue for Columbia

## Version 4.6.7 – Released: October 26th, 2020

[Improvement]
* Special characters are now supported in Name, City, and Address Fields

[Bug Fix]
* Commercial invoice contains package details

## Version 4.6.6 – Released: October 10th, 2020

[Improvement]
* Display of Shipping phone number in FedEx labels

## Version 4.6.5 – Released: September 16th, 2020

[Improvement]
* Freight shipping rate calculations
* Shipping labels can now be printed in bulk with a custom scaling option

## Version 4.6.4 – Released: September 04th, 2020

[Improvement]
* Improved WooCommerce [4.4.1] Compatibility
* Improved compatibility with WooCommerce Checkout Addons plugin

## Version 4.6.3 – Released: August 07th, 2020

[Improvement]
* Improved compatibility issue with Flexible Shipping Pro plugin

## Version 4.6.2 – Released: July 22nd, 2020

[Bug Fix]
* Freight shipping rates when multiple quantities of a product are added to the cart/checkout page

## Version 4.6.1 – Released: July 17th, 2020

[Improvement]
* Updated Shipping Rates WSDL Version
* Added all Freight Line Item Freight Class to the shipping rates request
* Added Special Service OVER LENGTH when Freight Product Dimension crosses 96 inches
* Added support for Freight Shipping Label Generation in case of multiple packages
* Added support for shipping rate calculation for Freight and Saturday Delivery in Admin Edit Order page

## Version 4.6.0 – Released: July 09th, 2020

[Improvement]
* Compatibility update for PH HS Codes based on Destination Countries add-on

## Version 4.5.9 – Released: July 05th, 2020

[New Feature]
* Added option to set HS Tariff Code for all the products at a global level

[Improvement]
* Added option to get Saturday Delivery shipping rates
* Added option to enable Doc Tab Content for shipping label in ZPLII format
* Added option to specify Cut-off Time for displaying shipping rates at cart and checkout page

## Version 4.5.8 – Released: June 19th, 2020

[Improvement]
* Added Product Freight Class in rate and shipment requests in all packing algorithms
* Improved compatibility with WooCommerce Ship to Multiple Addresses plugin

[Bug Fix]
* Fixed the number of units printed on the commercial invoice in case extra packages are added manually

## Version 4.5.7 – Released: June 05th, 2020

[Improvement]
* Improved compatibility with PluginHive's WooCommerce Shipment Tracking Pro
* Added option to disable tracking details to customer in My Account Order View and Order Completion Email

## Version 4.5.6 – Released: May 16th, 2020

[Improvement]
* Display of delivery estimate in DDMMYYYY format for FedEx Ground and Ground Home Delivery
* Optimised Shipping time adjustment calculation
* Logging of address validation details only when debug is enabled

[Bug Fix]
* Fixed automatic label generation flow improvement

## Version 4.5.5 – Released: April 09th, 2020

[New Feature]
* Added option to include ETD (Electronic Trade Documents) in Shipping Labels for International Shipments

[Improvement]
* Added Sender as the default Duties and Taxes Payer

[Bug Fix]
* Fixed the Customs Values for Rate Request with the Conversion Rate option

## Version 4.5.4 – Released: March 24th, 2020

[Improvement]
* Option to edit & update Hold At Location for each order
* Option to send Additional Labels (commercial invoice, cod labels, etc.) via email
* Improved compatibility with FOX Multi-Currency plugin (formerly knows as WOOCS Multi-Currency plugin) for AED, JYE, JED, KUD, DHS, SID, NMP, SFR, UKL, and ARN

## Version 4.5.3 – Released: February 28th, 2020

[Improvement]
* Improved Spanish Language Translation

## Version 4.5.2 – Released: February 14th, 2020

[Improvement]
* Added Help & Support Section for Improved User Experience
* Set Billing Address to the Alternate Return Address for the Undelivered Shipments
* Added Order Number as Invoice number for Commercial Invoice
* Support for 7-day delivery option in case of FedEx Home Delivery

## Version 4.5.1 – Released: January 18th, 2020

[Improvement]
* Added support for FedEx Tube and A4 Boxes

[Bug Fix]
* Fixed return label not getting generated when Customs Duties Payer set to Recipient
* Fixed the issue of Customs Value not being added correctly in Commercial Invoice

## Version 4.5.0 – Released: December 26th, 2019

[Improvement]
* Added option for editing FedEx default boxes.

## Version 4.4.9 – Released: December 05th, 2019

[New Feature]
* Set Fallback Rates for cases when FedEx does not return shipping rates
* Insurance/Declared Value will be rounded off

[Improvement]
* Support for Order Currency in Commercial Invoice using FOX Multi-Currency plugin (formerly knows as WOOCS Multi-Currency plugin)

## Version 4.4.8 – Released: November 13th, 2019

[New Feature]
* Add Alternative Return Address for Undelivered Shipments

[Improvement]
* Support for OP 900 Label for Hazardous Shipments
* Improved plugin update functionality

## Version 4.4.7 – Released: October 30th, 2019

[Improvement]
* Added Address Validation in Orders Page for Calculated Shipping Rates and Services

## Version 4.4.6 – Released: October 21st, 2019

[Improvement]
* Print FedEx Freight Shipping Label along with Bill of Lading document
* Option to select Freight Document Type as VICS Bill of Lading or FedEx Freight Straight Bill of Lading
* Generate Shipping Labels in three more sizes – PAPER_4x6.75, STOCK_4x6.75, and STOCK_4x9

[Bug Fix]
* Fixed COD Return not supported for Ground Shipments

## Version 4.4.5 – Released: October 18th, 2019

[Improvement]
* Handled tax computation and discounts with WooCommerce multiple address plugin.

## Version 4.4.4 – Released: October 17th, 2019

[Improvement]
* Optimised process of automatic label generation.

## Version 4.4.3 – Released: October 15th, 2019

[Improvement]
* Handled HS code mapping during label creation for Bundled products from WooCommerce Product Bundles.

## Version 4.4.2 – Released: October 13th, 2019

[Improvement]
* Handled Pre-Packed option for variable products when Multi-product Add-On is used.

## Version 4.4.1 – Released: October 11th, 2019

[Improvement]
* Handled rate discrepancy for 'Hold at location' feature at Payment Gateway page(Paypal page).

## Version 4.4.0 – Released: October 8th, 2019

[Improvement]
* Support for the commercial invoice with FOX Multi-Currency plugin (formerly knows as WOOCS Multi-Currency plugin)
* Introduced supports for variation products in commercial invoices.

## Version 4.3.9 – Released: October 1st, 2019

[Improvement]
* Introduced calculation of 'Unit Value' field in the commercial invoice for discounted products.

## Version 4.3.8 – Released: September 30th, 2019

[Improvement]
* Provided option to add shipping charges in the commercial invoice
* Enabled display of discounted prices in the commercial invoice for variable products.

## Version 4.3.7 – Released: September 29th, 2019

[Improvement]
* Provided feature of adding FedEx Address Suggestion to order notes
* Provided option to include discounted product price in the commercial invoice
* Included Shipping charges in the commercial invoice

[Bug Fix]
* Hold at Location endpoint changes for Production and Test environment.

## Version 4.3.6 – Released: September 25th, 2019

[Improvement]
* Display of FedEx Pickup Location (along with Pickup Number) in Order Listing Page
* Added 'Shipping Time Adjustment' feature for Ground Home delivery

## Version 4.3.5 – Released: September 14th, 2019

[Improvement]
* Introduced Drop off option in plugin settings which allows shipments to be dropped off at the FedEx office.
* Introduced Commodity description for domestic Pickups.

## Version 4.3.4 – Released: September 11th, 2019

[Improvement]
* Enabled Pickup for Ground and Freight shipments.
* Introduced FedEx Pickup number under FedEx Pickup Column in Order Listing page.

[Bug Fix]
* Rounded off Insurance amount to prevent mismatch of Insurance amount with customs value.
* Released Fix related to email notification.

## Version 4.3.3 – Released: August 26th, 2019

[Improvement]
* Option to include COD charges along with shipping charges at checkout.
* Option to include Estimated Duties & Taxes along with shipping charges at checkout.
* Simultaneous scheduling of Domestic and International Pickup for orders in bulk.

## Version 4.3.2 – Released: August 14th, 2019

[Improvement]
* Improved display of Shipping methods in 'Thank you' page(Compatibility with WooCommerce Multiple Address plugin).

[Bug Fix]
* Minor correction in manual package addition at orders page(create shipment).
* Fixed selection of shipping methods when a coupon is applied.

## Version 4.3.1 – Released: July 31st, 2019

[Improvement]
* Automatic and manual label generation compatibility with multiple shipping address plugin when multiple shipping service is selected.
* Unset COD for return shipments.

[Bug Fix]
* Introduced error handling for WooCommerce order packages.

## Version 4.3.0 – Released: July 22th, 2019

[Improvement]
* Improved Compatibility with WooCommerce Ship to Multiple Addresses Plugin

[Bug Fix]
* Case related to Hold at location handled.

## Version 4.2.9 – Released: July 12th, 2019

[Improvement]
* Changed Sunday pickup to Monday.

[Bug Fix]
* For Ground and Home delivery COD is made compatible
* Error Handling for insurance when the product price is not defined.

## Version 4.2.8 – Released: July 4th, 2019

[New Feature]
* Added Email Address to Commercial Invoice.

[Improvement]
* PHP older version compatibility.

## Version 4.2.7 – Released: July 1st, 2019

[New Feature]
* Added Customs Options Type (Reason for Return) for International Shipments
* Added Email Subject Feature for sending shipping label and added [CUSTOMER NAME], [CUSTOMER EMAIL] Tag Holders for Email Format

[Improvement]
* Support for Singapore Country without any city

## Version 4.2.6 – Released: June 14th, 2019

[Improvement]
* COD for Personal and Company check.

[Bug Fix]
* Case related to Bulk Printing of labels
* Case related to Saturday delivery

## Version 4.2.5 – Released: June 4th, 2019

[Improvement]
* Enhanced currency support for WooCommerce Multi-Currency.

## Version 4.2.4 – Released: May 30th, 2019

[Improvement]
* Added Toggle for FedEx options at the product level.
* Enhanced multiple currency support.

[Bug Fix]
* Fix for On-Hold location.

## Version 4.2.3 – Released: May 25th, 2019

[New Feature]
* Implemented B13 for Shipments from Canada.
* Implemented Option to remove special characters from FedEx request.

[Improvement]
* Hold at location updated if the customer selects the shipping address instead of the billing address.

## Version 4.2.2 – Released: May 18th, 2019

[Improvement]
* Improved Pre Packed algorithm for weight-based: Purely divided by weight.

[Bug Fix]
* One rate request modified for shipments from Canada.

## Version 4.2.1 – Released: Apr 26th, 2019

[Improvement]
* Added FedEx Standard Box Support for Canada
* UI Changes

[Bug Fix]
* Fixed Notices in Logs while generating FedEx Freight Labels

## Version 4.2.0 – Released: Apr 09th, 2019

[New Feature]
* Extensive Support for FedEx Hazmat Products

[Bug Fix]
* Special Characters support for Product Name
* Hold At Location Debug Details Visible at Cart Page
* Fixed conflict where FedEx Class Name has to be changed for Tracking
* Fixed Minor Notices

## Version 4.1.9 – Released: Mar 25th, 2019

[Bug Fix]
* 10kg & 25kg FedEx Box getting selected for Domestic (US) shipments
* Fixed Liftgate/Inside Delivery not working
* Fixed FedEx One Rates displaying for ineligible shipments

## Version 4.1.8 – Released: Mar 6th, 2019

[New Feature]
* Option to enable Saturday Pickup
* Added Maximum Shipping Cost

[Improvement]
* Box Packing UI changes
* Fixed Weight and Dimension Standard Units while adding a Custom Box
* Address validation for specific countries
* Compatibility with WooCommerce Currency Switcher plugin

[Bug Fix]
* Fixed Custom Value at Shipment Level conflict with Custom Value at the Commodity level
* Fixed Network Site Activation for FedEx plugin

## Version 4.1.7 – Released: Jan 4th, 2019

[New Feature]
* Added Debug XML Request and Response for FedEx Pickup
* Option to communicate with FedEx in a Currency different than the Store Currency
* FedEx Hold at Location is now supported
* Support for shipping from multiple address via third party plugin
* Option to set Dry Ice Weight in the Product page
* Option to Print Label & Custom Invoice From Order List Page

[Improvement]
* Various UI changes
* Improved Bundled Product Compatibility
* Debug Message related improvements
* Multiple Vendors (split cart) can now Print FedEx Labels with the selected FedEx Service (requires vendor addon 1.2.5)
* Automatically enable COD for all orders created via COD
* Display Rates for Only Enabled Services on Order Page
* Display Estimated Delivery Date on Order Page
* Introduced Email Content Modification

[Bug Fix]
* Handling Refunded Item
* License related message is now shown as notice, not error
* Estimated delivery date now works properly for FedEx Ground and Smart Post with adjustment

## Version 4.1.6 – Released: Sep 7th, 2018
License migration changes.

## Version 4.1.5 – Released: September 7th, 2018

[Improvement]
* Introduced display of COD tracking number on the individual order page.
* Renamed the following services: FedEx Economy Freight to FedEx International Economy Freight, and FedEx Priority Freight to FedEx International Priority Freight

## Version 4.1.4 – Released: August 30th, 2018

[New Feature]
* Provided option to set a minimum Shipping cost.

[Improvement]
* COD option is automatically selected for label generation if the payment method is chosen as 'COD'.
* Insurance will not display on the orders page when not enabled on the settings page.

[Bug Fix]
* Case related to notice in the console during manual package creation fixed.

## Version 4.1.3 – Released: August 9th, 2018

[New Feature]
* Provided option to remove pre-generated packages.
* Provided option for insurance amount on the Order page.
* Provided option to adjust shipment day for rate request, it will affect estimated delivery.
* Provided option to get the reason for return label on the customer Myaccount page before generating the return label, reason will reflect in the order note.

[Improvement]
* Handled weekend case in case of Estimated delivery for FedEx Ground.
* Debug has been refined.
* Handled the Conflict with DHL.

## Version 4.1.2 – Released: June 21, 2018

[New Feature]
* Option to hide FedEx meta box on the order page.

[Improvement]
* Added Vendor option in case of multi-vendor scenario to send the label to the vendor, if multi vendor addon active.

## Version 4.1.1 – Released: June 15, 2018

[New Feature]
* Bulk label generation and printing
* Option to send the label to the sender and receiver
* Volumetric weight option
* Liftgate pickup and Inside delivery pickup
* OP900 label generation, require addon and preprinted OP900 form

[Improvement]
* Made Compatible with WooCommerce 3.4.
* Woocommerce FedEx Integration with WooCommerce Mixed and Match Product plugin
* Prevent address validation if the complete address has not been provided
* Non-standard option at variation label
* Support for Japanese Yen currency

## Version 4.1.0 – Released: April 17, 2018

[New Feature]
* Option to provide item description in the settings page.
* Option to define custom email HTML for auto emailing the label.

[Improvement]
* Made compatible with WC older version (2.3)
* Error handling and writing into the log file, for SOAP and NUSOAP issues.

[Bug Fix]
* Case of custom value for international shipping
* Removed Price Adjustment from the order page.
* Corrected default box names for European countries.
* Correction of HST for variation products.
* Corrected compatibility with bundled products

## Version 4.0.4 – Released: March 01, 2018

[Improvement]
* Automatic label generation restricted to order status processing only.
* Shipping date format changed to the official WordPress date format.
* Enhanced debugging for the Pickup request.

[New Feature]
* Incorporated new FedEx services- FedEx SameDay and FedEx SameDay City.
* WooCommerce FedEx Integration with WooCommerce Measurement Price Calculator plugin.
* Option to see the shipping rates before generating the label on the admin order page.

[Bug Fix]
* Compatible with PHP Version 5.5 and before.
* Enhanced Smartpost service for orders exceeding $100.

## Version 4.0.3 – Released: January 24, 2018

[Improvement]
* Option to give insurance amount at the product level
* Option to select accessibility and regulations at product variation level for dangerous products
* Send email address in shipper contact request (compatibility with multivendor plugins)
* changed the estimated delivery format to WordPress default

[New Feature]
* Option to select alcohol for shipping at product variation level

[Bug Fix]
* Made to work with currency Kuwaiti dinar
* Corrected issue of License key tab conflicting with other XA plugins settings

## Version 4.0.2 – Released: December 29, 2017

[Improvement]
* Support for external products and bundled products and it requires WooCommerce bundled product plugin 5.6.1

[Bug Fix]
* Resolved problem with dimensions not reflecting in debugging.

## Version 4.0.1 – Released: December 22, 2017

[Improvement]
* Changed the slug when navigating to the FedEx settings from the video page.
* Modified the image URL(to an absolute path from URL) for commercial invoice company logo and signature.

## Version 4.0.0 – Released: December 18, 2017

[New Feature]
* New UI.

[Bug Fix]
* Filter introduced to alter the product price.
* Case related to Estimated delivery showing the invalid date.

## Version 3.3.13 – Released: December 22, 2017

[Bug Fix]
* Fixed notice.

## Version 3.3.12 – Released: December 08, 2017

[Bug Fix]
* Case related to Customs value missing.

## Version 3.3.10 – Released: December 04, 2017

[Bug Fix]
* Corrected Conflict with WooCommerce Shipment Tracking Basic Version.

## Version 3.3.9 – Released: November 30, 2017

[Bug Fix]
* Case related to Country-State not getting saved in some cases.

## Version 3.3.8 – Released: November 29, 2017

[Bug Fix]
* PHP warning on a fresh install.

## Version 3.3.7 – Released: November 29, 2017

[Bug Fix]
* PHP warning on a fresh install.

## Version 3.3.6 – Released: November 28, 2017

[Bug Fix]
* Compatibility with WC older version.
* Case related to Exclude tax in the product price.

## Version 3.3.5 – Released: November 27, 2017

[Improvement]
* Combined Country and State fields from the plugin settings page
* Handled case if address line-1 exceeding 30 characters.

## Version 3.3.4 – Released: November 23, 2017

[Improvement]
* Restricted Enqueue media for admin.

[Bug Fix]
* Case related to Estimated delivery time.

## Version 3.3.3 – Released: November 17, 2017

[Bug Fix]
* Case related to Special service ETD not going with Label request.

## Version 3.3.2 – Released: November 16, 2017

[Improvement]
* Added missing SmartPost hubs.

## Version 3.3.1 – Released: November 15, 2017

[Bug Fix]
* The XA-multi-part-product addon plugin's compatibility with FedEx.

## Version 3.3.0 – Released: November 15, 2017

[New Feature]
* Digital Signature for Commercial Invoice
* Company logo in Commercial Invoice
* Non-Standard products

[Bug Fix]
* Case related to freight shipment.

## Version 3.2.3 – Released: November 10, 2017

[New Feature]
* Option to choose a default service.

[Bug Fix]
* Corrected CSS on select boxes in the plugin settings page

## Version 3.1.22 – Released: November 5, 2017

[Bug Fix]
* Case related to return label for my account page.

## Version 3.1.21 – Released: October 31, 2017

[Bug Fix]
* Case of Return label button not appearing if the rate is disabled.

## Version 3.1.19 – Released: October 27, 2017

[Bug Fix]
* Correction if the product is going unpacked.

## Version 3.1.18 – Released: September 15, 2017

[Bug Fix]
* Case related to the Estimated delivery date.

[Improvement]
* Support for Shipping common add-on to bring Residential checkbox on the Checkout page.

## Version 3.1.17 – Released: September 14, 2017

[Improvement]
* Compatibility with Multiple Shipping address plugin.

## Version 3.1.16 – Released: September 06, 2017

[Bug Fix]
* Case related to Estimated Delivery not showing for some countries.

## Version 3.1.15 – Released: August 25, 2017

[Bug Fix]
* Case related to tracking message.

## Version 3.1.14 – Released: August 10, 2017

[Bug Fix]
* Corrected Conflicts with the Basic Version

## Version 3.1.13 – Released: August 04, 2017

[Bug Fix]
* Added Filter for custom tracking message.

## Version 3.1.12 – Released: August 04, 2017

[Improvement]
* Corrected Compatibility with PHP7 problem.

## Version 3.1.11 – Released: August 01, 2017

[Improvement]
* Introduced new column in orders page to show pickup requested or not

[Bug Fix]
* Case related to Pickup not working.

## Version 3.1.10 – Released: July 30, 2017

[Bug Fix]
* Corrected PHP 7.0 compatibility issue.

## Version 3.1.09 – Released: July 24, 2017

[Improvement]
* Introduced Extreme length surcharge with Freight shipment if the length exceeds 180 inches.
* Default signature option kept as empty.

## Version 3.1.08 – Released: July 10, 2017

[New Feature]
* Introduced pre-packed option at the product level.

## Version 3.1.06 – Released: July 06, 2017

[Improvement]
* Added option for saving the name for boxes in box packing

## Version 3.1.05 – Released: July 05, 2017

[Improvement]
* Backward compatibility: Fixed issue of recipient phone number not populating in WC older version.

## Version 3.1.04 – Released: July 05, 2017

[Improvement]
* Corrected Destination address is not going with an older version of WC.

## Version 3.1.03 – Released: July 03, 2017

[Improvement]
* Hide ineligible services for extra added packages.

## Version 3.1.02 – Released: June 29, 2017

[Improvement]
* Option to select Tax type.

[Bug Fix]
* Corrected Compatibility issue with php7.

## Version 3.1.01 – Released: June 28, 2017

[Bug Fix]
* Corrected issue of weight in the fraction

## Version 3.1.0 – Released: June 23, 2017

[New Feature]
* Generate and print the return label from the my-account page.

## Version 3.0.6 – Released: June 14, 2017

[New Feature]
* Implemented Tax Identification Number at the vendor level.

## Version 3.0.5 – Released: June 07, 2017

[New Feature]
* Implemented Custom tracking message.

## Version 3.0.3 – Released: June 05, 2017

[Bug Fix]
* Corrected issue with the third party in Freight shipment.

[New Feature]
* New Box packing algorithm.

## Version 3.0.2 – Released: May 30, 2017

[Bug Fix]
* Removed fraction values from package dimensions.

## Version 3.0.1 – Released: May 29, 2017

[Improvement]
* Changed default delivery time format.

[Bug Fix]
* Corrected display of delivery time twice.

## Version 3.0.0 – Released: May 27, 2017

[Bug Fix]
* Corrected issue of CEF (Clearance Entry Fee)
* FedEx, Ups Conflict in Automatic Label Generation.

## Version 2.9.9 – Released: May 24, 2017

[New Feature]
* Introduced TIN number.
* Compatibility with 'xa-shipping-common-addon'.

## Version 2.9.8 – Released: May 22, 2017

[New Feature]
* Automatic Label Generation, and email Label to the customer.

## Version 2.9.7 – Released: May 22, 2017

[Bug Fix]
* Compatibility issue fix for variable products.

## Version 2.9.6 – Released: May 18, 2017

[New Feature]
* Third-party payer option for Freight shipment.

## Version 2.9.5 – Released: May 17, 2017

[Improvement]
* Compatible With New Addon (Add More Shipping Fields (For Multi-Part Product).

## Version 2.9.4 – Released: May 16, 2017

[Improvement]
* Updated pre-defined box dimension.

## Version 2.9.3 – Released: May 15, 2017

[New Feature]
* Implemented FedEx CEF(Clearance Entry Fees)
* Delivery date format updates on cart page
* Introduced FedEx Specialty boxes

## Version 2.8.3 – Released: May 5, 2017

[Improvement]
* Updated WSDL

## Version 2.8.2 – Released: April 25, 2017

[Bug Fix]
* Corrected issue with services.

## Version 2.8.1 – Released: April 18, 2017

[Bug Fix]
* Case related to issue with Currency ARS.

## Version 2.8.0 – Released: April 07, 2017

[Improvement]
* Introduced Welcome screen with FedEx Shipping Plugin Setup Tutorial.

## Version 2.7.4 – Released: April 11, 2017

[Improvement]
* Updated default label size.

## Version 2.7.3 – Released: March 28, 2017

[Bug Fix]
* Case related to no weight provided by the customer.

## Version 2.7.1 – Released: March 22, 2017

[Bug Fix]
* Case related to estimated delivery time.

## Version 2.7.0 – Released: March 17, 2017

[Improvement]
* WC 2.7 Version compatibility.
* Estimated delivery message improvements

[Bug Fix]
* Case related to dimensions with FedEx Boxes in shipment creation.

## Version 2.6.5 – Released: March 10, 2017

[New Feature]
* Added feature for shipping time offset.

[Improvement]
* Enhancements in duty payer.

[Bug Fix]
* Case related to Package selection.

## Version 2.6.4 – Released: March 02, 2017

[Improvement]
* Return label enhancements.

## Version 2.6.3 – Released: February 27, 2017

[Bug Fix]
* Weight and dimension display on admin order meta.

## Version 2.6.2 – Released: February 23, 2017

[Bug Fix]
* Case related to currency AED

## Version 2.6.1 – Released: February 20, 2017

[Improvement]
* Label text of Box Maximum Weight changed to Max Package Weight.

[Bug Fix]
* Case related to Smart Post Hub in the case of Freight.

## Version 2.6.0 – Released: January 30, 2017

[New Feature]
* Added option of the return label.

## Version 2.5.0 – Released: January 06, 2017

[Bug Fix]
* Fixed the issue of manual package dimension in the case of multi-vendor/multiple shipping addresses.

## Version 2.4.9 – Released: January 04, 2017

[New Feature]
* Handle refunded products while creating the shipment.

## Version 2.4.8 – Released: January 02, 2017

[New Feature]
* Compatibility with 'Multiple shipping address' plugin while creating the shipment.

## Version 2.4.6 – Released: December 26, 2016

[Improvement]
* Enhancements

## Version 2.4.5 – Released: December 20, 2016

[Bug Fix]
* Fixed compatibility issue with older WC version.

## Version 2.4.4 – Released: December 10, 2016

[Improvement]
* Updated readme.txt file.

## Version 2.4.2 – Released: November 27, 2016

[New Feature]
* Added minimum amount.
* Added dangerous goods.
* Added language support for French, Italian, German, and Spanish.

## Version 2.4.0 – Released: November 15, 2016

[Improvement]
* Stability Improvements in Generate Packages.

## Version 2.3.9 – Released: November 14, 2016

[Improvement]
* Stability improvement in dry ice shipment.

## Version 2.3.8 – Released: November 12, 2016

[Bug Fix]
* Correction in dry ice shipment.

## Version 2.3.7 – Released: November 08, 2016

[Improvement]
* Multi-vendor stability improvements.

## Version 2.3.6 – Released: November 01, 2016

[New Feature]
* Implemented dry ice feature.

## Version 2.3.5 – Released: October 29, 2016

[Improvement]
* Splitting of labels.

## Version 2.3.4 – Released: October 19, 2016

[Bug Fix]
* Version fixes.

## Version 2.3.3 – Released: October 18, 2016

[Improvement]
* Added filter for the extra package.

## Version 2.3.2 – Released: September 28, 2016

[Improvement]
* Implemented manual packaging with weight-based shipping and made it compatible with the multi-vendor scenario.

## Version 2.3.1 – Released: September 28, 2016

[New Feature]
* Introduced manual dimension options on packages.

## Version 2.3.0 – Released: September 21, 2016

[Improvement]
* Older version compatibility.

## Version 2.2.9 – Released: September 16, 2016

[New Feature]
* Provided Inner dimensions for weight and dimensions packing.

## Version 2.2.8 – Released: September 08, 2016

[Bug Fix]
* Case related to NUSOAP

## Version 2.2.7 – Released: September 02, 2016

[Bug Fix]
* Case related to PHP compatibility.

## Version 2.2.6 – Released: September 02, 2016

[New Feature]
* Added filter for custom user rule.

## Version 2.2.5 – Released: August 25, 2016

[New Feature]
* Added additional label image types and image sizes.

## Version 2.2.4 – Released: August 23, 2016

[Improvement]
* Address Validation Request enhanced.

## Version 2.2.3 – Released: August 20, 2016

[Improvement]
* Removed redundant code, improved manual dimensions.

## Version 2.2.2 – Released: August 18, 2016

[Improvement]
* Manual dimensions correction and improved label printing.

## Version 2.2.1 – Released: August 17, 2016

[Bug Fix]
* Case related to 'Purpose of Shipment'.

## Version 2.2.0 – Released: August 16, 2016

[New Feature]
* Introduced Country of Manufacture for products.
* Support for non-SOAP servers.

## Version 2.1.9 – Released: August 11, 2016

[Bug Fix]
* Corrected Pickup time issue.

## Version 2.1.8 – Released: August 08, 2016

[Improvement]
* Generalized JS file.
* Case related to API Manager fixed.

[Bug Fix]
* Case related to delivery estimates printing with the rate.

## Version 2.1.7 – Released: August 01, 2016

[Bug Fix]
* API Manager issue fixed.

## Version 2.1.5 – Released: July 28, 2016

[Improvement]
* Added option to exclude taxes from products while generating shipping labels or commercial invoices.

## Version 2.1.4 – Released: July 27, 2016

[Improvement]
* Stability Improvements – Handled warning.

## Version 2.1.3 – Released: July 25, 2016

[Bug Fix]
* Case related to notice.

## Version 2.1.2 – Released: July 25, 2016

[New Feature]
* Pick up options enabled in Settings under Advanced tab

[Bug Fix]
* The case related to the conflict between the base version and the premium version.

## Version 2.1.1 – Released: July 12, 2016

[Bug Fix]
* Case related to Freight class not linking with shipping class.

## Version 2.1.0 – Released: July 11, 2016

[Bug Fix]
* Corrected API manager issue.

## Version 2.0.9 – Released: July 07, 2016

[Bug Fix]
* Case related to PHP compatibility.

## Version 2.0.8 – Released: July 05, 2016

[Improvement]
* Stability Improvements.

## Version 2.0.7 – Released: July 04, 2016

[Bug Fix]
* Case related to deactivation of license.

## Version 2.0.6 – Released: July 04, 2016

[Improvement]
* Improvement in license key implementation.

## Version 2.0.5 – Released: July 04, 2016

[Improvement]
* Improvement in license key implementation.

## Version 2.0.4 – Released: July 02, 2016

[Improvement]
* Implemented license keys.
* Automatically update the plugin from WordPress admin.

## Version 2.0.3 – Released: June 30, 2016

[Improvement]
* Stability Improvements.

## Version 2.0.2 – Released: June 29, 2016

[New Feature]
* Compatibility with a multi-vendor add-on while calculating shipping cost.

## Version 2.0.1 – Released: June 23, 2016

[Bug Fix]
* Case related to address validation (address line 1).

## Version 2.0.0 – Released: June 20, 2016

[Improvement]
* Changed Singapore currency code to SIG from SGD.

## Version 1.9.9 – Released: June 16, 2016

[Bug Fix]
* Version fixes.

## Version 1.9.8 – Released: June 15, 2016

[Improvement]
* Woocommerce Compatibility update for version 2.6.0.

## Version 1.9.7 – Released: June 13, 2016

[New Feature]
* Introduced Harmonized code.

## Version 1.9.6 – Released: June 09, 2016

[Bug Fix]
* Case-related weight in freight.

## Version 1.9.5 – Released: June 03, 2016

[Bug Fix]
* Case related to insurance value.

## Version 1.9.4 – Released: June 03, 2016

[Improvement]
* Order reference no added to the shipping label.

## Version 1.9.3 – Released: June 03, 2016

[New Feature]
* Added email notification for both shipper and customer.

## Version 1.9.2 – Released: May 31, 2016

[New Feature]
* Added signature option.

## Version 1.9.1 – Released: May 28, 2016

[New Feature]
* Added a filter to skip products from the package.

## Version 1.9.0 – Released: May 27, 2016

[Improvement]
* Changed description of Commercial invoice field.

## Version 1.8.9 – Released: May 26, 2016

[Bug Fix]
* Case related to COD.

## Version 1.8.8 – Released: May 24, 2016

[Improvement]
* Reduced the variable-length when the total length of the field exceeds 64 characters.

[New Feature]
* Added a feature of email notification.

## Version 1.8.7 – Released: May 09, 2016

[New Feature]
* Commercial Invoice feature for label printing.

## Version 1.8.6 – Released: May 04, 2016

[New Feature]
* Support for new UK domestic services.

## Version 1.8.4 – Released: May 04, 2016

[Improvement]
* Settings page content update.
* Stability-related fixes.

## Version 1.8.0 – Released: April 11, 2016

[New Feature]
* Manual Label Printing.
* Show Delivery Estimate.
* Method Available to option on settings.

[Improvement]
* Stability-related fixes.

## Version 1.7.5 – Released: April 02

[New Feature]
* Saturday delivery option.
* Added option to provide Conversion Rates.
* Added option to flip Ship from and to address.
* Code changes for supporting Vendor Plugin.

## Version 1.6.5 – Released: March 11, 2016

[New Feature]
* Weight Based shipping feature introduced.

## Version 1.6.3 – Released: March 10, 2016

[Bug Fix]
* Case related to print label.

## Version 1.6.2 – Released: February 29, 2016

[Bug Fix]
* Case related to the invoice value.

[Improvement]
* Filter added to modify FedEx request.

## Version 1.6.0 – Released: February 17, 2016

[Bug Fix]
* Case related to COD total.

[Improvement]
* Restricted creating a label for unpacked items using box packing method.
* Added notice log for address verification request and response.

## Version 1.5.6 – Released: February 04, 2016

[New Feature]
* Introduced Weight Based Shipping.

## Version 1.5.5 – Released: February 03, 2016

[New Feature]
* B13A filing option with the export document for International Shipment (Other than the US) from Canada.

[Bug Fix]
* Case related to label printing.

## Version 1.5.2 – Released: January 21, 2016

[Bug Fix]
* Case related to Mexican Peso fixed while Showing rates on Cart Page

## Version 1.5.1 – Released: January 02, 2016

[New Feature]
* Introduce support for KG/CM
* Introduced CHF SFR (Swiz) & Peso Mexicano currency support
* Minor UX/Content Changes

[Bug Fix]
* Fixed issue related to a call to get_countries.

## Version 1.4.5 – Released: December 10, 2015

[Bug Fix]
* Case related to label printing.

[Improvement]
* WooCommerce FedEx Integration with multiple shipping address plugin.

## Version 1.4.3 – Released: October 26, 2015

[New Feature]
* Can choose COD Collection Type.

## Version 1.4.2 – Released: October 25, 2015

[New Feature]
* Implemented COD Return Label.

## Version 1.4.1 – Released: October 08, 2015

[Bug Fix]
* For all the PluginHive shipping plugins to work simultaneously

## Version 1.4.0 – Released: October 08, 2015

[New Feature]
* New Feature: Cash On Delivery option while printing the label.

## Version 1.3.0 – Released: August 04, 2015

[New Feature]
* Automatically add tracking details in order completion email.

[Bug Fix]
* Used FedEx currency code 'UKL' for the UK.

## Version 1.2.1 – Released: August 03, 2015

[New Feature]
* Added a new option Automatic in Indicia settings. Automatically will choose PRESORTED STANDARD if the weight is less than 1lb and PARCEL SELECT if the weight is more than 1lb.

## Version 1.1.2 – Released: August 01, 2015

[Improvement]
* As per the suhosin.post.max_name_length guidelines following field names changed to less than 64 lengths. Please re-enter the values for these fields and save the settings after the installation: Billing Street Address 2, Billing ZIP / Postcode, Billing Country Code, Tracking PIN, Rates in base currency.

## Version 1.1.1 – Released: April 28, 2015

[Improvement]
* As per the guidelines following field names changed to less than 64 lengths. Please re-enter the values for these fields and save the settings after the installation: Shipper Person Name, Shipper Company Name, Shipper Phone Number, Shipper Street 2, Shipper Residential.

## Version 1.1.0 – Released: April 15, 2015

[New Feature]
* Plugin to work globally wherever FedEx service available. Customs information for all countries except US & CANADA and Added 'Purpose' => 'SOLD'
* Addition provision to enable FedEx Boxes for other countries than the US. FedEx One Rates will be offered if the items are packed into a valid FedEx One box, and the origin and destination are the US. For other countries, this option will enable FedEx packing. Note: All FedEx boxes are not available for all countries, disable this option or disable different boxes if you are not receiving any shipping services.
* Option to convert the currency to base currency 'FedEx API returns the rates in USD. Please enable Rates in the base currency option in the plugin. Conversion happens only if FedEx API provides the exchange rates.'

## Version 1.0.0 – Released: April 08, 2015

[New Feature]
* Dynamic Shipping Rates
* Label Printing
