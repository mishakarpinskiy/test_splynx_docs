Netcash Debit Order (formerly SagePay direct debit)
====================

**Netcash Debit Order is a Splynx add-on (previously SagePay direct debit).It's used to generate debit orders and is processed via https://netcash.co.za/**

To install Netcash Debit Orders navigate to **Config → Integrations → Add-ons:**

![addons icon](addons_icon.png)

![install](install.png)
Install the add-on with commands from terminal:

or it can be installed from terminal:

```
apt update
apt install splynx-netcash-debit-order
```

**After that you need to registrate on [Netcash portal](https://netcash.co.za/) and configure your account.**

When the installation has completed, you need to register with Netcash and configure your account:

Account service key:
![acc_service key](account_service_key.png)

Debit orders service key:
![do service key](service_key.png)

PCI vault key:
![pci vault key](vault_key.png)

And merchant account number.


These values have to be added into **Config → Integrations → Modules list -> Netcash** :
![modules_list.png](modules_list.png)

![edit_module.png](edit.png)

![settings1.png](settings_1.png)
****PCI vault key - this key is only needed when customers use their own credit cards to pay.****
![settings2.png](settings_2.png)

You can also set service and unpaid fees for customers and set which admins roles have access via the admin panel.
Also admins can be notified when a customer has created a Netcash payment account - to enable it use "Notifications settings".

To add a Netcash payment account navigate to the customer's "Billing" tab and click on the card icon on Payment accounts window. Recommended method - using card icon to add account with validation.

![add account.png](add_account_from_admin.png)

here the admin can add a Netcash payment account for the customer with provided bank account or credit card details.

Also a payment account can be added by clicking on the "+" button, however this will bypass the Netcash validation procedure.

When customers have Netcash payment accounts configured, the admin can charge their invoices all at once.

This is the concept which will allow us to run debit orders.

![charge1.png](invoices_charge.png)

Invoices can be charged by full invoice amount or by customer balance:

![charge1.png](charge.png)

![charge balances.png](charge_balances.png)

If you charge the invoices using the “Netcash_balance” charge handler the customer will be charged not according to an invoice amount, but with the amount outstanding on the customer’s account. Example: A customer has an invoice with amount 10 in the current month, but the balance of the account is -100 (the customer didn't pay for 10 months) in this case the customer will be charged with the amount 100 and not 10. Be very attentive when using the “Netcash_balances” charge handler.


Once charged, Splynx will create and send the debit batch file with payment details to  [*https://netcash.co.za/*](https://netcash.co.za/) When the file is received in Netcash, you should select the correct batch type, either “two day” or “sameday” as well as the action date. The last step is to click on authorize and complete the procedure, after which Netcash process the file on the selected action date.


Splynx will send two request per day (00:15 and 12:15) to Netcash via a cron job to retrieve the payments from Netcash. This will auto allocate the payments and update the invoice status to “paid”. You can also manually run the check payments for any historic date by using the “*Netcash debit order check payments*” in the finance menu:

![check payments](check_payments.png)

The charge history can be observed under the "Charge history" tab:

![history](charge_history.png)

A file record with charged invoices can be downloaded or deleted.

The process of invoice charging can be automated. To achieve this, the admin should add a "Auto charge filter":

![auto charge](add_auto_charge.png)

Be vigilant when creating this filter as it will process the charge without any human intervention.

### Customer portal widgets (entry points)

After installing the Netcash Debit order addon, customers are able to pay their invoices directly from their portal page using widgets.

The first step is to enable widgets (entry points) in the module config:

![edit_module.png](edit.png)

![enable widget](enable_entry_point.png)

![edit widgets](edit_entry_point.png)

Here widgets can be enabled/disabled and updated by partner or location value to make this widget available only for specific partners or locations.

![entry point](entry_point.png)

Once it's enabled let's navigate to the customer portal:

![widget1](widget1.png)

The first entry point allows the customer to pay their invoices on the dashboard of the customer portal.

Another entry point allows payment for a specific invoice under  **Finance -> Invoices**:

![widget2](widget2.png)

The customer can also view, update or remove Netcash account details here:

![edit_module.png](customer_pay_creds.png)

**Note** if the customer pays their invoices using Netcash Debit Order in the portal a new bank statement will be created in the admin portal (**Finance/Bank statements/History**). We use bank statements in Splynx to track and allocate payments to the correct invoices once retrieved.

### Admin page widgets and log files

Netcash logs can be found under **Administration/Logs**:

![logs](administration_logs.png)

In general logs, different records can be observed like when a statement was created, when payments were processed etc:

![general logs](general_logs.png)

and under charge logs only logs regarding charges can be found:

![charge logs](charge_logs.png)

We have created a tool which we use to import account details from the Netcash Master file or any other CSV with the relevant details. We simply require an identifier to match the payment record in the document to the customer on Splynx eg. an account/reference number or customer name. This tool can be found under **Config -> Tools**:

![import tool](import_tool.png)

Here a CSV file can be uploaded, a delimiter can be selected and finally the file can be uploaded:

![import](import.png)

When the data has been uploaded, select the corresponding header:

![fields](required_fields.png)

The file must contain: ID/Name, bank account type, branch code, bank account number and bank account name.

### General information

1. **Description on how the add-on works**:

  **1.1**. An admin will charge the invoices in Splynx. Once charged successfully, bank statements + batch files will be created and sent to Netcash and the charged invoices will change to a "Pending" state;

  **1.2** Netcash can take up to two days after the action date to receive the payments as well as non-payments (bounced payments);

  **1.3** Splynx will check Netcash twice a day for any payments and allocate them to the correct invoice in which case the invoice will become “paid”. In the case we receive non-payments the invoice status will return to unpaid.

2. **How to re-charge invoices**: 

  **2.1** The debit order batch should be deleted in Netcash as well as the relevant bank statement in Splynx (be very vigilant when deleting bank statements as deleting the wrong statement can cause payments not to be auto allocated back to the correct invoices), once completed, invoices can be re-charged.
