Moneris
=======

Moneris is a Splynx add-on. It's used to pay invoices and proforma invoices with _Moneris Payment Gateway_ -  [https://www.moneris.com/](https://www.moneris.com/).

## Installation

You can install splynx-moneris via Linux shell or via web-interface.

### Installation via Linux shell

Use following commands:

```bash
apt-get update
apt-get install splynx-moneris
```

### Installation via web-interface

 Info: <icon class="image-icon">![(info)](information.png) This installation method is available only for Splynx versions ≥ 2.1.

* Open _Config / Integrations / Add-ons_  
  ![(image)](install.png)

* Click _Update (apt)_, then _Refresh_, then install.
### Configuration

After installation, add-on should be configured. Open _Config / Integrations / Modules list_:

![(image)](modules_list.png)

![(image)](edit_module.png)

### Settings

![(image)](settings.png)
![(image)](settings2.png)

**API domain** - Splynx URL.  
**API key**, **API secret** - default values. Don't change them without need.  
**Splynx URL** - Splynx URL.  
**Payment method** - when customer pays by using this add-on, the payment will be with this payment type.  
**Group of bank statements** - Group bank statements (_Finance / Bank Statements / History_) monthly or daily.  
**Service fee to**:
* Payee - customer won't pay Additional service fee.
* Additional service fee - customer will pay Additional service fee.
**Additional service fee** - if **Service fee to**=_Additional service fee_, here you have to specify_Additional service fee_ percent.  
**Fee message** - _Additional service fee_ description.  
**Fee VAT** - _Additional service fee_ VAT percent.  

**Transaction fee category** - [transaction category](configuration/finance/transaction_categories/transaction_categories.md) of the _Additional service fee_.
<icon class="image-icon">![(warning)](warning.png)</icon> It is used only for [proforma invoices](finance/proforma_invoices/proforma_invoices.md). For [invoices](finance/invoices/invoices.md) _Additional service fee_ category is always _Service._

These settings can be different for each [partner](administration/main/partners/partners.md):
**Select Country** - country.
**Select payment currency** - currency.
**Store Id**, **API token**, **HT Profile ID** - these values you can find in Moneris portal.

## Payment process

After successful configuration, customers can pay their invoices using Moneris system in _Finance / Invoices_:

![(image)](portal_pay_invoice.png)

![(image)](portal_pay_invoice_1.png)

![(image)](6.png)

If everything went well, you will see status of invoice as "Paid" (portal and admin).
