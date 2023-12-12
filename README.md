# SPS School Locator - Documentation

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

## Features

The following features are supported by the widget:

- [x] Search of schools by typing an address
- [x] Retrieve study areas for the grades offered by schools
- [x] Display schools and study areas on a map
- [x] Display notices to users for specific schools, programs, and grades

For more details on features and updates see the [change log](CHANGELOG.md).

## TL;DR

To use the widget, you need to:

1. Get an API key from PSTGI.
1. Download the latest release package from the [/Downloads](./Downloads) folder.
1. Unzip the package in the root of your website, which will create a `/dist` folder.
1. [Add a reference](#add-references-to-the-widgets-files) to the widget's files in your page.
1. [Add the HTML element](#add-the-widgets-html-element) of the widget to your page.
1. Load the page.


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

You can download the latest version of the widget from the [/Downloads](./Downloads) folder.
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
<sps-school-locator api-key="myApiKey"></sps-school-locator>
```
, where you should replace `myApiKey` with the API Key you obtained from PSTGI.

At this point, if you load the page in your browser, you should see the widget with the search
box. Try typing an address in it and see if the widget can suggest addresses based on its 
autocomplete feature. Selecting an address would display the schools in the area offering 
different programs and grades.

#### Customizing the widget

The following parameters customize the look and feel of the widget:

- `api-key` - (required) API Key you obtained from PSTGI
- `primary-color` - (required) accent color to be used for a better integration into your page
- `boundary-color` - (optional) fill color for boundaries (default: `#3388ff`)
- `api-url` - (optional) API server base URL (default: `https://api.spsplus.ca`); for development,
   you can use `https://dev.spsplus.ca`. Consider that the data you retieve from the development
   environment may be different from the production environment.
- `images-root-url` - (optional) path to images folder containing pin images and shadow; must end 
   with a `/`; (default: `dist/images/`).
- `bing-maps-key` - (optional) key for Bing Maps that you obtained directly from [Microsoft Bing
   Dev Center website](https://www.bingmapsportal.com/); if omitted, a fallback to 
   [Open Street Map](https://www.openstreetmap.org/) raster is used.

#### Example

The following example shows how to integrate the widget in your website. It will have a blue accent
color, use the default boundary color, and use the default API server URL. The widget will use
the default images for the map pins that came with the downloaded package.

> All keys in the examples below are fake and will not work. You must use the keys you obtained yourself.

```html
<sps-school-locator
    primary-color="#005fae"
    api-key="67dd753e-2c5e-48dd-9b11-b15f76f09878">
</sps-school-locator>
```

The following example will also set a Bing Maps key obtained from the Microsoft Bing Dev Center website.
It will display Bing Maps instead of Open Street Map.

```html
<sps-school-locator
    primary-color="#005fae"
    api-key="67dd753e-2c5e-48dd-9b11-b15f76f09878"
    bing-maps-key="SSBhbSBub3Qgc3VyZSB3aGF0IGtleSBJIHdpbGwgZ2V0IGZyb20gQmluZy">
</sps-school-locator>
```

The following example will also set a dark blue boundary color and use the development environment.

```html
<sps-school-locator
	primary-color="#005fae"
	boundary-color="#000055"
	api-key="67dd753e-2c5e-48dd-9b11-b15f76f09878"
	api-url="https://dev.spsplus.ca">
</sps-school-locator>
```

> While developing your client, you can use the Development environment. To do that, use the following domain
https://dev.spsplus.ca/


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

First, test if you can call the test API end-point that returns some basic information about the environment.

https://api.spsplus.ca/api/test/ping

While developing your client, you can use the Development environment. To do that, use the following domain
with the same requests:

https://dev.spsplus.ca/

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

### API Parameters

All HTTP Requests must contain the following header parameters:

- `Authorization` - (required) API Key you obtained from PSTGI
- `X-Api-Version` - (required) version of the end-point set you want to use. Currently, the latest and 
   recommended version is `3.0`. To use another one, first comform it with the PSTGI team.

### API End-points

To see a list of all end-points available in the API, use the Swagger page on the DEV server:

https://dev.spsplus.ca/swagger/

### Resolving issues

If you do not recieve a response from the server, check for the error message in the responce.
Most common issues are related to not having the `Authorization` API key or the `X-Api-Version`
value in the header.

Always try the [Development](https://dev.spsplus.ca/api/test/ping) or 
[Production](https://api.spsplus.ca/api/test/ping) test URL in your browser to confirm the 
API server is running and you can access it.


Good luck!

The PSTGI team
