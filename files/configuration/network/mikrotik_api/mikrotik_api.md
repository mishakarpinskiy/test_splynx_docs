MikroTik API
===========

To configure MikroTik API click on `Config → Networking → MikroTik API`.

![Icon](icon.png)

Here can be found settings for Mikrotik API.

![Config 1](settings_1.png)

### Size

Here we have to specify how much bytes in 1KB in Splynx, available options is 1000 or 1024 bytes.

### API

* **Debug** - enable/disable API debug log(under /var/www/splynx/logs/cron/mikrotik.log). Recommended only for testing/debug purposes;

* **Attempts** - select connection attempts(1-10);

* **Timeout** - select timeout in seconds.

#### Accounting

* **Write log file for accounting** - enable/disable accounting log(under /var/www/splynx/logs/cron/accounting.log). Recommended only for testing/debug purposes;

* **Min bytes for accounting** - Gather stats if "in + out" traffic is larger than (bytes);

* **Max timeout** - stop the accounting session after this time if no traffic during specified period of time(in seconds);

* **Max session time** - Divide large sessions into smaller sessions every (hours);

* **RRD enable** - enable/disable writing to RRD files(for graphs);

* **RRD cached enable** - enable/disable rrdcached (speed up rrd writing).

![config 2](settings_2.png)

### Router accounting options

* **Account local traffic** - enable/disable account the traffic to/from the router itself;

* **Threshold** - maximum number of IP pairs in the accounting table(allowed value is 1024-256000).

### Simple shaping

* **Reverse In/Out** - Enable if you want to change upload by download and vice versa;
* **Queue type for download** - Set queue download type;
* **Queue type for upload** - Set queue upload type.

### PCQ shaping:

* **Shaping in** - Chain where the rules are created;
* **Shaping out** - Chain where the rules are created;
* **Routing in** - Set type of routing in;
* **Routing out** - Set type of routing out;
* **For radius** - If yes, rules will be made for all plans (but without address-list, and without aggregation in plans);
* **Connection mark** - Enable connection mark.

### PPP secrets

* **Add caller ID** - enable/disable add the MAC address to the restriction (PPP) via API;

* **Include inactive customers** - enable/disable including inactive customers when adding "Disabled customers to address list" under router in Splynx on "Mikrotik" tab.

![Config 3](settings_3.png)

### IP firewall filter/DHCP

* **Add framed route** - enable/disable add routes to the service additional network field if IP-MAC filter or DHCP is enabled;

* **Filter rules** - list of rules that will be uploaded to a router. Use {{SPLYNX_WHITE_RESOURCES_ADDRESS_LIST}} for white resources Address list name and {{SPLYNX_IP_ADDRESS}} for Splynx IP address;

* **Filter rules position** - select position for firewall filter rules. Available options are: default, top, bottom;

* **Splynx IP address** - set Splynx server IP address if you want customers to be able to redirect to blocking pages;

* **White resources Address list name** - name for address list for white resources;

* **White resources addresses** - white resources addresses(IP or URL).

### Force API configuration

Click on "Push config to all routers" if you want to apply some new Mikrotik API configurations.
