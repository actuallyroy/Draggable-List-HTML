# Draggable List Element

## Overview

The Draggable List Element is a JavaScript class that allows you to create a list of draggable elements with custom rendering and reordering capabilities. It's designed to make it easy to create and manage lists of items that can be repositioned by dragging and dropping.

## Features

- Create a list of draggable elements.
- Customize the rendering of each item in the list.
- Easily reorder items by dragging and dropping.
- Dispatch events when an item is dragged.

## Installation

You can include the `DraggableListElem` class in your project by adding it to your JavaScript files. Make sure it is loaded after the DOM has been fully loaded.

```html
<script src="draggable-list-elem.js"></script>
```

## Usage

### Creating a Draggable List

To create a draggable list, instantiate the `DraggableListElem` class with the following parameters:

- `listArray`: An array of items to be displayed in the list.
- `container`: The DOM element where the list will be rendered.
- `renderer`: A function that defines how each item should be displayed.
- `className`: A class name to be applied to each list item element.

```javascript
const options = {
  listArray: myArray,
  container: document.getElementById("myListContainer"),
  renderer: (item) => `<div>${item}</div>`,
  className: "list-item",
};

const draggableList = new DraggableListElem(options);
```

### Handling Drag Events

You can listen for drag events by using the `onDrag` method. This allows you to react to drag-and-drop actions and access the updated list.

```javascript
draggableList.onDrag((event) => {
  const { listArray, srcElem } = event;
  // Handle the drag event here
});
```

### Customizing Styles

You can customize the styles of your list items by modifying the CSS. You can add or modify CSS rules for the `list-item` class and any other classes you use in your rendering function.

```css
.list-item {
  /* Add your custom styles here */
}

.active-drag-list {
  /* Add styles for active dragged elements here */
}
```

## Example

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <div id="myListContainer"></div>

  <script src="draggable-list-elem.js"></script>
  <script>
    const myArray = ["Item 1", "Item 2", "Item 3"];
    
    const options = {
      listArray: myArray,
      container: document.getElementById("myListContainer"),
      renderer: (item) => `<div>${item}</div>`,
      className: "list-item",
    };
    
    const draggableList = new DraggableListElem(options);
    
    draggableList.onDrag((event) => {
      const { listArray, srcElem } = event;
      // Handle the drag event here
    });
  </script>
</body>
</html>
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

This README provides a basic introduction to the `Draggable List Element` class. You may want to expand it with more details on specific methods, configuration options, and advanced usage as per your project's requirements.
