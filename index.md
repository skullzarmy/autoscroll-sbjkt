---
layout: single
title: "Autoscroll SBJKT"
description: "Easily add the autoscroll bookmarklet to your bookmarks bar"
---

# Autoscroll SBJKT

Drag the button below to your bookmarks bar to enable autoscrolling on pages with the element ID `mg-gallery`.

<a href="javascript:(function(){let%20scrollSpeed=5;let%20scrollContainer=document.getElementById('mg-gallery');if(!scrollContainer){console.error('Scrollable%20element%20with%20ID%20%22mg-gallery%22%20not%20found.%20Please%20ensure%20the%20correct%20ID%20is%20used.');return;}let%20scrollInterval=setInterval(()=>{scrollContainer.scrollBy(0,1);if((scrollContainer.scrollTop+scrollContainer.clientHeight)>=scrollContainer.scrollHeight){clearInterval(scrollInterval);console.log('Reached%20the%20bottom.%20Auto-scrolling%20stopped.');}},scrollSpeed);console.log('Auto-scrolling%20started.%20Click%20anywhere%20on%20the%20page%20to%20stop.');document.addEventListener('click',()=>{clearInterval(scrollInterval);console.log('Auto-scrolling%20stopped%20by%20user.');});})()" class="btn btn-primary">Autoscroll SBJKT</a>

## Installation Instructions

1. Drag the **Autoscroll SBJKT** button above to your bookmarks bar.
2. Click it on pages where you want autoscroll enabled.

---

## Source Code

Here's the bookmarklet code for reference:

```javascript
javascript: (function () {
    let scrollSpeed = 5;
    let scrollContainer = document.getElementById("mg-gallery");
    if (!scrollContainer) {
        console.error('Scrollable element with ID "mg-gallery" not found. Please ensure the correct ID is used.');
        return;
    }
    let scrollInterval = setInterval(() => {
        scrollContainer.scrollBy(0, 1);
        if (scrollContainer.scrollTop + scrollContainer.clientHeight >= scrollContainer.scrollHeight) {
            clearInterval(scrollInterval);
            console.log("Reached the bottom. Auto-scrolling stopped.");
        }
    }, scrollSpeed);
    console.log("Auto-scrolling started. Click anywhere on the page to stop.");
    document.addEventListener("click", () => {
        clearInterval(scrollInterval);
        console.log("Auto-scrolling stopped by user.");
    });
})();
```
