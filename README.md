# Discourse Theme

## Theme Files and Folders
<br />
There are 3 main sections:

 * Common - Anything you change in the common tab will apply to desktop/mobile.
 * Desktop
 * Mobile

You can preview the mobile view on a desktop device by appending ?mobile_view=1 to the end of the URL (?mobile_view=0 switches back to Desktop).


### Subsections

#### CSS

File: `common.scss`

You can add CSS and SCSS here. Whatever you add is complied automatically on save and added as a separate .css stylesheet to the `<head>` section if the theme is active.


#### <head>

File: `head_tag.html`

 You can add html here (including script tags). Anything you add here is inserted just ***before*** the close tag of the `<head> ` close tag or `</head>`.

 ```
    <script type="text/javascript">
        console.log('Items would go here.');
    </script>
 </head>
 ```


#### Header

File: `header.html`

 You can also add html here. Anything you add here is ***inserted at the top of the <body> tag before the Discourse Header***.

```
<body>
    <h1>MY STUFF</h1>

    ########################
    ### Discourse Header
    ########################
</body>
```


#### After Header

File: `after_header.html`

Same as above. You can add html here. However, anything you add here will be ***inserted below*** the Discourse header ***but above the rest of the page content***.

```
<body>
    ########################
    ### Discourse Header
    ########################

    <h1>MY STUFF</h1>

    ...
    ...
    ...
</body>
```


#### </body>

File: `body_tag.html`

You can use html here. Anything you add is ***inserted at the very bottom of the <body> tag or just before the </body> tag***.

```
<body>
    ########################
    ### Discourse Header
    ########################
    
    ...
    ...
    ...

    <h1>MY STUFF</h1>
</body>
```

#### Footer

File: `footer.html`


You can also use html here but it’s is ***inserted just after the end of the page content or just below the <div id="main-outlet"> close tag***.

```
<body>
    ### Page Content
    
    ...
    ...
    ...

    <div id="main-outlet"></div>

    <h1>MY STUFF</h1>
</body>
```


#### Embedded CSS

File: `embedded.scss`

You can add CSS and SCSS here as well, the difference is that whatever you add here is only applied to Discourse when it’s embedded on another site. At the moment we support embedding [comments](https://meta.discourse.org/t/embedding-discourse-comments-via-javascript/31963) and [topic lists](https://meta.discourse.org/t/embedding-a-list-of-discourse-topics-in-another-site/125911).

The desktop and mobile sections are exactly the same except that they will only target their respective devices and they don’t have the Embedded CSS subsection.


##### Color Schemes

[Reference about.json]

A color scheme is a set fo colors you choose that is used to automaticlaly color all the elements in Discourse. The colors are **linked** to the values you enter in the `about.json` file.

Discourse then takes those colors (if that color scheme is active) does a bit of magic to them (see other section) and creates a few variations of those colors to style all the elements. This removes the need to write a gazillion lines of CSS just to change the them colors across the board.