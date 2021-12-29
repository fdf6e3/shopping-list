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

- Depending on user's OS IME(e.g. macOS), several items are simultaneously generated in when entering a word in a language(e.g. Korean) that is formed one character with two or more alphabets.
- It is because the keydown event is triggered while the alphabets are combined
- to solve this error, the if-statement with `isComposing` below should be added.

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

- it can be simple to use `HTML form tags` with `submit` event.

```cs
const form = document.querySelector('.new-form');

form.addEventListener('submit', (event) => {
  event.preventDefault();
  onAdd();
});
```
