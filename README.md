# School Locator documentation

This project contains the documentation for the School Locator widget. It is intended for 
developers working for school boards who want to use the widget in their own website.

See the [change log](CHANGELOG.md) for the major changes.

## License

This project is intended only for customers of PSTGI. The specific license is managed 
by [this license file](LICENSE.md) and the specific contract between PSTGI and the customer.

## How to install the widget

To use the widget, you need to obtain an API Key from PSTGI. This key is used to identify
your website and to allow the widget to be used on your website. The key is also used to
track the usage of the widget.

### Download the widget

You can download the latest version of the widget from the [Downloads folder](.\Downloads).
Always use the latest version of the widget. Check the [change log](CHANGELOG.md) for the
changes in each version and attempt to update your website to use the latest version. The
widget is updated regularly to fix bugs and add new features.

### Integrate the widget in your website

The widget is built using HTML, CSS, and JavaScript only. You will not need any third party
libraries to use the widget.

To integrate the widget in your website, you need to add the following code to the HTML of 
your website:

```html
<abc-123></abc-123>
```

Set the following parameters:

- `abc` - defines X
- `123` - defines Y

### Test the widget

To check if you have access to the API server, you can use the following URL:

```
https://api.spsplus.ca/api/test/ping
```

It will respond with a basic JSON response similar to following one:

```json
{
    "message": "Pong",
    "status": "Service is running.",
    "appVersion": "3.9.1",
    "serverTime": "2023-11-30T11:00:25.1632332+00:00",
    "environment": "Production"
}
```

The PSTGI team
