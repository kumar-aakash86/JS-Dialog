# JS-FormDialog
A simple vanilla js library to generate custom form on the go. Dialog will be generated & customized via a simple json object. 


## Usage
Copy following lines
> ```
> <script src="https://cdn.jsdelivr.net/npm/js-form-dialog@1/js/js-form-dialog.min.js"></script>
> <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/js-form-dialog@1/css/style.css">
> 
> ```

Use as following
>     JSDialog.init({
>         title:'Login',
>         titleCenter: true,
>         backdrop: "dismiss",
>         showClose: true,
>         width: "300px",
>         fields: [
>             {
>                 type: "text",
>                 placeholder: "Username",
>                 expand: "100%",
>                 key: "url",
>                 required: true
>             },
>             {
>                 type: "password",
>                 placeholder: "Password",
>                 expand: "100%",
>                 key: "password",
>                 required: true
>             }
>         ],
>         submitCallback: function(data) {
>             console.log(data);
>             document.getElementById("response").innerHTML = "<h2>Login successful</h2>";
>         },
>         closeCallback: function() {
>             console.log('Login form closed');
>         }
>     });
> 
>     JSDialog.show();


**This will return you json in following format on successful submit click**
> {url: "test@test.com", password: "123456"}

This response is in key-value pair. With the keys passed in the fields array.



## Properties
Property | Type | Description
---------|------|------------
title | string | Render as title of dialog. Either pass string or html string.
titleCenter | boolean | Align title as center. Default **false**
backdrop | string | Pass 'dismiss' to enable dismiss dialog on background click. Default **none**
showClose | boolean | Show close button on top. Default **false**
width | string | Pass desired dialog width. Ex- '300px'. Default **80% of window**
fields | JsonArray | Collection of elements to generate form. Defined below.


## Fields
Property | Type | Description
---------|------|------------
type | string | Type of textbox to generate
placeholder | string | String to use as placeholder
expand | string | Control width in percentage
key | string | Key to identify the output json
required | boolean | Set field as required. Default **false**


## Properties
Property | Description
---------|-------------
submitCallback | Callback to get the response from dialog on submit button. It returns **data** in response.
closeCallback | Fires when dialog closed. Captures close button click, submit & background dismiss.

## As of now the form only supports
```
Text Input
Numeric Input
Password Input
Required validation
```

## Other features are
```
Customizable Header
Multiple dialogs support on single page
Success callback
Dialog closed callback
```

## Proposed features
```
Checkbox input with validation
Radiobutton input with validation
Regex validation
Disable button until agree
```

## Roadmap
- [x] Classic html, css & js integration
- [ ] Angular integration
- [ ] React integration
- [ ] React native integaration


# LICENSE
```
MIT License

Copyright (c) 2019 Aakash Kumar

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```