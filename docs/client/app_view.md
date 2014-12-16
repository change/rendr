## AppView

Inherits from [BaseView](../shared/base/view.md). You can change your main content container from this view by changing the `contentEl` key in the `options` object when extending `BaseAppView`

```javascript
var AppView = BaseAppView.extend({
  options : {
    contentEl : "#mainContent"
  }
})
```
