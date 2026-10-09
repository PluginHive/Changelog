## Version 6.6.5 – Released: October 8th, 2026

[New Feature]
* Added Hazmat Emergency Contact and Hazmat Emergency Phone Number settings, so you can send your own 24 hour emergency contact details for dangerous goods shipments instead of your store's regular attention name and phone number.
* Added a "Product SKU x Quantity" option to show each package's products and quantities on the label reference, for example "NGx3,TWLx1".

[Improvement]
* Address classification and suggestions now work at checkout even when live rates are turned off.
* For shipments to or from Vietnam, the plugin now works out the province from the postcode, so rate requests and labels no longer fail because of a missing province.

## Version 6.6.4 – Released: September 17th, 2026

[New Feature]
* Added a new "ph_ups_skip_commercial_invoice" filter that lets store owners skip commercial invoice generation for orders going to regions not part of WooCommerce's countries list, without affecting the shipping label or destination country.

[Improvement]
* Completed and corrected translations across the plugin for French, German, Italian, and Spanish.

[Bug Fix]
* Fixed incorrect HazMat quantity sent to UPS when the product's weight unit differed from the account's configured unit of measure.
* Fixed an issue where the shipping cost stored for an order could include extra decimal places when a Rate Adjustment or currency conversion was applied, causing it to not exactly match what was displayed at checkout.

## Version 6.6.3 – Released: August 6th, 2026

[New Feature]
* Added a new "[ADDITIONAL LABELS]" placeholder tag for the shipment label email, letting store owners include download links for extra shipment documents (such as a dangerous goods manifest or commercial invoice) directly in the email body.

## Version 6.6.2 – Released: July 31st, 2026

[Improvement]
* Added "DAP – Delivery at Place" as a new option under the "Terms of Sale (Incoterm)" setting for international shipments.

[Bug Fix]
* Fixed a duplicate confirmation message that appeared when saving WordPress settings pages while the UPS plugin was active.
* Fixed an issue where UPS Simple Rate was incorrectly applied to international shipments.

## Version 6.6.1 – Released: July 15th, 2026

[New Feature]
* The country list used for "Skip Commercial Invoice for EU Shipments" is now merchant-editable, instead of a fixed, hardcoded set of EU countries.
* Added new "Show only for UPS methods" setting — shows up only when the Access Point locator is enabled, and when checked, hides the Access Point field on the checkout page if a non-UPS shipping method is selected.
* Added new "Global Tax Information" setting to declare the Consignee Type (Business or Individual) for international shipments, supporting EU de-minimis customs requirements. A default can be set globally, with the option to override it per order from the edit order page.

[Improvement]
* The "Duties and Taxes Payer" field is no longer shown on the edit-order page for domestic shipments, since it doesn't apply to them.

[Bug Fix]
* Fixed an issue where the "Duties and Taxes Payer" selection made on the edit order page was being ignored during label generation, causing the label to always use the global setting instead.

## Version 6.6.0 – Released: June 15th, 2026

[New Feature]
* UPS Access Point Locator is now fully supported in WooCommerce Block Checkout – customers can select a nearby UPS Access Point® location with rates updating automatically.
* Added Recipient TIN field support for Block Checkout with a configurable field label, saving billing and shipping TINs independently for label generation.
* Added "Automatic Additional Handling" setting — automatically applies the UPS AdditionalHandlingIndicator for packages exceeding UPS size or weight thresholds.
* Added per-package Additional Handling checkbox in Edit Order with manual override support – state persists across page reloads and Calculate Cost.
* Added an option under International Forms settings to skip Commercial Invoice generation for intra-EU shipments, ensuring CI is only included when shipping to destinations outside the European Union

[Improvement]
* Redesigned Edit Order package section with structured package cards showing labelled fields for weight, dimensions, insurance, and shipping service.

[Bug Fix]
* Resolved UPS checkout rate errors and missing signature requirement on US-Puerto Rico labels when delivery confirmation is configured

## Version 6.5.1 – Released: May 28th, 2026

[Improvement]
* Improved admin page load performance by optimising the notice system to avoid unnecessary database operations when there are no active notices.
* Developer hooks to control UPS signature requirements and package/shipment service options — works across checkout rates, auto-labels, and manually generated labels from the order page.

## Version 6.5.0 – Released: April 29th, 2026

[New Feature]
* Added WooCommerce Block Checkout compatibility for UPS Address Suggestion, with a new configurable suggestion message setting.

## Version 6.4.3 – Released: April 16th, 2026

[Bug Fix]
* Replaced transient-based storage with wp_options for auth token and internal endpoints. Caching plugins like Object Cache Pro, Redis and others were serving stale data, causing intermittent Unauthorized errors. This ensures consistent data across all caching setups.

## Version 6.4.2 – Released: March 31st, 2026

[Bug Fix]
* Resolved a fatal error during plugin update checks by adding robust validation to safely handle empty or unexpected API responses from the update server.

## Version 6.4.1 – Released: March 27th, 2026

[Improvement]
* Compatibility for PHP v7.4 on handling transient data by replacing usage of match() function with switch()

[Bug Fix]
* Fixed shipping rate calculation between checkout and edit order when using conversion rates

## Version 6.4.0 – Released: March 26th, 2026

[Improvement]
* Introduced new hooks and internal enhancements to support the upcoming PH UPS WorldEase Shipment Management Addon.
* Added filter hooks to allow exclusion of specific orders from UPS pickup requests and cancellation workflows for better extensibility.

[Improvement]
* Refactored shipment JavaScript structure to improve code maintainability and scalability without impacting existing functionality.
* Optimized International "Sold To" logic for more efficient processing while preserving current behavior.
* Improved internal void shipment flow to enhance reliability and handle edge cases more effectively.
* Implemented transient-based caching on the license page to improve performance and reduce redundant processing.
* Enhanced bearer token retrieval and management to ensure stable and efficient API authentication with UPS, particularly for environments with object caching enabled.
* Refactored bulk printing of labels and commercial invoices into a reusable utility to streamline code and reduce duplication.
* Updated default settings for Real-Time Rates and Label Type to align with common usage and simplify initial configuration.

## Version 6.3.10 – Released: January 29th, 2026

[Bug Fix]
* Handled UPS access point field returning single value.

## Version 6.3.9 – Released: January 22nd, 2026

[Improvement]

[Bug Fix]
* Fixed meta data saving twice in database
* Handled UPS access point field being empty.

## Version 6.3.8 – Released: December 3rd, 2025

[Improvement]
* Added commercial invoice option for shipments between EU countries The manifest for HazMat products now shows the correct total weight for a package instead of listing each item separately.

## Version 6.3.7 – Released: October 22nd, 2025

[Bug Fix]
* The manifest for HazMat products now shows the correct total weight for a package instead of listing each item separately.

## Version 6.3.6 – Released: October 7th, 2025

[Improvement]
* Shipment request handling to ensure hazmat rate details are included for multi-package shipments, resulting in accurate hazmat surcharge calculation

## Version 6.3.5 – Released: October 6th, 2025

[Improvement]
* Enhanced WordPress Security Configuration Compliance.
* UPS ZPL labels are now saved in the uploads folder, ensuring they download properly without permission issues

## Version 6.3.4 – Released: September 8th, 2025

[Improvement]
* Added compatibility for the new WooCommerce Hazmat Package Splitter For UPS add-on.

## Version 6.3.3 – Released: August 8th, 2025

[Improvement]
* Faster rate fetching times at cart and checkout page.
* Show Monday delivery dates along with Saturday delivery dates – applicable when Saturday Delivery is enabled.
* Option to add Insurance for shipments on the Edit Order page.
* Option to include tax on the commercial invoice when the price value is selected as a Discounted Price.

[Bug Fix]
* Auto label generation for billing address – Ireland and shipping address – USA.

## Version 6.3.2 – Released: July 16th, 2025

[Improvement]
* Compatibility with WooCommerce v.10.0.2.

## Version 6.3.1 – Released: July 11th, 2025

[Bug Fix]
* Fixed box packing method with stack-first packaging, including pre-packed items.

## Version 6.3.0 – Released: June 30th, 2025

[Deprecated]
* Removed legacy UPS XML API support; OAuth-based registration is now mandatory for account connection.

[Improvement]
* Improved handling of special characters in the Ship To City and Contact Name fields.

[Bug Fix]
* Fixed an issue where validation settings were not saving as expected.
* Addressed a packaging conflict with third-party shipping plugins.

## Version 6.2.9 – Released: May 28th, 2025

[Improvement]
* Rates compatibility with UPS Access Point.

## Version 6.2.8 – Released: May 20th, 2025

[Improvement]
* Compatibility with WooCommerce v.9.8.5.
* Compatibility with WordPress v.6.8.1.
* Improved the process for Plugin License Activation.
* Support for Cash on Delivery (COD) at the shipment level (for Poland, Italy, UK etc).
* Support for German special characters in ZPL label.

## Version 6.2.7 – Released: April 15th, 2025

[Improvement]
* Improved compatibility with Estimated Delivery Date Adjustment for UPS addon.

## Version 6.2.6 – Released: April 9th, 2025

[Improvement]
* Option to request shipping rates without estimated delivery when Rates not returned due to strict address validation when requesting rate with time in transit.

[Bug Fix]
* Selected shipping method is not reflecting in the Express Checkout Payment Gateway.

## Version 6.2.5 – Released: April 4th, 2025

[New Feature]
* Added Max Quantity filter for boxes.
* Min and Max Shipping Cost range for rates at cart & checkout.
* Insurance Amount now gets added to commercial invoice.

[Improvement]
* Removed caching on clickable buttons.
* Updated "Default recipient phone number" as default settings for shipment creation when the phone number is missing in the order.
* Bulk activation of boxes.
* Placeholder selection options for Shipping Label "Email subject" and "Content of email with labels".
* Extensions submenu with a list of compatible and useful plugins.
* Added Vendor Collect ID in bulk and auto-generate shipments.
* Improved working days functionality for rates, labels, and pickups.

## Version 6.2.4 – Released: February 27th, 2025

[Improvement]
* Support for UPS Multi-Account Registration with Multi Warehouse Addon.

## Version 6.2.3 – Released: February 5th, 2025

[New Feature]
* Added Working days functionality.
* Added new feature Cleanup UPS Shipment Details.

[Improvement]
* Auto label printing support for UPS Import Control shipments.
* Return label printing support for UPS Import Control shipments.

## Version 6.2.2 – Released: January 24th, 2025

[Bug Fix]
* Updated PHP class names in the packing algorithm to prevent conflicts with third-party plugins.
* Fixed error caused by the missing Box Weight option in Weight-based Packing.

## Version 6.2.1 – Released: January 16th, 2025

[Improvement]
* Compatibility with PH UPS Roll & Pack addon.
* Improved compatibility with WooCommerce Measurement Price Calculator.

## Version 6.2.0 – Released: January 2nd, 2025

[Improvement]
* Added Compatibility with WooCommerce Product Bundles.
* Added option to add default Vendor Collect ID Number.
* Compatibility for minimum WooCommerce version 8.6.2.

[Bug Fix]
* Display Tin number in the commercial invoice as Vendor Info is enabled.

## Version 6.1.9 – Released: December 3rd, 2024

[New Feature]
* Introduced a Box Weight Option for the Weight-Based Parcel Packing Method.
* View boxes in a drop down option before generating label on edit order page.

[Improvement]
* Display box name after generating label for box packing to easily identify boxes.

## Version 6.1.8 – Released: November 14th, 2024

[Improvement]
* Compatibility with WooCommerce Ship to Multiple Addresses plugin.
* Compatibility with Kadence WooCommerce Email Designer Plugin.
* Compatibility with WooCommerce Product Bundles plugin.

[Bug Fix]
* Printing the shipping label in landscape mode with Display in Browser option.
* Adding new packaging boxes after deleting existing ones.

## Version 6.1.7 – Released: October 23rd, 2024

[Improvement]
* Updated the void shipment process.
* Introduced an easy way to re-generate shipping labels.

[Bug Fix]
* Fixed Custom Scaling for Display Labels in Browser for Individual Order.

## Version 6.1.6 – Released: October 15th, 2024

[Improvement]
* Added Order Id placeholder for email subject and content.

[Bug Fix]
* Fixed Adding Package Details in email content.
* Fixed "Consider Shipping Address as Sold to Address".

## Version 6.1.5 – Released: September 16th, 2024

[Improvement]
* Support for special characters in the Custom Box Name

## Version 6.1.4 – Released: August 7th, 2024

[Improvement]
* Support for UPS Ground Freight Pricing (GFP) rates and labels via Rest API

[Bug Fix]
* Return label printing for Laser 8.5 x 11 format
* Bulk label generation for products without weight or dimensions with UPS Rest API
* Case related to additional document upload

## Version 6.1.3 – Released: July 11th, 2024

[Improvement]
* Case related to UPS Account Re-registration Process

## Version 6.1.2 – Released: July 9th, 2024

[Bug Fix]
* Case related UPS Account registration with renewed license keys

## Version 6.1.1 – Released: July 6th, 2024

[Bug Fix]
* Fatal error – due to compatibility issues with third-party plugins.

## Version 6.1.0 – Released: July 5th, 2024

[New Feature]
* Support for custom actions triggered by the UPS Pickup Request Addon.
* Added UPS Shipping Rates under WooCommerce Shipping Zones.
* Estimated Delivery Dates support for WooCommerce Blocks.

[Improvement]
* Support for special characters in shipment details.
* Alert notice for users when their license is nearing expiration.
* Reduced plugin size for improved performance.

## Version 6.0.9 – Released: June 25th, 2024

[Improvement]
* Improved compatibility with Multi-Warehouse Addon.

## Version 6.0.8 – Released: June 12th, 2024

[Improvement]
* Support to Print Customer's Name as Company Name on Commercial invoice for Billing Details.
* Support for backward compatibility WooCommerce v5.0.0.

[Bug Fix]
* Fixed Sure post Rates for REST.
* Added Default boxes filter based on Country.

## Version 6.0.7 – Released: May 21st, 2024

[Bug Fix]
* Corrected the label in the vendor email for OAuth.

## Version 6.0.6 – Released: May 14th, 2024

[Improvement]
* UI improvements for Return Label Service Selection Option.
* Compatibility with Replace Carrier Account Add-on.
* Compatibility of Insured Value with REST.
* Compatibility of "UPS Order Pickup Date Based on Delivery Date Add-on" with UPS REST.

[Bug Fix]
* Corrected the label in the vendor email to accurately reflect the information.
* UPS Boxes not getting displayed during initial installation for new users.

## Version 6.0.5 – Released: April 29th, 2024

[New Feature]
* Added option to select Unit of Measure (UOM) for Invoice Products.

[Bug Fix]
* Case related to printing Dangerous Goods Signatory Info Document using new UPS OAuth.
* Resolved Signature Info display for accurate Rate Calculation and Shipment Creation.

## Version 6.0.4 – Released: April 17th, 2024

[Improvement]
* Grouping Hazmat details for products in similar category on the Hazmat shipping label.
* Added Custom Declared Value for every unit product in Commercial Invoice.
* Delivery Signature options available while generating shipping labels manually.

[Bug Fix]
* REST API compatibility for UPS Negotiated Rate with Tax On Rates, delete option for uploaded documents & UPS Address Suggestion.
* PHP Warning Fix for Manual Package Label Generation.

## Version 6.0.3 – Released: April 6th, 2024

[New Feature]
* UPS Account Management now includes the ability to Remove Account & Re-register.

[Bug Fix]
* Fixed Rate & Label Issue for Renewed Plugin License Keys.
* Resolved Shipment Creation Issue for Postal codes with 9 Digits for International shipments.

## Version 6.0.2 – Released: April 2nd, 2024

[Bug Fix]
* Case related to negotiated rate calculation.
* Fixed fatal error occurring on the cart page when the shipping address is empty.

## Version 6.0.1 – Released: March 30th, 2024

[Bug Fix]
* Corrected Duties And Taxes Payer and Transportation settings for "Shipper" option.
* Ensured correct passing of split product description.
* Resolved issue with the undeliverable email address when multiple email tracking notifications were selected.

## Version 6.0.0 – Released: March 28th, 2024

[New Feature]
* Migration to UPS REST API.

## Version 5.0.5 – Released: March 20th, 2024

[Improvement]
* Label Generation with Delivery Confirmation handled at package or shipment level for countries other than US, Puerto Rico, and Canada.
* UPS API Migration Announcement Banner for REST API.

## Version 5.0.4 – Released: March 8th, 2024

[Improvement]
* Compatibility with UPS Order Pickup Date based on Delivery Date Addon.

## Version 5.0.3 – Released: March 6th, 2024

[Improvement]
* Enhanced compatibility with WooCommerce Ship to Multiple Addresses plugin.

[Bug Fix]
* Resolved issue with Label Generation when Adult Signature Required.
* Fixed recipient TIN not updating via WooCommerce Edit Orders page.

## Version 5.0.2 – Released: February 7th, 2024

[Improvement]
* Handling Empty Invoice Description.

[Bug Fix]
* Sending Shipping Labels via Emails for Vendors.
* Send Shipping Label via Email with Custom Content.

## Version 5.0.1 – Released: January 11th, 2024

[Improvement]
* Enhanced Support for Older WooCommerce Versions (Prior to v.8.2).

## Version 5.0.0 – Released: December 28th, 2023

[Improvement]
* Compatibility with WooCommerce High-Performance Order Storage(HPOS)

## Version 4.9.1 – Released: December 15th, 2023

[Improvement]
* Compatibility with WooCommerce 8.4.0

## Version 4.9.0 – Released: November 9th, 2023

[Bug Fix]
* Preventing multi-click for Create Shipment.
* Added Dimensions UnitOfMeasurement for manual package.

## Version 4.8.9 – Released: October 19th, 2023

[Improvement]
* Duties & Taxes payer as Recipient now supported with UPS Access Points

## Version 4.8.8 – Released: October 11th, 2023

[Improvement]
* PHP 8.2 Compatibility.
* Updated Service names based on UPS API documentation.

[Bug Fix]
* Fixed multi-click for bulk label generation.

## Version 4.8.7 – Released: September 14th, 2023

[Bug Fix]
* Fixed related to weight-based packing when the packing process is 'Pack heavier items first'.

## Version 4.8.6 – Released: August 10th, 2023

[Bug Fix]
* Case related to printing manifests for orders with HazMat variable products.

## Version 4.8.5 – Released: August 9th, 2023

[New Feature]
* Added a new field for Packaging Instruction Code within product settings.

[Bug Fix]
* Case related to the display of checkout rates when Hazmat products are involved.
* Case related to ZPL label printing using Firefox browser.

## Version 4.8.4 – Released: July 13th, 2023

[Bug Fix]
* Fixed plugin license activation issue causing rates to experience difficulties

## Version 4.8.3 – Released: July 12th, 2023

[Improvement]
* Improved UPS Rate request & response from UPS API.
* Improved UPS labels with EEI for products having cost value in decimals.

## Version 4.8.2 – Released: June 16th, 2023

[New Feature]
* Option to re-register UPS Account

[Improvement]
* Added support for GFP rates & labels, Landed Cost, Upload document, API History Table

## Version 4.8.1 – Released: June 6th, 2023

[Bug Fix]
* Fixed PHP warning.

## Version 4.8.0 – Released: June 5th, 2023

[New Feature]
* Migration to UPS OAuth 2.0: Upgrading API security for enhanced protection.

## Version 4.7.7 – Released: May 30th, 2023

[Improvement]
* Added Hook Support for Multi Warehouse Shipping Addon.

## Version 4.7.6 – Released: May 18th, 2023

[Improvement]
* Added Hook Support for PluginHive Addons.

## Version 4.7.5 – Released: May 4th, 2023

[New Feature]
* Send Shipping Labels to multiple recipients using the Email Recipients in CC option.

[Improvement]
* Option to add only Order Number in the Shipment Description/Reference Number.

## Version 4.7.4 – Released: April 18th, 2023

[Improvement]
* Added loading icon for Address Suggestion.

[Bug Fix]
* Added Delivery Confirmation for a manual package.

## Version 4.7.3 – Released: April 6th, 2023

[Improvement]
* Handled empty product price.
* Added Custom Declared Value option at product variation level.

## Version 4.7.2 – Released: March 10th, 2023

[Improvement]
* Compatibility with WooCommerce Shipping Label Addon

## Version 4.7.1 – Released: March 9th, 2023

[Improvement]
* Added Shipper phone number in Commercial invoice

## Version 4.7.0 – Released: February 16th, 2023

[New Feature]
* Compatibility with Replace Carrier Account add-on

[Bug Fix]
* Case related to conversion rate for multi-vendor scenario.
* ISC not passing for rates and labels.

## Version 4.6.9 – Released: February 10th, 2023

[New Feature]
* Currency Conversion support for Vendors

## Version 4.6.8 – Released: February 3rd, 2023

[Bug Fix]

## Version 4.6.7 – Released: February 1st, 2023

[Improvement]

[Bug Fix]

## Version 4.6.6 – Released: January 17th, 2023

[Improvement]

## Version 4.6.5 – Released: December 27th, 2022

[Improvement]

## Version 4.6.4 – Released: December 16th, 2022

[New Feature]

[Bug Fix]

## Version 4.6.3 – Released: December 1st, 2022

[New Feature]

[Improvement]

## Version 4.6.2 – Released: November 25th, 2022

[Improvement]

[Bug Fix]

## Version 4.6.1 – Released: November 14th, 2022

[New Feature]

## Version 4.6.0 – Released: October 28th, 2022

[Improvement]

## Version 4.5.9 – Released: October 14th, 2022

[New Feature]

## Version 4.5.8 – Released: September 29th, 2022

[Improvement]

## Version 4.5.7 – Released: September 22nd, 2022

[New Feature]

[Bug Fix]
* Fatal error while calculating shipping.

## Version 4.5.6 – Released: September 17th, 2022

[New Feature]

[Bug Fix]

## Version 4.5.5 – Released: September 12th, 2022

[Improvement]

## Version 4.5.4 – Released: August 11th, 2022

[Bug Fix]

[Improvement]

## Version 4.5.3 – Released: July 1st, 2022

[Improvement]

## Version 4.5.2 – Released: May 30th, 2022

[New Feature]
* Return label is made available to the end customer through email upon generation by merchant.

[Improvement]

## Version 4.5.1 – Released: May 17th, 2022

[Improvement]
* Support for the new addon, 'UPS Terms Of Sale Automation'.

## Version 4.5.0 – Released: April 13th, 2022

[Improvement]
* Print UPS Label (PDF) options under WooCommerce Bulk Actions will directly download the PDF file instead of opening the file in the browser.

## Version 4.4.8 – Released: March 29th, 2022

[New Feature]
* Added new option to select Ultimate Consignee Type under EEI Data Settings

## Version 4.4.7 – Released: March 24th, 2022

[Bug Fix]
* Case related to Shipper addresses while fulfilling an order with multiple vendors

## Version 4.4.6 – Released: March 18th, 2022

[New Feature]
* Added UPS Vendor Collect ID (VCID)

## Version 4.4.5 – Released: March 11th, 2022

[New Feature]
* Added ITN Number & Exemption Legend Options on the Order Edit Page

[Bug Fix]
* Case related to Product Price display on Commercial Invoice

## Version 4.4.4 – Released: March 5th, 2022

[New Feature]
* Added Pickup & Delivery Options for Freight Rates

[Bug Fix]
* Fatal error related to Access Points

## Version 4.4.3 – Released: February 5th, 2022

[Improvement]
* Return Label support for Multiple Packages in case of International Shipments

## Version 4.4.2 – Released: January 19th, 2022

[Improvement]
* Introduced UPS Label generation in Multi-vendor Dokan Dashboard
* Updated Stack first Packing Algorithm

## Version 4.4.1 – Released: January 11th, 2022

[Bug Fix]
* Case related to display of Access Point address during automatic label generation
* Case related to rate calculation on the order edit page with Access Point as special service

## Version 4.4.0 – Released: December 22nd, 2021

[Improvement]
* Added a component to support Multi-Warehouse addon for Freight shipments

## Version 4.3.9 – Released: December 16th, 2021

[Bug Fix]
* Case related to Undefined error

[Improvement]
* Updated the UPS Import Control text link in the plugin settings

## Version 4.3.8 – Released: December 15th, 2021

[Improvement]
* Added option to pass "Order details in Shipment Description"

## Version 4.3.7 – Released: December 11th, 2021

[New Feature]
* Added option to select Multiple Tracking Notification type under "Send Email Notification To" option

[Bug Fix]
* Case related to removing Access Points Option on Edit Order Page

## Version 4.3.6 – Released: November 30th, 2021

[Bug Fix]
* Automatic Label generation for orders paid through Paypal

## Version 4.3.5 – Released: November 24th, 2021

[Bug Fix]
* Case related to activation of PluginHive UPS plugin along with "WooCommerce Shipping label" plugin

## Version 4.3.4 – Released: November 17th, 2021

[New Feature]
* Provided option to add UPS custom Tracking URL

## Version 4.3.3 – Released: November 10th, 2021

[Bug Fix]
* UPS Special Services will be considered for Shipping Rate Calculation on Edit Order Page (COD, Direct Delivery, UPS Import Control, Saturday Delivery)
* Saturday Delivery support for Shipping Rate Calculation on Cart/Checkout page

[Improvement]
* UI Update – Added new tab for Special Services
* Removed Debug Logs display from Cart/checkout page
* Rounding off Package Dimensions exceeding 2 decimals

## Version 4.3.2 – Released: October 22nd, 2021

[New Feature]
* Added ShipFrom Address Preference on the Edit Order Page

[Bug Fix]
* State Province Code exceeding the maximum no. of allowed characters

## Version 4.3.1 – Released: October 13th, 2021

[New Feature]
* Added new option for Shipment Description for Labels – Product Name x Quantity

[Bug Fix]
* Exclude Refunded Items from Package/Label Creation

## Version 4.3.0 – Released: October 5th, 2021

[Bug Fix]
* Delivery Confirmation was not reflecting when updated on the Edit Order Page for Rate Calculation

## Version 4.2.9 – Released: September 24th, 2021

[New Feature]
* Added Delivery Confirmation and Direct Delivery Options on the Order Edit Page

[Improvement]
* Order Edit page UI update

## Version 4.2.7 – Released: August 26th, 2021

[Improvement]
* Added Options to limit Access Point Locations by "Location Type" and "Max Locations"

[Bug Fix]
* Fixed Access Point Locator Address saving and UI Issues on the Edit Order Page

## Version 4.2.6 – Released: August 20th, 2021

[Improvement]
* Allow UPS Pickup when ShipFrom "Company Name" is empty

[Bug Fix]
* Fixed console errors

## Version 4.2.5 – Released: August 17th, 2021

[New Feature]
* UPS Pickup support when "ShipFrom Address Preference" is set to Shipping Address
* Compatibility with WooCommerce Blocks Plugin to display UPS Estimated Delivery on Cart/Checkout pages.

## Version 4.2.4 – Released: August 9th, 2021

[Improvement]
* Restricted Shipment Description up to 50 characters for Product SKU on Shipping Label

## Version 4.2.3 – Released: July 14th, 2021

[Improvement]
* Improved Address Suggestion (Display as Option) on Checkout Page

[Bug Fix]
* Fixed error related to Import Control Shipment incase of Canadian Shipper Address
* Fixed conflict with Pay for Order page when Address Suggestion (Display as Option) is enabled

## Version 4.2.2 – Released: June 26th, 2021

[Bug Fix]
* Fixed Shipping Rate Calculation with Multi-Vendor Split and Sum Option

## Version 4.2.1 – Released: June 15th, 2021

[Improvement]
* Compatibility with PHP version 8
* Changed the placement of "Additional Taxes & Charges" field after Order Total (on cart page)

## Version 4.2.0 – Released: June 11th, 2021

[Improvement]
* Introduced option to show "Customs Duties and Taxes" in cart page

[Bug Fix]
* Fixed issue with Terms of Shipment in Edit Order Page

## Version 4.1.9 – Released: May 31st, 2021

[Improvement]
* Personalize the content with Customer Name and Email address while sending shipping label in an email

## Version 4.1.8 – Released: May 26th, 2021

[Improvement]
* Updated Freight Shipping Service Names
* Added Hooks to support PluginHive Addons

## Version 4.1.7 – Released: May 15th, 2021

[Bug Fix]
* Fixed – Cash On Delivery label Issue for Multi-Package Shipment

## Version 4.1.6 – Released: May 4th, 2021

[Improvement]
* Added Delivery Confirmation option in UPS global settings page

[Bug Fix]
* Case related to "Method Availability" option for certain countries

## Version 4.1.5 – Released: April 15th, 2021

[Improvement]
* UPS Shipping rates calculation for more than 50 packages
* Shipment description won't support special characters
* Support for UPS SurePost shipping rates calculation for single-piece shipments

[Bug Fix]
* Tracking Number for UPS Ground with Freight Pricing (GFP)

## Version 4.1.4 – Released: March 25th, 2021

[Bug Fix]
* Display of notices after activation of the plugin

## Version 4.1.3 – Released: March 25th, 2021

[Improvement]
* Display shipping charges in Commercial Invoice
* Display discounted price in Commercial Invoice
* Print Dangerous Goods Signatory Information (DG Paper) for Hazardous Shipments
* Select Terms of Sale for WooCommerce orders
* Compatibility with Print Invoice & Delivery Notes for WooCommerce plugin
* Stack First Algorithm for unpacked products

[Bug Fix]
* Discounted price displaying in Commercial Invoice for the product with no weight & dimensions

## Version 4.1.2 – Released: March 11th, 2021

[New Feature]
* Support for UPS Import Control with Automatic & Bulk Label Generation

[Improvement]
* Align how the shipping labels are displayed within the browser for individual orders

[Bug Fix]
* Number of packages that are generated for UPS Freight while calculating shipping rates
* Automatically printing shipping labels by clicking in Generate Packages option

## Version 4.1.1 – Released: February 26th, 2021

[Improvement]
* Added UPS Import Control option for International Shipments during Manual Label Generation
* Option to display PNG and GIF Label in Landscape mode in Browser for Individual Orders
* Option to display Address Suggestion(as options) on Checkout Page

[Bug Fix]
* Fix delivery confirmation issue for Ground with Freight Pricing

## Version 4.1.0 – Released: February 18th, 2021

[Bug Fix]
* Option Rate Calculation for manual packages when no weight and dimensions are assigned to the products

[New Feature]
* Option to enable COD rates in the shipping price
* Third Party Option for "Transportation" and "Duties and Taxes"
* Provided Product Description option at the product level
* Added HS Tariff Option for Variable Products

## Version 4.0.9 – Released: February 4th, 2021

[New Feature]
* UPS International Special Commodity options for WooCommerce shipments

[Improvement]
* Updated UPS shipping services names
* Optimized shipment insurance calculation
* Compatibility with Ship To Multiple Addresses addon

[Bug Fix]
* Fixed shipping label size while printing ZPL labels in bulk
* Fixed default shipping service issue while printing labels in bulk (for manually placed orders only)

## Version 4.0.8 – Released: January 4th, 2021

[Improvement]
* Supporting Brexit changes, print the commercial invoice for shipments from the UK to EU and back

## Version 4.0.7 – Released: December 4th, 2020

[Bug Fix]
* Fixed rates issue when the cart contains more than 4000 products

## Version 4.0.6 – Released: November 26th, 2020

[Improvement]
* Improved Stack First Packing Algorithm
* Added meta key support to Shipping Address Phone Number
* Added Minimum Package Weight as "0.05"

## Version 4.0.5 – Released: November 23rd, 2020

[Improvement]
* Added option to automatically change the packing method from Stack First to Volume Based when the products are packed in a box and the filled up space is less than 44% of the box volume

[Bug Fix]
* Unit of measurements in the pickup request

## Version 4.0.4 – Released: November 13th, 2020

[Improvement]
* Introduced line breaks for street lines during Address Suggestion

[Bug Fix]
* Pickup for shipments generated using Manual Packages

## Version 4.0.3 – Released: November 5th, 2020

[Improvement]
* Address suggestions on WooCommerce checkout page

[Bug Fix]
* Shipping cost calculation on WooCommerce Orders page when UPS Access Point is selected by the customers

## Version 4.0.2 – Released: October 26th, 2020

[Improvement]
* Compatibility with WooCommerce Ship to Multiple Addresses plugin

## Version 4.0.1 – Released: October 16th, 2020

[Bug Fix]
* Print UPS shipping labels in bulk from WooCommerce orders page

## Version 4.0.0 – Released: October 12th, 2020

[New Feature]
* UPS pickup date is now displayed under the Shipping Address section on the WooCommerce Orders page

[Improvement]
* If UPS pickup is requested after the company closing time, it will be automatically scheduled for the next working day
* Printing shipping labels for UPS Freight Shipments in bulk
* Supported UPS Freight delivery options can be selected while generating labels
* Added Address Line 2 for the Shipper, Ship From, and Freight Third Party address

[Bug Fix]
* Shipping rates calculation when the cart subtotal is less than 1

## Version 3.16.0 – Released: September 11th, 2020

[Improvement]
* Commercial Invoice support for Satellite Countries
* Compatibility with WooCommerce Mix and Match Products plugin
* Compatibility with WooCommerce Checkout Add-Ons plugin
* Compatibility with WooCommerce v4.5

[Bug Fix]
* Fixed Company Name and Attention Name within the Shipper Address

## Version 3.15.9 – Released: August 13th, 2020

[Bug Fix]
* Fixed Tracking Number generation while generating packages automatically

## Version 3.15.8 – Released: July 28th, 2020

[Improvement]
* Improved shipping label printing as the image in bulk
* Improved the Display Labels in Browser option to display GIF labels in Portrait Mode for each order
* Improved shipping rates request with the address line 2 in the checkout page
* Added an option to display EDI in shipping labels for International Shipments

## Version 3.15.7 – Released: July 10th, 2020

[Improvement]
* Added shipping support for postal code in case of Sri Lanka, Saudi Arabia, Uruguay, and Vietnam

## Version 3.15.6 – Released: July 4th, 2020

[Improvement]
* Improved SurePost shipment tracking using UPS tracking numbers

[Bug Fix]
* Fixed the Product Level Fields not displaying for Simple and Variable product when WooCommerce Subscriptions plugin is active
* Fixed the shipping label not printing for multiple packages when Label Format 8.5x11 is selected

## Version 3.15.5 – Released: June 30th, 2020

[Improvement]
* Removed Special Characters from Access Point Names for Label Generation
* Updated the print label button text on the My Account page
* Updated Diagnostic Reports with new logs for Address Validation & Access Point Locator

[Bug Fix]
* Fixed SurePost and USPS Mail Innovation Label Printing for Label Format Laser 8.5x11

## Version 3.15.4 – Released: June 19th, 2020

[Improvement]
* Improved UPS Address Validation
* Added the check for address line 2 for Address Validation

## Version 3.15.3 – Released: June 9th, 2020

[New Feature]
* Added option to print Dangerous Goods Manifest for Hazardous shipments

[Improvement]
* Added option to remove special characters from Product Name while printing product details in Commercial Invoice
* Improved Language Translation for the tracking message sent in order completion mail

[Bug Fix]
* Shipping tab not displaying properly as Active

## Version 3.15.2 – Released: May 22nd, 2020

[New Feature]
* Mail Innovation Tracking using USPSPICNumber
* Added Option to display Product SKU on the UPS Shipping Label

[Improvement]
* Added Min Weight as 0.05 Kg for Metric Unit of Measurements

[Bug Fix]
* Estimated Delivery Date Display

## Version 3.15.1 – Released: May 2nd, 2020

[Improvement]
* For International Mail Innovation shipments, Mail Innovation Packaging type defaults to International Parcel option
* Option to select USPS Endorsement for Mail Innovation Shipments
* Compatibility of TIN Checkout Field with "Checkout Field Editor for WooCommerce"

## Version 3.15.0 – Released: April 30th, 2020

[Improvement]
* Option to select Caching Time for UPS Shipping Rates
* Option to select Packaging Type for Mail Innovation Services
* Usage of Billing Address TIN for ShipTo Address in the commercial invoice when customer's billing address is same as the shipping address

## Version 3.14.9 – Released: April 20th, 2020

[Improvement]
* Added special character support in case of Ship-To Postal Code
* Live UPS Shipping Rates will be cached for a day for improved performance
* Custom Checkout Fields like TIN, UPS Access Point, etc. can now be cleaned using WC Cleanup

## Version 3.14.8 – Released: April 2nd, 2020

[Improvement]
* Added support for UPS Access Point Economy for Poland
* Added Translation support for Tracking Details in My Account Page
* Added support for UPS Return Label for COD shipments

## Version 3.14.7 – Released: March 21st, 2020

[Improvement]
* Support for Variable Product Name in Shipping Label
* Auto Residential Address check using Address Classification Option

## Version 3.14.6 – Released: March 11th, 2020

[New Feature]
* Added Residential Delivery support for UPS Freight Shipments

[Improvement]
* Compatibility with WooCommerce v.4.0.0

## Version 3.14.5 – Released: March 9th, 2020

[Improvement]
* Added support for Adult Signature option while calculating shipping cost in the Orders page
* Improved Skip Product functionality
* Introduced Custom Scaling for displaying shipping labels in the browser window

## Version 3.14.4 – Released: February 18th, 2020

[Improvement]
* Improved Automatic Package and Label Generation
* Added option to print Billing Address on the UPS shipping label

[Bug Fix]
* Fixed missing Service Code for Freight Shipments while generating labels automatically

## Version 3.14.3 – Released: February 6th, 2020

[Improvement]
* Purchase Order Number will now be passed in BOL for UPS Freight Shipments
* Product Description with Quantity will be displayed in BOL for UPS Freight Shipments
* Added Higher Priority to the COD shipment label as compared to the Signature Confirmation in UPS shipping label
* Improved UPS Shipping Label generation for UPS Standard Boxes – UPS Letter, UPS 10kg Box & UPS 25kg Box

[Bug Fix]
* Fixed Company Name not displaying correctly in BOL for UPS Freight Shipments
* Fixed UPS Shipping Label not generating for a COD shipment with Shipper Release Indicator enabled in the plugin settings
* Fixed Estimated Delivery Month not getting translated

## Version 3.14.2 – Released: January 31st, 2020

[Improvement]
* Major UI Improvements – Setting Tabs for easy access and convenience
* Added Help & Support Section for Improved User Experience
* Added Filter Hook to support Custom Actions on Delivery Addon

[Bug Fix]
* Fixed Return UPS Shipping Label not getting generated in case Delivery Confirmation is Enabled
* Fixed Return UPS Shipping Label not getting generated from the USA to Canada & Puerto Rico

## Version 3.14.1 – Released: January 22nd, 2020

[Improvement]
* Added Country of Manufacture on Product Level
* Improved UPS Automatic Package & Label Generation
* Automatically identify COD Shipments & Generate UPS COD Shipping Labels

## Version 3.14.0 – Released: January 16th, 2020

[Improvement]
* Added option to set Origin Address at the Product level
* Calculate and get shipping rates on the Order Page for UPS GFP Shipments

[Bug Fix]
* Fixed Issue with Minimum and Maximum Weight Restriction for Shipping Rate Calculation & Label Generation

## Version 3.13.9 – Released: January 9th, 2020

[Improvement]
* Generate and Print UPS Ground with Freight Pricing (GFP) Shipping Labels for orders containing multiple packages

## Version 3.13.8 – Released: January 3rd, 2020

[Bug Fix]
* Fixed Label generation for GFP(Ground with freight pricing) when Ship From Different Address is enabled.

## Version 3.13.7 – Released: January 2nd, 2020

[Bug Fix]
* Delivery Confirmation included for Variable Products.

## Version 3.13.6 – Released: December 29th, 2019

[Improvement]
* Added option for customers to provide Tax Identification at checkout.
* Modification: Using Billing address for 'Sold to' Address & TIN details on the commercial invoice.
* Given the option to add Terms of Sale (Incoterm).

## Version 3.13.5 – Released: December 10th, 2019

[New Feature]
* Extensive compatibility with WooCommerce Bookings & Appointments plugin to support shipping for bookable products using Bookings UPS Shipping add-on

[Bug Fix]
* Fixed UPS Address Suggestions displaying multiple times on the cart and checkout page

## Version 3.13.4 – Released: November 30th, 2019

[Bug Fix]
* Fixed the First Shipping Method getting selected every time for a Commercial Address in case of UPS SurePost

## Version 3.13.3 – Released: November 15th, 2019

[Improvement]
* Improved Error handing when ZIPArchive and DOMElement classes are not enabled
* Improved plugin update functionality

## Version 3.13.2 – Released: October 14th, 2019

[Improvement]
* Support for Add More Shipping Fields (For Multi-Part Product) addon

## Version 3.13.1 – Released: October 11th, 2019

[Improvement]
* Handled UI issue with thank you page.

## Version 3.13.0 – Released: October 9th, 2019

[Improvement]
* Added Shipment Reference Number as Order Number in EEI Data Document.
* Handled return label packaging when forward labels are created using manual packaging options.
* Separate display of forward and return tracking numbers in 'My Accounts' page and email.

## Version 3.12.9 – Released: October 5th, 2019

[New Feature]
* Introduced feature to generate UPS EEI Data Document.

## Version 3.12.8 – Released: October 1st, 2019

[Improvement]
* Provided option in settings to display 'Shipper Release' text in label.

## Version 3.12.7 – Released: September 30th, 2019

[Improvement]
* Support for pre-packed products with Stack first packaging algorithm.

## Version 3.12.6 – Released: September 21st, 2019

[Improvement]
* Restrict Nafta based on origin and destination address.

[Bug Fix]
* Corrections related to PDF label display.

## Version 3.12.5 – Released: September 14th, 2019

[Improvement]
* Added option to exclude box weight from box selection algorithm for Volume Based Box Packing.
* Introduced option to select a reason for Export returns
* Introduced 'Laser 8.5x11' size for PNG Labels.
* Restricted character length to 35 in Address line field and 30 in City Field.

## Version 3.12.4 – Released: August 29th, 2019

[Improvement]
* Enabled Freight calculation in orders page for the button 'Calculate Shipping Cost'.
* Code changes to support integration with Shipment Tracking plugin(Provided option in Shipment Tracking plugin to update UPS tracking number).

## Version 3.12.3 – Released: August 19th, 2019

[New Feature]

## Version 3.12.2 – Released: August 14th, 2019

[New Feature]

## Version 3.12.1 – Released: July 30th, 2019

[Improvement]

## Version 3.12.0 – Released: July 27th, 2019

[Improvement]

## Version 3.11.9 – Released: July 11th, 2019

[Improvement]

## Version 3.11.8 – Released: July 9th, 2019

[Improvement]

## Version 3.11.7 – Released: July 3rd, 2019

[Improvement]

## Version 3.11.6 – Released: June 24th, 2019

[New Feature]

[Improvement]

## Version 3.11.5 – Released: June 14th, 2019

[Improvement]

## Version 3.11.4 – Released: June 10th, 2019

[New Feature]

## Version 3.11.3 – Released: June 3rd, 2019

[New Feature]

[Improvement]

## Version 3.11.2 – Released: May 24th, 2019

[Improvement]

## Version 3.11.1 – Released: May 17th, 2019

[New Feature]

[Improvement]

## Version 3.11.0 – Released: May 7th, 2019

[Improvement]

[Bug Fix]

## Version 3.10.15 – Released: April 29th, 2019

[Improvement]
* Improved French Translation

[Bug Fix]
* Fixed issue with Variable Products

## Version 3.10.14 – Released: April 28th, 2019

[Improvement]
* Remove Packages option for Generated Packages
* Customize Label Description based on Product Name, Category or Custom Text
* Option to remove Recipient Phone Number from Shipping Label
* Option to Enable/Disable UPS Address Suggestions

[Bug Fix]
* Fixed Some Notices while Creating Shipment

## Version 3.10.13 – Released: April 19th, 2019

[Improvement]
* Extensive support for WooCommerce – Store Exporter Deluxe plugin
* Extensive support for Estimated Delivery Date Adjustment and Auto-Label Generation for UPS Freight add-on

[Bug Fix]
* Fixed Label Printing for both Parcel and Freight together
* Fixed Blank Page while generating labels for Virtual Products

## Version 3.10.12 – Released: April 10th, 2019

[Improvement]
* PRO Number available for Freight Shipment Tracking

[Bug Fix]
* Fixed USPS Endorsement Number missing in Mail Innovations Services
* Fixed Return Label not generating when Generating Labels using Bulk Actions
* Fixed Shipment Description to have Product Title instead of Order ID
* Freight Services available for Auto-Label Generation under Default Services

## Version 3.10.11 – Released: April 4th, 2019

[Bug Fix]
* Fixed Label Generation for Multiple Freight Packages
* Fixed Bulk Label Printing Orientation issue for PDF format

## Version 3.10.10 – Released: April 2nd, 2019

[New Feature]
* Extensive support for UPS Ground with Freight Pricing

[Improvement]
* Included City Name while displaying UPS AccessPoint Locations

[Bug Fix]
* Fixed issues with Include Return Label option while generating packages
* Fixed SurePost Rates displaying for Commercial Address
* Fixed Discount not displaying in Commercial Invoice, now it will be reflected in the item cost
* UPS Shipping Label orientation for PNG format

## Version 3.10.9 – Released: March 22nd, 2019

[Bug Fix]
* Handling Multiple Tracking Numbers
* Support for UPS Density-Based Rating for UPS Freight

## Version 3.10.8 – Released: March 12th, 2019

[New Feature]
* Compatibility with Multi-Currency for WooCommerce
* Support for HazMat products

[Improvement]
* Option to Edit AccessPoint Location address in the Orders page
* Option to Add Packages Manually

[Bug Fix]
* Fallback rate not displaying
* Insurance Amount not added correctly while creating packages
* Bundle Products with Variable Products not displayed in Commercial Invoice
* HS Tariff Code not appearing in Commercial Invoice

## Version 3.10.7 – Released: January 28th, 2019

[New Feature]
* UPS Address Validation on the Checkout page
* Set Freight Classes in the backend

[Bug Fix]
* Commercial Invoices for Bundled Products

## Version 3.10.6 – Released: January 4th, 2019

[New Feature]
* Choose from UPS Services to Print Return Labels
* Support for Minimum Weight required by UPS in Israel
* WooCommerce Multiple Address plugin compatibility

[Improvement]
* Updated Language Translation-German & French
* Access Point Language Translation
* Shipping Rates Debug Data will be written in Logs file (file name Ph_UPS_Shipping)
* WooCommerce Bundle Product Compatibility improved
* Option to Enable/Disable UPS Tracking Details in WooCommerce Order Complete Email
* Single package for Freight Shipments
* Checking Commercial Invoice for EU
* Insurance Status is now available in Order Notes if Insurance is Enabled
* Other Code Improvements

[Bug Fix]
* Warnings in Woocommerce 3.5
* Sending Labels to the customer if the Shipper and Vendor are selected
* HST not displaying in Commercial Invoice
* Shipping Method not displaying in Orders Page due to Estimated Delivery Date getting enforced
* Displaying multiple/duplicate Estimated Delivery Date

## Version 3.10.5 – Released: November 2nd, 2018

[Improvement]
* Restricted character length to 35 in Attention Name and Company Name for Label Printing as per UPS Standard.
* Implemented a Freight Billing Option(Prepaid and Third Party) on the settings page.
* Implemented Freight Weekend Pickup Option for Real-time rates.
* Compatibility with Woocommerce Multicurrency plugin.
* Limited Shipment description field to 35 characters for domestic shipments(as per new UPS changes).
* Adding description in the label for domestic US shipments as per the new UPS update.
* Provided Option to select Check/Cash for COD – Only for European Countries.
* Latin encoding enhancement.
* Introduced Cyrillic character translation.
* COD currency for European countries.
* Improved algorithm to allow Rounding of dimensions to 6 decimal places for products to be accommodated in the boxes.
* Control Log Receipt Feature - When forward shipments' declared value is between $999 and $50,000 USD.
* Option to add Recipients Tax Identification Number (International Shipments).
* NAFTA Certificate Feature for International Shipments (North American Free Trade Agreement Certificate of Origin).
* Changed UPS COD Label Currency To Order Currency.
* Improved Latin Encoding.
* Implemented UPS Taxes feature for General list rates.
* Changed UPS Invoice Currency to Order Currency.
* Return Commercial Invoice.
* HazMat Support for variation product.
* MRN Number implementation for shipments from Germany for orders over 1000 Euros.
* Incorporated Technical Name and Additional description options in UPS Hazmat.
* Option to add product name/category/custom description in commercial invoice.
* Reset 'Duties and Taxes' payer value to 'Receiver' by default.
* Compatibility with WooCommerce Subscriptions plugin.
* Improved Label display in PDF – Height adjustment.
* Packing algorithm enhanced.
* Added Duties and Taxes Payer option.
* Added Option to Include Order Id in Label Description.

[Bug Fix]
* Handling special characters in company/attention name.
* Removed special character from tracking number on the email.
* Fixed Label Downloading Issue for different file formats.
* Minor Bug Fixes.

## Version 3.10.4 – Released: September 13th, 2018

[Improvement]
* Option to modify estimated delivery text.
* Implemented Estimated Delivery for freight rates.
* Added pot file for translation.
* Improved text for license manager.
* Handled space in API keys and email.

## Version 3.10.3 – Released: September 7th, 2018

## Version 3.10.2 – Released: August 28th, 2018

[Improvement]
* Introduced an option to allow null value(in-service selection) for the generation of labels.
* Enhancement in the freight rate calculation.

## Version 3.10.1 – Released: August 22nd, 2018

[Improvement]
* Estimated Delivery showed on the order page
* Automatic label generation improvement.

## Version 3.10.0 – Released: August 9th, 2018

[Improvement]
* Debug Information has been refined
* Allowed the shipping service title to be displayed when the cheapest cost is shown.

## Version 3.9.17 – Released: July 12th, 2018

[Improvement]
* Improvements in API manager.
* Enhanced the support for bundled product plugin by Woothemes.

[Bug Fix]
* Estimated delivery correction for international shipments.
* Removal of virtual products from Commercial invoice.

## Version 3.9.16 – Released: June 20th, 2018

[Improvement]
* UPS API updated according to 2018 documentation.

## Version 3.9.15 – Released: June 15th, 2018

[Improvement]
* Estimated delivery option.
* Volumetric weight option
* Bulk label printing in pdf and image format
* Option to send the label to shipper and customer.
* Option to provide custom message in the email

[Improvement]
* Compatible with Woocommerce 3.4.
* WooCommerce UPS Integration with WooCommerce Composite Products.
* WooCommerce UPS Integration with WooCommerce Bundle plugin.
* Introduced Automatic label generation on Thank You page.
* Service code 74 added in the plugin

[Bug Fix]
* Delivery Confirmation correction for US and PR
* Handling of Special characters.
* UI enhancements

## Version 3.9.14 – Released: April 17th, 2018

[Improvement]
* Support for Dokan Multi-Vendor.
* Support for product weight and dimension divider addon.

[Bug Fix]
* Case of an adjustment getting applied in order page
* Case of conversion rate not getting applied to backend rates.

## Version 3.9.13 – Released: March 29th, 2018

[Improvement]
* HS tariff code implementation at the product level.

[Improvement]
* PO number displayed in the Commercial invoice
* Weight-based packing algorithm made available for Freight Shipments.
* Introduced a mechanism to divide the Access Point Address into Address 1 and Address 2.
* Case related to default services getting priority over Customer selected services.
* Correction related to the display of Surepost rates.

## Version 3.9.12 – Released: March 1st, 2018

[Improvement]
* Can configure Direct delivery options at the product level.
* Automatic label generation using a default service in the case when free shipping is offered.

[New Feature]
* Option to see the shipping rates before generating the label on the admin order page.
* Show Product details in each box before printing labels.

[Bug Fix]
* Automatic label generation restricted to order status processing only.
* Compatible with PHP Version 5.5 and before.
* Enhancement in Surepost & Freight services.
* Enhancement in the SSL connection.

## Version 3.9.11 – Released: January 29th, 2018

[Improvement]
* Restricted Email notification for eligible services only.
* Sending single requests instead of sending separate requests for each service.
* Changed Order Id to Order number on Shipping label, Added pot file, and updated German translation

[New Feature]
* Option to give insurance amount at the product level
* CompanyName character length fixed to 35( outbound label) and 30(return label), Warning fixed when freight mode is enabled
* Fatal error due to box packing if no box is specified or item doesn't fit into boxes
* Fatal error in the older versions of WooCommerce (up to 3.0) if automatic label generation is enabled.

## Version 3.9.10 – Released: January 28th, 2018

[Improvement]
* Added a new filter for conversion rate.

## Version 3.9.9 – Released: January 24th, 2018

[Improvement]
* Option to Print Pickup debug information.

## Version 3.9.8 – Released: November 17th, 2017

[Improvement]
* Option to choose default service for Domestic and International shipping.

## Version 3.9.7 – Released: November 10th, 2017

[New Feature]
* Swap the origin and destination address if the origin address preference selected shipping
* Made Compatible with 'XA-shipping-common-addon' plugin.

[Bug Fix]
* Enhancements in box packing

## Version 3.9.6 – Released: November 8th, 2017

[Improvement]
* Made compatible to have access point field on the checkout page.

## Version 3.9.4 – Released: November 2nd, 2017

[Improvement]
* Enhanced the rate and label portion.

## Version 3.9.3 – Released: October 18th, 2017

[Bug Fix]
* Fixed Automatic label generation is not working.

## Version 3.9.2 – Released: October 9th, 2017

[Bug Fix]
* Made compatible with special characters
* Organised the flow of characters when exceeding the limit on the commercial invoice.
* Rollback of Ground Freight Pricing.

## Version 3.9.1 – Released: September 12th, 2017

[Bug Fix]
* Enhanced Pickup to be generated at Package level instead of Product level.

## Version 3.9.0 – Released: August 28th, 2017

[New Feature]
* New feature: Email notification to sender and recipient.

[Bug Fix]
* Issue related to Ground Freight API.

## Version 3.8.11 – Released: August 5th, 2017

[Bug Fix]
* Conflict with the basic version.

## Version 3.8.10 – Released: August 2nd, 2017

[New Feature]
* Introduced Freight ground as a new service.

[Bug Fix]
* Display of Access point details in order page.

## Version 3.8.9 – Released: July 25th, 2017

[Bug Fix]
* Display of Packing algorithm dropdown

## Version 3.8.8 – Released: July 11th, 2017

[New Feature]
* Added Ground Freight option.

## Version 3.8.6 – Released: July 7th, 2017

[Improvement]
* Added option to show only enabled services on the order admin page

## Version 3.8.5 – Released: July 7th, 2017

[Improvement]
* Added option to select different services for the return shipment.

## Version 3.8.4 – Released: July 6th, 2017

[Bug Fix]
* Case when no rates are returned from API.

## Version 3.8.3 – Released: June 21st, 2017

[Improvement]
* Implemented Declaration Statement within the commercial invoice.
* State code for country Ireland.

[Bug Fix]
* Case of Shipment services not showing.

## Version 3.8.2 – Released: June 19th, 2017

[Improvement]
* Fixed print label is not working with Access Point Locator order.
* Email notification with APL label.
* Added email address with shipper and recipient address

## Version 3.8.1 – Released: June 9th, 2017

[New Feature]
* Added Freight Shipment Support.

[Bug Fix]
* Case related to creating a shipment.

## Version 3.7.7 – Released: June 6th, 2017

[Improvement]
* Introduced the 'Reason for Export' option for International shipment
* Introduced option to set working days on pickup
* Introduced New box packing algorithm.

[Bug Fix]
* Case related to PLT
* Case related to Access Point Locator

## Version 3.7.4 – Released: June 2nd, 2017

[Bug Fix]

## Version 3.7.2 – Released: May 31st, 2017

[Bug Fix]
* Latin encoding support.

[New Feature]
* Tax Identification Number.

## Version 3.7.1 – Released: May 26th, 2017

[Bug Fix]
* Conflict with FedEx in Automatic Label Generation

## Version 3.7.0 – Released: May 24th, 2017

[New Feature]
* Automatic Label Generation.

## Version 3.6.9 – Released: May 17th, 2017

[Bug Fix]
* Compatibility Fix for Other Shipping Plugin.

## Version 3.6.8 – Released: May 12th, 2017

[Improvement]
* New Algorithm (Based on Volume Used * Item Count)

## Version 3.6.7 – Released: May 11th, 2017

[Improvement]
* 'CustomerClassification' for non-US countries.

## Version 3.6.6 – Released: May 10th, 2017

[Improvement]
* Updated the language translations.
* Updated Customer Classification with new values
* Displayed full address of Access Point Locator (APL) (in my account page and order page).

[Bug Fix]
* Case related to label generation.

[New Feature]
* PLT for commercial invoice.

## Version 3.6.5 – Released: May 9th, 2017

[Bug Fix]
* Case related to the pre-packed product on variation level.

## Version 3.6.4 – Released: May 4th, 2017

[Improvement]
* Implemented pre-packed at variation level.

## Version 3.6.3 – Released: April 30th, 2017

[Bug Fix]
* Compatibility with an older version of PHP.

## Version 3.6.2 – Released: April 30th, 2017

[Bug Fix]
* Compatibility of Access Point Locator with WC 3.0+.

## Version 3.6.1 – Released: April 25th, 2017

[Bug Fix]
* Compatibility of Access Point Locator with WC 3.0+.

## Version 3.6.0 – Released: April 25th, 2017

[Improvement]
* Printing billing phone number for both billing and shipping.

## Version 3.5.9 – Released: April 20th, 2017

[Improvement]
* Applied filter for tracking message translation in customer email.

## Version 3.5.8 – Released: April 20th, 2017

[Bug Fix]
* Case related to return label fixed.

## Version 3.4.8 – Released: April 7th, 2017

[Bug Fix]
* Case related to variable products' weight and dim.

## Version 3.4.7 – Released: April 6th, 2017

[Bug Fix]
* Case related to the enhancement of InvoiceLineTotal node.

## Version 3.4.6 – Released: April 6th, 2017

[Bug Fix]
* Related to a compatibility issue with WC 3.0

## Version 3.4.5 – Released: April 5th, 2017

[Improvement]
* Updated filter of packages on label requests.

## Version 3.4.4 – Released: March 31st, 2017

[Improvement]
* Introduced Different services for different packages on the order page.

## Version 3.4.3 – Released: March 30th, 2017

[Bug Fix]
* Insurance removed from Sure Post services.

## Version 3.4.2 – Released: March 23rd, 2017

[Bug Fix]
* Case related to conflict with other plugins.

## Version 3.4.1 – Released: March 22nd, 2017

[Improvement]
* Added filter for change product details.

## Version 3.4.0 – Released: March 17th, 2017

[Improvement]
* Compatibility with WC 2.7.

## Version 3.3.5 – Released: March 13th, 2017

[Improvement]
* Enhancement for altering shipment description.

## Version 3.3.3 – Released: March 12th, 2017

[Improvement]
* Minor Content changes

## Version 3.3.1 – Released: March 12th, 2017

[New Feature]
* Introduced Pre-packed package(It will treat the pre-packed product as a separate package).

## Version 3.3.0 – Released: March 10th, 2017

[Improvement]
* Increased size of Package box fields.

## Version 3.2.9 – Released: February 3rd, 2017

[Improvement]
* Box Maximum Weight label changed to Max Package Weight.

## Version 3.2.8 – Released: January 30th, 2017

[Bug Fix]
* Case of COD with box packing option.

## Version 3.2.7 – Released: January 18th, 2017

[Improvement]
* Added option to change the encoding to Latin.
* Modified generate a package to generate the package for the empty package and enable the user to generate labels for order with the item having no length, width, height, and weight by providing them during label generation manually.

## Version 3.2.6 – Released: January 14th, 2017

[Bug Fix]
* Case related to commercial invoice.

## Version 3.2.5 – Released: January 12th, 2017

[Improvement]
* Case related to Access Point Locator.

## Version 3.2.4 – Released: January 6th, 2017

[Improvement]
* Bug Fix for taking previously-stored access point location.

## Version 3.2.3 – Released: December 29th, 2016

[Improvement]
* Added Address line1 with Rate Request.

## Version 3.2.0 – Released: December 19th, 2016

[Improvement]
* Added tax option in shipping rates.

## Version 3.1.9 – Released: December 16th, 2016

[Bug Fix]
* Case related to COD for European countries.
* Case related to the tracking number.

## Version 3.1.8 – Released: December 15th, 2016

[Bug Fix]
* Case related to Method Availability field.

## Version 3.1.7 – Released: December 8th, 2016

[Improvement]
* Updated readme.txt file.

## Version 3.1.6 – Released: December 8th, 2016

[Bug Fix]
* Compatability issue with older WC version(below 2.6).
* Case related to COD.

## Version 3.1.4 – Released: December 1st, 2016

[Improvement]
* Added filter to create shipment data.

## Version 3.1.2 – Released: November 22nd, 2016

[Improvement]
* Added language support for 'French, German, Italian, Spanish.
* Added minimum order price option and Auto accept of shipment.

## Version 3.1.1 – Released: November 17th, 2016

[Improvement]
* Added label printing buttons to order listing page.

## Version 3.1.0 – Released: November 16th, 2016

[Improvement]
* Correction on the AccessPoint selection problem.

## Version 3.0.9 – Released: November 14th, 2016

[Improvement]
* Updated state code feature for the US and Canada only.

## Version 3.0.7 – Released: November 4th, 2016

[Bug Fix]
* Corrected problem in Generate Package.

## Version 3.0.6 – Released: November 3rd, 2016

[Bug Fix]
* Case related to SurePost weight unit.

## Version 3.0.5 – Released: October 28th, 2016

[Improvement]
* Omitted residential address indicator when the destination is UPS access point.

## Version 3.0.4 – Released: October 24th, 2016

[Improvement]
* Improvements on box packing.

## Version 3.0.3 – Released: October 21st, 2016

[Improvement]
* Added different service option for each package while generating label
* Introduced Bulk shipment creation.

## Version 3.0.2 – Released: October 4th, 2016

[New Feature]
* Added Access Point Locator.

## Version 3.0.1 – Released: September 22nd, 2016

[Improvement]
* Added Order Id in shipment description and excluded insurance value from SurePost request.

## Version 3.0.0 – Released: September 19th, 2016

[Improvement]
* Introduced API Manager settings page link

[Bug Fix]
* Case related to insurance value.

## Version 2.9.9 – Released: September 9th, 2016

[Improvement]
* Added Currency Code.

## Version 2.9.8 – Released: August 30th, 2016

[Improvement]
* Incorporated Commercial Invoice.

## Version 2.9.7 – Released: August 25th, 2016

[Improvement]
* Extra manual packages can be added while creating a shipment.

## Version 2.9.6 – Released: August 25th, 2016

[Bug Fix]
* Case related to Pickup code.

## Version 2.9.5 – Released: August 22nd, 2016

[Improvement]
* Adult signature implemented.
* ISO charset applied to confirm shipment request.

## Version 2.9.4 – Released: August 19th, 2016

[Improvement]
* Included all Pickup related fields to advanced settings.

## Version 2.9.3 – Released: August 19th, 2016

[Improvement]
* Pickup option added.

## Version 2.9.2 – Released: August 11th, 2016

[Improvement]
* Added new filter to alter account details in this version.

## Version 2.9.1 – Released: August 10th, 2016

[Improvement]
* Stability Improvements.

## Version 2.9.0 – Released: August 5th, 2016

[Improvement]
* Added Advanced settings section,
* Added SSL verify settings,
* Upgraded admin notice.

## Version 2.8.9 – Released: August 4th, 2016

[Bug Fix]
* Case related to conflict with the basic version.

## Version 2.8.7 – Released: August 3rd, 2016

[Bug Fix]
* Weight-based shipping. Enhanced API manager error handling.

## Version 2.8.6 – Released: July 29th, 2016

[Bug Fix]
* Case related to API Manager.

## Version 2.8.5 – Released: July 22nd, 2016

[Improvement]
* Filter for skipping products in the cart.

## Version 2.8.4 – Released: July 21st, 2016

[Improvement]
* Changed the extension of ZPL files to ZPL from txt.

## Version 2.8.3 – Released: July 18th, 2016

[Bug Fix]
* Case related to manual dimension field conflict with stamps/USPS.

## Version 2.8.2 – Released: July 11th, 2016

[Bug Fix]
* API manager issue.

## Version 2.8.1 – Released: July 9th, 2016

[Improvement]
* Multiple Manual packaging and

[Bug Fix]
* Case related to API manager.

## Version 2.8.0 – Released: July 5th, 2016

[Improvement]
* Stability Improvements.

## Version 2.7.9 – Released: July 4th, 2016

[Bug Fix]
* Issue with respect to deactivation of license.

## Version 2.7.8 – Released: July 4th, 2016

[Improvement]
* Improvement of license key implementation.

## Version 2.7.7 – Released: July 4th, 2016

[Improvement]
* Implemented license keys.
* Automatically update the plugin from WordPress admin.

## Version 2.7.6 – Released: July 4th, 2016

[Improvement]
* Added filter for the rate to incorporate snippet for adjusting price based on states.

## Version 2.7.5 – Released: June 28th, 2016

[Bug Fix]
* Woocommerce Compatibility update for version 2.6.0.

## Version 2.7.4 – Released: June 10th, 2016

[Improvement]
* Enabled Saturday delivery.

## Version 2.7.3 – Released: June 9th, 2016

[Improvement]
* Fixed problem to display exact error message returned API while creating the label.

## Version 2.7.2 – Released: June 9th, 2016

[Improvement]
* Added PAK option.

[Bug Fix]
* Case related to Shipment label generation while creating order from admin panel.
* Case related to invalid create shipment request.

## Version 2.7.1 – Released: May 25th, 2016

[Improvement]
* Added new filter to confirm shipment request.

## Version 2.7.0 – Released: May 24th, 2016

[Bug Fix]
* Fixed dimension error for box packing.

## Version 2.6.9 – Released: May 18th, 2016

[Improvement]
* New services added.

## Version 2.6.8 – Released: April 29th, 2016

[Improvement]
* Introduced Label formats ZPL and EPL.
* Stability improvements.

## Version 2.6.4 – Released: April 18th, 2016

[Improvement]
* Weight Based Packing feature is introduced.

## Version 2.6.1 – Released: March 3rd, 2016

[Improvement]
* Allowing an empty Ship-to Company Name while label printing.
* Default option for Consumer Classification Code.

## Version 2.6.0 – Released: February 26th, 2016

[Improvement]
* UX tweaks on UPS Settings page.
* Default option for Consumer Classification Code.

## Version 2.5.9 – Released: February 18th, 2016

[Bug Fix]
* Fixed the address related issue while printing the return label.

## Version 2.5.8 – Released: February 11th, 2016

[Improvement]
* New Feature for UPS Weight based shipping.

## Version 2.5.6 – Released: February 8th, 2016

[Improvement]
* More accurate negotiated rates while showing real-time rates.
* Added option to choose Customer Classification Code.

## Version 2.5.5 – Released: February 2nd, 2016

[Improvement]
* UPS SurePost is now supported.

## Version 2.5.3 – Released: January 25th, 2016

[Bug Fix]
* Fixed an error while the remote call to UPS API.

## Version 2.5.2 – Released: January 18th, 2016

[Improvement]
* Introduced Collect on Delivery (CoD) Feature.
* Introduced Return Label Feature.

## Version 2.4.3 – Released: January 10th, 2016

[Improvement]
* Fixed issue with negotiated rates while print label.

## Version 2.4.2 – Released: December 15th, 2015

[Improvement]
* Introduced Feature to display the label in the browser
* Introduced settings toggle to turn on the feature.
* This feature can be used to deal with the issue in which the downloaded file is getting corrupted because of PHP BOM.

[Bug Fix]
* Fixed inverted PNG image issue.

## Version 2.3.15 – Released: November 3rd, 2015

[Improvement]
* Email tracking introduced for order competition mail.

[Bug Fix]
* Fixed the issue while shipping to countries without a postcode.

## Version 2.2.2 – Released: July 30th, 2015

[Improvement]
* Introduced option to enter manual dimensions for label printing. Print labels even though product dimensions are not set.
* Admin toggle for turning on this feature.
* Service selection combo for label printing.
* Generate label using UPS even for those orders without UPS as the shipping method.

## Version 2.2.0 – Released: July 15th, 2015

[Improvement]
* Automatic Shipment Tracking for Both Customer and Admin.
* Admin Turn off tracking option only for customer side (default) as well as complete tracking feature.
* Tracking is integrated with creating label feature.

## Version 1.3.0 – Released: June 20th, 2015

[Improvement]
* Introduced phone number field in ups admin settings.

[Bug Fix]
* Fixed an issue with the label printing

## Version 1.2.1 – Released: May 27th, 2015

[Improvement]
* UI tweaks especially while showing messages.
* Label Printing in GIF and PNG.
* Support for ~4x6 size.

## Version 1.0.0 – Released: May 13th, 2015

[Improvement]
* Admin configuration to switch between the live and test environment.
* Label Printing.

## Version 1.0 – Released: April 28th, 2015

[Improvement]
* Dynamic Shipping Rates.
