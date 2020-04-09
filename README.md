# Splynx unofficial documentation

In this repository we store one of beta-versions of Splynx documentation

You can visit official page of Splynx documentation following this link: https://docs.splynx.com/

### Files format description

#### Page title

Each page should be begin from the page title.

```
Page Title
==========
```
This title will be show in the header of the documentation panel.

![Page title example](./images/page_title.png)

#### Image

```
![Image alt](http://site.com/images/img.png)
```

#### Image with size

For set image size you can use url parameters.

```
![Image alt](http://site.com/images/img.png?w=200&h=100)
```

This code will be converted to:

```html
<img src="http://site.com/images/img.png?w=200&h=100" alt="Image alt" width="200" height="100">
```

#### Image src
For images `src` you can use absolute url or relative path.

Absolute url:

```
http://images.google.com/some_image.png
```

Relative path (recommended):

```
./images/my_image.png
```
#### Icon

```
<icon class="image-icon">![Image alt](image.png)</icon>
```

#### Links
You can use:

* Absolute links. This links will be open in new tab.

```
[Google](https://google.com)
```

* Relative links to other docs pages.

```
[Invoices](finance/invoices/invoices.md)
```

* Javascript functions

```
// Switch Splynx page
[Open config](javascript:switch_page('/admin/config'))

// Open dialog
[Add location](javascript:open_dialog_new('administration/locations--add'))

// Open help dialog
[Please help me](javascript:open_help_dialog('index.md'))
```

#### Youtube video
```
<iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/embed/wQyBkJDsmuw?wmode=opaque">Video on youtube</iframe>
```

<!--- Version 20 mar 2019 -->
