## BaseView

Inherits from [Backbone.View](http://backbonejs.org/#View).

#### Public methods

#### `view.initialize()`
*Environment: shared.*

This is where you put any initialization logic.

#### `view.preRender()`
*Environment: shared.*

#### `view.render()`
*Environment: client.*

You should never have to override `view.render()` unless you're doing something really custom. Instead, you should be able to do anything you need using `view.postRender()`,

#### `view.postRender()`
*Environment: client.*

Here is where you'd put any initialization code that needs to access the DOM. This is a good place for jQuery plugins, sliders, etc.

#### `view.getTemplateData()`
*Environment: shared.*

The default implementation returns something reasonable: essentially `view.model.toJSON()` or `{models: view.collection.toJSON()}`. This method is easy to override in order to pass custom data to the template, or to decorate the model data.

```js
var MyView = BaseView.extend({
  getTemplateData: function() {
    // Get `super`.
    var data = BaseView.prototype.getTemplateData.call(this);
    return _.extend({}, data, {
      someOtherProperty: 'something custom'
    });
  }
});
```

#### Methods you can override for custom view behaviors

#### `view.getTemplate()`
*Environment: shared.*

You should never need to touch this, unless you're heavily customizing the view. Return a function that gets executed with a single `data` object as an argument.

#### `view.getTemplateName()`
*Environment: shared.*

You'll probably never touch this unless you're heavily customizing the view. This defaults to `view.constructor.id`. You can return a string to render a different template. This is used by the default implementation of `view.getTemplate()`.

#### `view.getInnerHtml()`
*Environment: shared.*

#### `view.getHtml()`
*Environment: shared.*

#### `view.getAttributes()`
*Environment: shared.*

Gets HTML attributes for outer DOM element. Used by `view.getHtml()`.
