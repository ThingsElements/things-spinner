# things-spinner

## This is a component for representing work in progress and provides a global event.

## Example 1. Things spinner

``` html
  	<p class="paper-font-subhead">Things spinner</p>
      <demo-snippet class="centered-demo">
        <template>
          <things-spinner id="thingsSpinner"></things-spinner>
          <paper-button color="green" id="spn-button">Toggle Spinner</paper-button>
          <script>
            function toggleSpinner  (e) {
              var spinner = document.querySelector('#thingsSpinner');
              spinner.loading =! spinner.loading;
            };

            var spnButton = document.querySelector('#spn-button');
            spnButton.addEventListener('tap', toggleSpinner);
          </script>        
        </template>
      </demo-snippet>
```

******

## Example 2. Apply spinner through Things spinner behavior.

``` html
      <p class="paper-font-subhead">Things spinner behavior</p>
      <demo-snippet class="centered-demo">
        <template>
          <things-spinner id="thingsSpinner"></things-spinner>
          <paper-button color="green" id="behavior-button">Toggle Spinner</paper-button>
          <script>
            var spnButton = document.querySelector('#behavior-button');
            spnButton.addEventListener('tap', toggleSpinnerWBehavior);
            function toggleSpinnerWBehavior  (e) {
              Things.SpinnerBehavior.toggleSpinner();
            };
          </script>        
        </template>
      </demo-snippet>
  ```

******

## Example 3. Create a new spinner Controller with Things spinner behavior.

  ```html
      <p class="paper-font-subhead">Things spinner behavior with custome element</p>
      <demo-snippet class="centered-demo">
        <template>
          <things-spinner id="thingsSpinner"></things-spinner>
          <spinner-controller></spinner-controller>

          <dom-module id="spinner-controller">
            <template>
              <style>
                :host {
                  display: block;
                }
              </style>
              <paper-button color="green"
                            id="behavior-button"
                            on-tap="toggleSpinner">
                  Toggle Spinner
              </paper-button>
            </template>
            <script>
              Polymer({
                is: 'spinner-controller',
                behaviors: [
                  Things.SpinnerBehavior
                ]
              });
            </script>
          </dom-module>
        </template>
      </demo-snippet>
```

*****


## Dependencies

Element dependencies are managed via [Bower](http://bower.io/). You can install that via:

    npm install -g bower

Then, go ahead and download the element's dependencies:

    bower install

## Playing With Your Element

If you wish to work on your element in isolation, we recommend that you use
[Polyserve](https://github.com/PolymerLabs/polyserve) to keep your element's
bower dependencies in line. You can install it via:

    npm install -g polymer-cli

And you can run it via:

    polymer serve

Once running, you can preview your element at
`http://localhost:8080/components/things-spinner/`, where `things-spinner` is the name of the directory containing it.
