# Scripting

Scripting in Mindustry is done with the [Rhino JavaScript](https://github.com/mozilla/rhino) runtime. Scripts may be added to your mod by putting them in `scripts/`. Using the built-in `extendContent` function, you can extend existing Java types from JS, using *allowed classes* which are injected into your namespace.

For example:

```javascript
//Create dialog
const myDialog = new BaseDialog("My Dialog");
//Add "go back" button
myDialog.addCloseButton();
//Add text "Hi"
myDialog.cont.add("Hi!");
//Show dialog
myDialog.show();
```
