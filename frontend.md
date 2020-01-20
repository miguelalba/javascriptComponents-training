# Part 2 - Frontend

The frontend involves the web resources and dependencies configured. Every JS node must have one Javascript source that defines the view in a namespace that has the same name as configured in the backend.
This view must have the following methods if configured:
- init
- getComponentValue
- validate
- setValidationError

The names of these methods are not relevant as they can be configured in the backend. Only the init and getComponentValue methods are mandatory. The validation methods are optional.

## Example with vanilla JavaScript

```javascript
(jsform = function() {

    let _representation;
    let _value;

    let view = {};

    view.init = function(representation, value) {
        _representation = representation;
        _value = value;

        createUI();
    };

    view.getComponentValue = () => {
        _value.firstName = document.getElementById("firstName").value;
        _value.lastName = document.getElementById("lastName").value;

        return _value;
    };

    function createUI() {
        let body = document.getElementsByTagName("body")[0];
        body.innerHTML = `<h2>Example JS form</h2>
        <form>
          <p>First name: <input id="firstName" type="text" value="Dick"></p>
          <p>Last name: <input id="lastName" type="text" value="Grayson"></p>
        </form>`;
    }

    return view;
}());
```

This javascript produces the following view:

![vanillajs_view](img/vanillajs_view.PNG)


## Example with libraries: Bootstrap

## Example with CSS