### Installation
```
npm install --save sdk-paynl
```
require module
```javascript
const Paynl = require('sdk-paynl');
```
## Merchant Documentation:
Init
```javascript

const PaynlMerchant = new Paynl.Merchant({
    callback: {
        error: 'https://error.com',
        success: 'https://success.com'
    }
}, {debug: false});
```
### Create payment
```javascript

PaynlMerchant
    .getOrderId({
        amount: 1,
        currency: 'USD',
        description: 'MIT SDK NODE TEST'
    })
    .then(res => {
        return PaypalMerchant.createPaymet(res)
    })
    .then(console.log)
    .catch((error) => {
        console.error('Create Error,', error);
    });

```
### Browse function:
```javascript
function payment(param) {
    var method = param.method || "post";
    var form = document.createElement("form");
    form.setAttribute("method", param.method);
    form.setAttribute("action", param.url);
    for (var key in param.data) {
        if (param.data.hasOwnProperty(key)) {
            var hiddenField = document.createElement("input");
            hiddenField.setAttribute("type", "hidden");
            hiddenField.setAttribute("name", key);
            hiddenField.setAttribute("value", param.data[key]);

            form.appendChild(hiddenField);
        }
    }
    document.body.appendChild(form);
    form.submit();
}
```
