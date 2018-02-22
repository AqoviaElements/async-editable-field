![Bower version](https://img.shields.io/bower/v/async-editable-field.svg)
[![Build status](https://travis-ci.org/AqoviaElements/async-editable-field.svg?branch=master)](https://travis-ci.org/AqoviaElements/async-editable-field)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/AqoviaElements/async-editable-field)
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/AqoviaElements/async-editable-field?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

## &lt;async-editable-field&gt;

`<async-editable-field>` is an editable field component which can validate input and POST asynchronously

<!---
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="async-editable-field.html">
    <style>
      async-editable-field {
        max-width: 200px;
        margin: auto;
        font-family: sans-serif;
        font-size: 14px;
      }
    </style>
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
<async-editable-field
    id="myField"
    name="fieldName"
    value="Field Value" 
    url="http://localhost:8085/endpoint/"
    save-text="Update"
    cancel-text="Cancel">
</async-editable-field>

<script>
    var editableField = document.querySelector('async-editable-field#myField');

    editableField._setSuccessResponseFunction(function(response) {
      alert("Success: " + response);
    });

    editableField._setErrorResponseFunction(function(response, status) {
      alert("[" + status + "] Response: " + response);
    });
        
    editableField._setValidationFunction(function(value) {
        var reg = new RegExp(/^\d+$/);
        if (!reg.test(value)) {
            alert("Value must only contain numbers!");
            return false;
        }
        return true;
    });
</script>
```
