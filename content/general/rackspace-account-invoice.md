---
node_id: 4218
title: Rackspace account invoice
type: article
created_date: '2014-09-01'
created_by: Kenny Johnston
last_modified_date: '2015-08-10'
last_modified_by: Nate Archer
product: undefined
product_url: undefined
---

Your monthly Rackspace account invoice includes account and billing
information, payment information, tax information, and summaries of your
service, promotions, and discounts. This article provides a detailed
description of each page and field in your PDF or CSV invoice.

### Recent changes

The invoice format has been improved. The information on your invoice is
now better summarized to eliminate an excessively long invoice. Your
invoice now also provides a **Service Summary**.

### Billing and account information

The first page of your invoice contains a detailed overview of your
account and billing information.

<img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/832-2.png" width="416" height="128" />

### Account summary

The bottom portion of the first page of your invoice includes the
following information:

-   **Previous Balance** - The amount billed before current invoice
-   **Payments** - The total of payments received during your last bill
    cycle
-   **Adjustments** - The total of any debits or credits from your last
    billing cycle
-   **Balance Forward** - The unpaid charges from your last bill cycle
-   **Current Invoice Charges** - The sum of all charges incurred since
    the prior bill
-   **Current Invoice Taxes** - Taxes applied based on net charges
    (Current Invoice Charges) based on the type of service and customer
    location
-   **Total Amount Due** - The total of your Current Invoice Charges
    plus any Balance Forward amount
-   **Payment Terms** - Indicates when your payment is due
-   **Remit Section** (if applicable) - Please detach and send with your
    payment

<img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/832-2a.png" width="688" height="136" />

### Service summary

The second page of your invoice is a summary of all support, product,
and other charges, and is organized as follows:

-   **Billing period** - The date range for this invoice, located
    directly below the page number
-   **Service** - Support, product, or other charges applied on your
    current bill, including a descriptive name of the product or charge
-   **Gross Charge** - The total charge accumulated by product or other
    charge categories before promotions and discounts
-   **Promotion & Discount** - The promotions and discounts associated
    with a product charge
-   **Net Charge** - The difference between Gross Charge and Promotion &
    Discount for a product charge; the pretax amount for a product
    charge; the pretax amount for a product charge
-   **Taxes** - The taxes calculated based on the net charge
-   **Total Charges** - The sum of the net product charge and the taxes
    for a product

<img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/832-3.png" width="684" height="591" />

Although most of the service summary items are self-explanatory, there
are two services that warrant additional description:

-   **Cloud Servers** - The Cloud Servers service line includes all
    Cloud Servers flavor classes, for example First Gen, Next Gen, and
    OnMetal
-   **Cloud Bandwidth** - The Cloud Bandwidth service line includes both
    Public and CDN Bandwidth

### Adjustment summary

The second page of your invoice also includes any adjustments that
occurred during the billing period.

-   **Type** - The reason for the adjustment (debit or credit) on your
    bill
-   **Reference ID** - The Rackspace generated unique ID for the
    adjustment
-   **Adjustment Date** - The date that the adjustment was processed by
    Rackspace
-   **Description** - Any details of the adjustment
-   **Net Amount** - The pre-tax amount of the adjustment
-   **Taxes** - The calculated tax amount based on the net amount of the
    adjustment
-   **Total Amount** - The sum of Net Amount and Taxes for an individual
    adjustment

<img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/832-3a.png" width="757" height="154" />

### Promotion and discount summary

The third page of your invoice provides a summary of the promotions and
discounts for the billing period.

-   **Category and Description** - The name and description of the
    promotions and discounts being applied to your bill
-   **Net Discount** - The total of all the promotions and discounts
    applied to your bill

<img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/832-5.png" width="724" height="281" />

### Tax summary

The **Tax Description** explains, in detail, the taxes being applied to
your bill.

<img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/taxsummary.png" width="731" height="198" />

### Goods and services tax

The following pages apply only if you are assessed a Goods and Services
Tax (GST). They show the aggregate product charges broken down into
taxable (T) and non-taxable charges for the given billing period.

<img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/832-6a.png" width="731" height="288" />

<img src="https://8026b2e3760e2433679c-fffceaebb8c6ee053c935e8915a3fbe7.ssl.cf2.rackcdn.com/field/image/832-8.png" width="730" height="343" />

### Invoice Details Document (CSV)

The CSV document shows a detailed view of your daily usage activity that
occurred during the course of your billing cycle. Each row contains a
daily usage item and an associated charge. It also shows a breakdown of
your charges in three different views. For example:

-   To see charges summarized across the entire billing cycle related to
    a given resource, you can create a PivotTable on the RES_ID column
-   To see charges summarized across the billing cycle related to a
    given service, you can create a PivotTable on the SERVICE_TYPE
    column
-   To see charges summarized across the billing cycle related to a
    given data center, you can create a PivotTable on the DC_ID column

### CSV column description

-   **ACCOUNT_NO** - Customer account number
-   **BILL_NO** - Invoice number
-   **BILL_START_DATE** - Start date of the billing cycle
-   **BILL_END_DATE** - End date of the billing cycle
-   **SERVICE_TYPE** - Service or product name (for Tax it will
    display ACCOUNT)
-   **EVENT_TYPE** - Sub-type for each service or product
-   **EVENT_START_DATE** - Start date and time of the usage or
    activity
-   **EVENT_END_DATE** - End date and time for the usage or activity
-   **IMPACT_TYPE** - Signifies whether the event is a CHARGE or a
    DISCOUNT
-   **QUANTITY** - Total quantity of the event measurement
-   **UOM** - Unit of measure for the quantity and event measurement
-   **RATE** - Rate applied for this event
-   **AMOUNT** - Charge applied based on RATE and QUANTITY
-   **USAGE_RECORD_ID** - Unique system generated ID for the event and
    charge
-   **DC_ID** - Data center
-   **REGION_ID** - Geographical region
-   **RES_ID** - Unique resource ID
-   **RES_NAME** - Customer-provided resource name
-   **ATTRIBUTE 1** - Resource attribute; for Cloud Servers, this
    provides the Flavor Name
-   **ATTRIBUTE 2** - Resource attribute; for Cloud Servers, this
    provides the Option Name
