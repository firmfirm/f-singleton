# `<f-singleton>` [ ![Codeship Status for firmfirm/f-singleton](https://codeship.com/projects/286d0510-bc49-0133-92b3-568b1089e8b8/status?branch=master)](https://codeship.com/projects/136142)

Polymer element that helps implementing singleton pattern declaratively.

Common use case is to provide shared state in your elements (e.g. for configuration).

Using ES6 features, so take care in production apps.

  - Try out [live demo](https://firmfirm.github.io/f-singleton/components/f-singleton/demo/).
  - Learn about element properties and methods in [component page](https://firmfirm.github.io/f-singleton/) (**temporarily not working**).

## Example:

```html
<f-singleton key="myKey" value="something"></f-singleton>
<f-singleton key="myKey" value="{{myValue}}"></f-singleton>
<!-- myValue is now 'something' -->
<p>[[myValue]]</p>
```

`key` is a property name to bind `value` to.
You can also use deep keys, like `key="myObj.myProp"`.

## Missing Features

The following Polymer helper methods are **not** implemented for manipulating `data` object directly:

`pop`, `shift`, `unshift`, or `splice`.

It would also be great to implement "domains" so that there could be different
groups of singletons.

# Development

From here on, documentation will only concern development of this component.

## Dependencies

Element dependencies are managed via [Bower](http://bower.io/). You can
install that via:

    npm install -g bower

Then, go ahead and download the element's dependencies:

    bower install

## Playing With Your Element

If you wish to work on your element in isolation, we recommend that you use
[Polyserve](https://github.com/PolymerLabs/polyserve) to keep your element's
bower dependencies in line. You can install it via:

    npm install -g polyserve

And you can run it via:

    polyserve

Once running, you can preview your element at
`http://localhost:8080/components/f-singleton/`, where `f-singleton` is the name of the directory containing it.


## Testing Your Element

Simply navigate to the `/test` directory of your element to run its tests. If
you are using Polyserve: `http://localhost:8080/components/f-singleton/test/`

### web-component-tester

The tests are compatible with [web-component-tester](https://github.com/Polymer/web-component-tester).
Install it via:

    npm install -g web-component-tester

Then, you can run your tests on _all_ of your local browsers via:

    wct

#### WCT Tips

`wct -l chrome` will only run tests in chrome.

`wct -p` will keep the browsers alive after test runs (refresh to re-run).

`wct test/some-file.html` will test only the files you specify.
