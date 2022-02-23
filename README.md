# checkAllUdemy
Easy way to get Udemy certificate

### How to use it
* open console from inspect element (right click on page)
* copy and paste code
* press Enter

### Open all course sections
```js
// Stores all unexpanded section headers, and clicks on the unexpanded section headers to expand them
const sectionEl = document.querySelectorAll("section[data-purpose='sidebar'] div.udlite-btn");
sectionEl.forEach((section) => {
const isClosed = section.parentElement.querySelector("span").getAttribute("data-checked") !== "checked"
if (isClosed) section.click()
});
```

### Check all the unchecked boxes
```js
// Stores all checkboxes on the page, and clicks on any checkboxes on that currently not checked
const checkboxes = document.querySelectorAll("input[type='checkbox']");
checkboxes.forEach((checkbox) => {
if(!checkbox.checked) {
checkbox.click();
}
})
```