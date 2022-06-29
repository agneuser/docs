# copyToClipboard

- `<p><code>txt</code>&nbsp;&nbsp;&nbsp;<button type="button" onclick="copy('txtToCopy')">+</button></p>`
- CSS

```css
button {
  cursor: pointer;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  vertical-align: middle;
  border-radius: 2px;
  width: 20px;
  height: 20px;
  font-size: 10px;
  padding: 0px;
  color: #FFF;
  background-color: #4F545C;
}
button:hover {
  background-color: #0000001A;
}
```

- Javascript

```javascript
function copy(input) {
  if (navigator.clipboard) {
    navigator.clipboard.writeText(input).then(() => {
      console.log('Copied to clipboard successfully.');
      alert('Text copied: ' + input);
    }, (err) => {
      console.log('Failed to copy the text to clipboard.', err);
    });
  } else if (window.clipboardData) {
    window.clipboardData.setData("Text", input);
  }
}
```
