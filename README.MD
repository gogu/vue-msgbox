# Overview

vue-msgbox is a message box (like Sweet Alert) for vue.js.

# Import

```JavaScript
import MessageBox from 'vue-msgbox';
```

# Usage

## Basic usage

```JavaScript
MessageBox("Good job!", "You clicked the button!", "success");// title, message, type
```

Or pass an object as options, and second parameter as callback:

```JavaScript
MessageBox({
  title: 'I\'m a title',
  message: 'I\'m a message',
  type: 'success',
  showCancelButton: true
}, function(action) {
  console.log('callback:', action);
  MessageBox('Clicked: ' + action);
});
```

## Promise based usage

### Basic usage

```JavaScript
MessageBox({
  title: 'I\'m a title',
  message: 'I\'m a message',
  type: 'success',
  showCancelButton: true
}).then(function(action) {
  console.log('callback:', action);
  MessageBox('Clicked: ' + action);
});
```

### alert

```JavaScript
MessageBox.alert(message, title, options);
```

```JavaScript
MessageBox.alert('message').then(function(action) {
  ...
});
```

### confirm

If user press cancel button, then this promise will be rejected.

```JavaScript
MessageBox.confirm(message, title, options);
```

```JavaScript
MessageBox.confirm('message').then(function(action) {
  ...
});
```

### prompt

If user press cancel button, then this promise will be rejected.

```JavaScript
MessageBox.prompt(message, title, options);
```

```JavaScript
MessageBox.prompt('message').then(function(value, cation) {
  ...
});
```

# Options

| Option | Description |
| ----- | ----- |
| title | The title of MessageBox. |
| message | The content of MessageBox. |
| type | The status type of MessageBox: success, warning, error |
| showConfirmButton | Boolean(default true) visible of confirm button. |
| showCancelButton | Boolean(default false) visible of cancel button. |
| confirmButtonText | The text of confirm button. |
| cancelButtonText | The text of cancel button. |
| confirmButtonClass | Extra className of confirm button. |
| cancelButtonClass | Extra className of cancel button. |
| showInput | Boolean(default false) visible of input. |
| inputValue | value of input. |
| inputPlaceholder | placeholder of input. |
| inputPattern | Regexp(default null). validation pattern of input. |
| inputErrorMessage | error message when inputPattern test inputValue failed. |

# License
MIT
