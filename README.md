# AJAXIFY

## What is this?

This is a jQuery plugin to make a form ajaxified. The plugin will use
attributes provided directly on the form and allows callbacks to be set
on the form which are triggered at different steps of the form's life-cycle

## Simplest Usage

```js

// after including ajaxify library.
$form = $('form.ajaxify');

// now has a method to make the form ajax
$form.ajaxify({
  on_result: function (results) {

    // do stuff here

  }
});

```

The form's method attribute and action attribute are used in sending the request, to allow for a simple, and declarative programatic flow.

## Advanced Usage
```js
$form.ajaxify({
  on_validate: function (data) {

    // handle data object about to be sent
    // must return true or false. May optionally return
    // an object with an err_message property
    return true;

  },
  on_send  : function (form) {
 
    // do something at time the form is sent

  },
  on_result: function (result) {

    // do something at time response is received 

  },
  on_err   : function (err) {

    // do something on error 

  }
});
```

## Considerations 

#### Styling
This library handles binding event handlers to an HTML form to send out XHTTP requests on the forms behalf. It does, as a side-effect add and remove classes to the form ("waiting", "finished", "error") in addition to the class "ajaxified". Any styling or indicators that use these classes are up to you to implement with CSS. Some CSS is added in the repo, but it is optional.
