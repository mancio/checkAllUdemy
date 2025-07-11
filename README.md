# checkAllUdemy
Easy way to get Udemy certificate

## code version 07/11/2025

### How to use it
* open console from inspect element (right click on page)
* copy and paste code
* press Enter
* refresh the page and repeat in case didn't work the first try

### Open all course sections
```js
function clickAllUncheckedAccordionPanels() {
    const accordionPanels = document.querySelectorAll('[id*="accordion-panel"]');

    accordionPanels.forEach(panel => {
        if (panel.getAttribute('data-checked') !== 'checked') {
            panel.click();
        }
    });
}

// Example usage:
// This will find all elements with "accordion-panel" in their id
// and click them if they are not checked.
clickAllUncheckedAccordionPanels();
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

### Open and check in one passage
```js
function clickAllUncheckedItemsWithDelay() {
  // --- 1. CLICK ACCORDION PANELS ---
  console.log("Starting: Clicking all unchecked accordion panels...");
  const accordionPanels = document.querySelectorAll('[id*="accordion-panel"]');
  accordionPanels.forEach(panel => {
    if (panel.getAttribute('data-checked') !== 'checked') {
      panel.click();
    }
  });
  console.log("Completed: Accordion panel check finished.");


  // --- 2. WAIT FOR 5 SECONDS ---
  console.log("Now waiting for 5 seconds...");
  setTimeout(() => {
    // --- 3. CLICK STANDARD CHECKBOXES ---
    console.log("Starting: Clicking all unchecked standard checkboxes...");
    const checkboxes = document.querySelectorAll("input[type='checkbox']");
    checkboxes.forEach((checkbox) => {
      if (!checkbox.checked) {
        checkbox.click();
      }
    });
    console.log("Completed: All tasks are finished.");
  }, 5000); // 5000 milliseconds = 5 seconds
}

// --- HOW TO RUN IT ---
// Call this single function to start the whole process.
clickAllUncheckedItemsWithDelay();
```