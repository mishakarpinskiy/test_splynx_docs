Netcash
====================

Using Netcash addon customers can pay their invoices in few clicks from portal.

To install an addon navigate to **Config → Integrations → Add-ons**

![icon](icon.png)

find "splynx-netcash" record and click on install button:

![install](install.png)

or from terminal:

```bash
apt update
apt install splynx-netcash
```

After installation an addon has to be configured, to do this navigate to **Config → Integrations → Modules list**

![modules list](icon_modules.png)

![netcash](edit_module.png)

![settings](settings_1.png)
![settings2](settings_2.png)

"Service key" field must be filled with your PayNow service key:

![netcash profile](netcash_profile.png)

Under "Payment notifications" section you have to configure Accept URL, Decline URL and Re-direct URL with value of next format: **https://yourSplynx.com/netcash/result**.


All the rest parameters can not to be changed or you can configure here additional service fee(if needed) and other common settings.

After configuration entry points(widgets for portal) should be enabled:

![enable entry](enable_entry.png)

![entry points](edit_entry_points.png)

Here can be enabled/disabled entry points(widgets) for customer's portal to pay their invoices.

We enabled 2 entry points and they are available from customer's portal:

On dashboard:
![widget 1](widget_1.png)

![pay 1](pay_widget_1.png)

And under Finance/Invoices:
![pay 2](pay_widget_2.png)

Also we have a widget for prepaid customers to add some amount of money directrly from portal. To enable it navigate to addon's entry points menu and find this widget:

![prepaid widget](prepaid_widget.png)

and you will see it under customer's portal:

![prepaid pay](prepaid_pay.png)

Netcash logs can be found under **Administration → Logs → Netcash logs**

![Logs](logs.png)

As you can see on our screenshot we have also Netcash debit order logs because we have installed this addon as well. Use only selected on a screenshot log entry for Netcash addon.
