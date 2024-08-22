# PSTGI's SPS School Locator - Documentation

This project contains the documentation and distributables for the School Locator widget.
It is intended for developers working for school boards who want to use the widget in
their own website.

The intent for the SPS School Locator widget is to be used by school boards to display
the schools in their district on a map.

The widget does not need any code to run on your server-side. It is a pure client-side
code that runs in the browser of your users.

## License

This project is intended only for PSTGI customers. The specific license is managed by
the specific contract between PSTGI and the customer and [this license file](LICENSE.md).

## TL;DR

To use the widget, you need to:

1. Get an API key from PSTGI.
1. Download the latest release package from [Downloads](https://github.com/pstgi/school-locator-documentation/tree/main/Downloads) in our GitHub repository.
1. Unzip the package in the root of your website, which will create a `/dist` folder.
1. [Add a reference](#add-references-to-the-widgets-files) to the widget's files in the `<head>` of your page.
1. [Add the HTML element](#add-the-widgets-html-element) of the widget to the `<body>` of your page.
1. Add the API key to the HTML element.
1. Load the page.

## Features

The following features are supported by the widget:

- Search of schools by typing an address
- Retrieve school boundaries for the grades offered by schools
- Display schools and school boundaries on a map
- Display notices to users for specific schools, programs, and grades

For more details on features and updates see the [Change Log](CHANGELOG.md).

## Using the widget

### Prerequisites

To use the widget, you need to obtain an API Key from PSTGI. This key is used to identify
your website and dataset on it. You will also need to download the package with distributable.

### Test connection to the API server

First, check if you have access to the API server. Navigate to the following URL. It does not
require authorization.

https://api.spsplus.ca/api/test/ping

In addition, you can confirm that your website code can properly communicate to the API server.
Use any JavaScript component that can call an end-point. Send a GET HTTP Request to the URL
above with no parameters. If your request is received by the API server, it will immediately
return a JSON response similar to the one below:

```json
{
    "message": "Pong",
    "status": "Service is running.",
    "appVersion": "3.9.4",
    "serverTime": "2023-12-12T09:54:32.3487501+00:00",
    "environment": "Production"
}
```

### Embedding the widget in a webpage

You can embed the SPS School Locator widget in any HTML page. To do that, you need to:

1. Download the latest version of the widget.
1. Unzip the downloaded package and copy the files to a `/dist` folder on your webserver.
1. Add a reference to the main JavaScript file as well as the main stylesheet file to your page.
1. Add the widget tag to the body of the page.

The widget will automatically load the data from the API server and display
the map with the schools with the programs and grades they offer.

Here are the details for each step listed above:

#### Download the widget

You can download the latest version of the widget from [Downloads](https://github.com/pstgi/school-locator-documentation/tree/main/Downloads)
in our GitHub repository.
Always use the latest version of the widget. Check the [change log](./CHANGELOG.md) for the
changes in each version and attempt to update your website on regular basis. PSTGI updates the
widget often to fix bugs and add new features.

#### Place the widget in your website

The widget is built using vanilla HTML, CSS, and JavaScript only. You will not need any
third party libraries to use it or the API.

You need to unzip the downloaded package in the root of your website, which will create a
`/dist` folder with all needed files. To avoid issues with the integration, it is recommended
to keep the widget's `/dist` folder in the root folder of your website.

> If you cannot create or place a `/dist` folder in the root folder of your website, you will
need to change the paths to the widget's files in the HTML code below in several places -
both links in the `<head>` and the `images-root-url` parameter in the widget's HTML element.

##### Add references to the widget's files

To load the necessary script (JS) and style (CSS) files for the user of your webpage, you
need to add the following two lines in the header section (between `<head>` and `</head>`)
of your HTML page:

```html
<link href="dist/sps-school-locator.css?v=1.4" rel="stylesheet" />
<script src="dist/sps-school-locator.js?v=1.4"></script>
```

It is recommended to change the value of the `v` parameter located after the `?v=` to the
version of the widget you downloaded. This will ensure that when your users visit your page
they will not use a cached version of the files, but load ones from your website.

###### Add the widget's HTML element

To add the actual map with the search box and the list of schools as a HTML element to the page,
you need to add the following line in the body section (between `<body>` and `</body>`) of the
same page.

```html
<sps-school-locator api-key="my-api-key-here"></sps-school-locator>
```
where you should replace `my-api-key-here` with the API Key you obtained from PSTGI.

###### School list element

Optionally, a second element listing all the schools can be placed anywhere in the same HTML page, usually right below the main school locator.

```html
<sps-schools></sps-schools>
```
That element doesn't have any parameters. It cannot function without the main `sps-school-locator` widget.

###### Testing the widget

At this point, if you load the page in your browser, you should see the widget with the search
box. Try typing an address in it and see if the widget can suggest addresses based on its
autocomplete feature. Selecting an address would display the schools in the area offering
different programs and grades.

### Customizing the widget

The following parameters customize the look and feel of the widget:

- `api-key` - (required) API Key you obtained from PSTGI
- `primary-color` - (required) accent color to be used for a better integration into your page
- `boundary-color` - (optional) fill color for boundaries (default: `#3388ff`)
- `api-url` - (optional) API server base URL (default: `https://api.spsplus.ca`); for development,
   you can use `https://dev.spsplus.ca`. Consider that the data you reteive from the development
   environment may be different from the production environment.
- `images-root-url` - (optional) path to images folder containing pin images and shadow; must end
   with a `/`; (default: `dist/images/`).
- `bing-maps-key` - (optional) key for Bing Maps that you obtained directly from [Microsoft Bing
   Dev Center website](https://www.bingmapsportal.com/); if omitted, a fallback to
   [Open Street Map](https://www.openstreetmap.org/) raster is used.
- `azure-maps-key` - (optional) key for Azure Maps that you obtained directly from
   [Microsoft](https://azure.microsoft.com/en-gb/products/azure-maps/); if omitted, a fallback to
   [Open Street Map](https://www.openstreetmap.org/) raster is used.
-  `default-program-code` - (optional) preselects the program with the given code (case sensitive).
   Only Schools offering that program will appear in search results, unless the user selects other
   programs in the advanced search filters.

#### Examples

The following example shows how to integrate the widget in your website. It will have a blue accent
color, use the default boundary color, and use the default API server URL. The widget will use
the default images for the map pins that came with the downloaded package.

> All keys in the examples below are fake and will not work. You must use keys you obtaine yourself.

```html
<sps-school-locator
    primary-color="#005fae"
    api-key="67dd753e-2c5e-48dd-9b11-b15f76f09878">
</sps-school-locator>
```

The following example will also set a Bing Maps key obtained from the Microsoft Bing Dev Center
website. It will display Bing Maps instead of Open Street Map.

```html
<sps-school-locator
    primary-color="#005fae"
    api-key="67dd753e-2c5e-48dd-9b11-b15f76f09878"
    bing-maps-key="SSBhbSBub3Qgc3VyZSB3aGF0IGtleSBJIHdpbGwgZ2V0IGZyb20gQmluZy">
</sps-school-locator>
```

The following example will use the development environment and also set a dark blue boundary color.

```html
<sps-school-locator
	primary-color="#005fae"
	boundary-color="#000055"
	api-key="67dd753e-2c5e-48dd-9b11-b15f76f09878"
	api-url="https://dev.spsplus.ca">
</sps-school-locator>
```

This configuration only shows Schools offering the Regular Track program (verify that the code for
that program is `RT`) in search results.

```html
<sps-school-locator
    primary-color="#005fae"
	api-key="67dd753e-2c5e-48dd-9b11-b15f76f09878"
    default-program-code="RT">
</sps-school-locator>
```

Example of a school locator widget followed by a school list component:

```html
<sps-school-locator
    primary-color="#005fae"
	api-key="67dd753e-2c5e-48dd-9b11-b15f76f09878">
</sps-school-locator>

<sps-schools></sps-schools>
```

### Updating an existing page

To update a page that already uses the widget, you need to first download the latest version
following the instructions above. Then, you need to remove the old files from the `/dist` folder
and place the new ones in the same folder. If you have added your own files to the folder,
where the widget files are located, you need to make sure that you keep them or add them
back to their original locations.

Finally, you need to update the version number in the `<head>` section of your page. This
ensures that your users will download the latest version of the widget and not use the
cached version in their browsers.

The version is specified as a `v` parameter of the `href` and `src` attributes of the
`<link>` and `<script>` tags respectively. Use the version number of the downloaded package.
For example, if you downloaded version 1.4, you need to change the value after `?v=` in
the following lines:

```html
<link href="dist/sps-school-locator.css?v=1.4" rel="stylesheet" />
<script src="dist/sps-school-locator.js?v=1.4"></script>
```

> Technically, you can change the value with any number that is different from all of the
previous values your users may have cached in their browsers. However, it is recommended to
follow the version number of the downloaded package.

## Call the API directly

You can directly call the API server that the widget uses to retrieve the same data.

First, test if you can call the test API end-point that returns some basic information about the 
environment.

https://api.spsplus.ca/api/test/ping

Calling the URL above from any HTTP client component with a GET HTTP Request should return
a JSON response similar to the following one:

```json
{
    "message": "Pong",
    "status": "Service is running.",
    "appVersion": "3.9.4",
    "serverTime": "2023-12-12T09:54:32.3487501+00:00",
    "environment": "Production"
}
```

> While developing and testing your web-client, you should use the Development environment. To do
that, use the domain https://dev.spsplus.ca/ instead. The Production environment is available at 
https://api.spsplus.ca/.

### Required Parameters

All HTTP Requests must contain the following header parameters:

- `X-API-Key`     - (required) API Key you obtained from PSTGI
- `X-API-Version` - (required) version of the end-point set you want to use. Currently, the latest
   and recommended version is `3.0`. To use another one, first comfirm with the PSTGI team.

### API End-points

To see a list of all end-points available in the API, use the Swagger page on the Development server:

https://dev.spsplus.ca/swagger/

> The Production server does not have a Swagger page. Use the Development server to see the list of
end-points and their parameters. Test your web-pages against it first.

You can also visit the sample demo HTML page connected to the Development API server using your API key.
It demonstrates how to call some of the API end-points directly and the results they produce. To see
it on the Development environment, use the following URL:

https://dev.spsplus.ca/app/api-demo.html?api-url=https%3A%2F%2Fdev.spsplus.ca&api-key={my-api-key-here}

, where you should replace `{my-api-key-here}` with the API Key you obtained from PSTGI.

### Resolving issues

If you do not receive a response from the server, check for the error message in the response.
Most common issues are related to not having the `X-API-Key` API key or the `X-API-Version`
value in the header.

Always try the test URL in your browser for the [Development](https://dev.spsplus.ca/api/test/ping)
or the [Production](https://api.spsplus.ca/api/test/ping) environment to confirm the API server
is running and you can access it.


Good luck!

The PSTGI team
