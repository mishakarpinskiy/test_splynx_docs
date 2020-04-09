FatturaPA
=========

FatturaPA is a Splynx add-on. It allows to export splynx invoices in xlm format, then you can export them to the system of electronic invoices.

To install "splynx-fatturapa" add-on please enter the command:

```bash
sudo apt update
sudo apt install splynx-fatturapa
```
or oyu can install it from Web UI:

*Config -> Integrations -> Add-ons:*

![1.png](0.png)

![1.png](1.png)

![1.png](4.png)

After installation, you have to configure add-on under *Config / Integrations / Modules list / splynx_fatturapa* <icon class="image-icon">![edit](2.png)</icon>.
Look at the screenshot:

![1.png](5.png)

![1.png](6.png)

choose partner to configure:

![1.png](7.png)

set partner params:

![1.png](8.1.png)

**ProgressivoInvio** - No particular criteria is established; the mode of valorization of the field, foreseen to contain an identifier alphanumeric of the transmitted file, is delegated to the user's evaluation according to requirement, but in compliance with the established characteristics from the XSD scheme.

**FormatoTrasmissione** - assumes a fixed value equal to "SDI11".

**CodiceDestinatario** - 567/5000 The field must contain the 6-character code, present on IndexPA between the information related to the billing service electronic, associated with the office, within the administration recipient, performs the function of receiving (and possibly processing) of the invoice. Alternatively, you can enhance the field with the Office code "Central" or with the default value "999999", when the conditions occur provided for by the provisions of the Ministry's interpretative circular of the Economy and Finance no. 1 of 31 March 2014.


**RegimeFiscale** - The field must contain one of the codes provided in the associated value list; the code identifies, on the basis of the commercial sector or the income situation, the tax regime in which the seller/lender operates.

**Nazione** - The field must contain, according to the standard ISO 3166-1 alpha-2 code, the country code.

**Provincia** - The field must contain the initials of the province in Italy to which the municipality indicated in the Common field belongs; its valorization is not allowed if the Nation field   contains a value other than "IT". Vice versa (field Country = "IT") must be present.

**Ufficio** - The field must contain the initials of the province of the registry of companies with which he is registered and registered the seller / lender.

**NumeroREA** - The field must contain the number with which the seller / lender is registered with the business register

**CapitaleSociale** - The field must contain the amount of the capital actually paid as a result of the last budget; is expected a numerical value consisting of an integer and two decimals; the decimals, separated by the whole with the dot character ("."), always go indicated even if zero (eg: 28000000.00).

**SocioUnico** - The field must contain the value "SU" in the case single member, or "SM" in the case of multi-personal company.

**StatoLiquidazione** - The field must contain the value "LS" in the case of companies in liquidation, or "LN" in the case of companies not in liquidation.

**Fax** - The field, if valued, must contain one fax number of the seller / lender.

**RiferimentoAmministrazione** - no particular criteria is established; the mode of valorization of the field, with a view to use such as the one on exposed, it is necessarily the result of an agreement between the parties, recipient of the document on one side and compiler of the document on the other; in particular the first (recipient of the document) will have an interest in communicating the correct value to be entered in the field, always respecting the characteristics established by the XSD scheme.

**TipoDocumento** - The field must contain one of the codes provided in the associated value list.

**Divisa** - The field must contain the currency code used according to ISO 4217 alpha-3: 2001 (for example "EUR" in the case of euros).

**EsigibilitaIVA** - The field can be used with "I" for VAT immediate repayment, "D" for VAT with deferred collectibility, "S" for spin-off of payments.

**CondizioniPagamento** - In this field "TP01" should be indicated in the case of payment in installments, "TP02" in the case of total payment in a single payment, "TP03" in case of payment of an advance

**ModalitaPagamento** - The field must contain one of the encoded values present in the associated list.

Also you have to go to the *Config/System/Company Information* and set partner settings.

![1.png](9.png)

![1.png](10.png)

**Company name** - required

**Street** - required

**ZIP Code** - required

**City** - required

**Email** - required

**Phone** - required

**VAT number** - required (format must be like - IT11111111111)

**VAT %** - required

**Bank Account** - required

**Bank name** - required

Now you need to set *Customer additional fields* for customers whose invoices you will export. Look at the screenshot:

![1.png](11.png)

**Fields: _Street, ZIP code and City_ in _customers information_ must be set!!!**

**IdPaese** - required  (format must be like - IT)

**IdCodice** - required (format must be like - 00071090303)

**Provincia** - required (format must be like - CB)

**Nazione** - required (format must be like - IT)

**Rif.Ufficio** - required (if Category = Private person then _Rif.Ufficio = CodiceDestinatario_ (_CodiceDestinatario_ see in the _Config / Integrations / Modules list / Splynx Add-on Fatturapa_
), if Category = Company then set here your Office code)

Now, when you Installed and configured _splynx-fatturapa_ you can go to the _Administration / Reports / Fatturapa Export_ and export invoices in XML format. Look at the screenshot:

![1.png](12.png)

Click the following button <icon class="image-icon">![1.png](16.png)</icon> and set filter to export. Then click "Export" button.

![1.png](13.png)

If everything went well,  you will see the new record in the Fatturapa table with a possibility to download an archive with invoices in XML format.

![1.png](14.png)

![1.png](15.png)

In case of an error you will see a new record in the table with an exclamation mark in the "Actions" column. Click the following button <icon class="image-icon">![1.png](17.png)</icon> to see invoices that were not exported with a description why

![1.png](18.png)

![1.png](19.png)
