# 🛒 Shopping List

This is one of the toy projects made with **Vanilla JavaScript** without any framework. It includes very basic yet important front-end features.

## 🔍 Project description

Users are able to

- add a new item to the list by entering the text and click the button ➕ or pressing Enter ⌨️
- delete the item(s) on the list by click the button 🗑️

## 🔨 Note

### ❗️

Since the `keypress` event has been deprecated,

- it should be changed to `keydown`(or `keyup`) event.

- However, depending on user's OS IME(e.g. macOS), several items are generated at the same time
- when a word is input in the language(e.g. Korean) in which a single letter is formed by combining two or more alphabets.
- It is because the keydown event is triggered while the alphabets are combined
- to solve this error, the if-statement with `event.isComposing` below should be added.

```cs
const input = document.querySelector('.footer__input');

input.addEventListener('keydown', (event) => {
  if (event.isComposing) {
    return;
  }
  if (event.key === 'Enter') {
    onAdd();
  }
});
```

or

- it can be simple to use `HTML form tags` with `submit` event. (See more info about [Form](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form))
- However, it should be called with `event.preventDefault();` to show the items
- because the page is loaded automatically by the browser after submit event.

```cs
const form = document.querySelector('.new-form');

form.addEventListener('submit', (event) => {
  event.preventDefault();
  onAdd();
});
```
