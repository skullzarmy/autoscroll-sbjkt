---
layout: single
title: "Autoscroll SBJKT"
description: "Easily add the autoscroll bookmarklet to your bookmarks bar"
---

# Autoscroll SBJKT

Drag the button below to your bookmarks bar to enable autoscrolling on pages with the element ID `mg-gallery`.

<a href="javascript:(function(){const%20SCROLL_SPEED=5;const%20SCROLL_ELEMENT_ID='mg-gallery';if(window.location.hostname!=='sbjkt.xyz'){console.warn('Autoscroll%20SBJKT%20only%20works%20on%20sbjkt.xyz');return;}const%20scrollContainer=document.getElementById(SCROLL_ELEMENT_ID);if(!scrollContainer){console.error(`Scrollable%20element%20with%20ID%20%22${SCROLL_ELEMENT_ID}%22%20not%20found.`);return;}const%20scrollInterval=setInterval(()=>{scrollContainer.scrollBy(0,1);if((scrollContainer.scrollTop+scrollContainer.clientHeight)>=scrollContainer.scrollHeight){clearInterval(scrollInterval);console.log('Reached%20the%20bottom.%20Auto-scrolling%20stopped.');}},SCROLL_SPEED);console.log('Auto-scrolling%20started.%20Click,%20scroll,%20or%20press%20any%20key%20to%20stop.');const%20stopScrolling=(event)=>{clearInterval(scrollInterval);console.log('Auto-scrolling%20stopped%20by%20user%20interaction.');event.stopPropagation();event.preventDefault();document.removeEventListener('click',stopScrolling,true);document.removeEventListener('scroll',stopScrolling,true);document.removeEventListener('keydown',stopScrolling,true);};document.addEventListener('click',stopScrolling,true);document.addEventListener('scroll',stopScrolling,true);document.addEventListener('keydown',stopScrolling,true);})()"
   class="btn btn-primary">Autoscroll SBJKT</a>

## Installation Instructions

1. Drag the **Autoscroll SBJKT** button above to your bookmarks bar.
2. Click it on sbjkt.xyz pages where you want autoscroll enabled.

---

## Source Code

Here's the bookmarklet code for reference:

```javascript
javascript: (function () {
    const SCROLL_SPEED = 5;
    const SCROLL_ELEMENT_ID = "mg-gallery";

    // Ensure the domain is correct
    if (window.location.hostname !== "sbjkt.xyz") {
        console.warn("Autoscroll SBJKT only works on sbjkt.xyz");
        return;
    }

    // Find the scroll container
    const scrollContainer = document.getElementById(SCROLL_ELEMENT_ID);
    if (!scrollContainer) {
        console.error(`Scrollable element with ID "${SCROLL_ELEMENT_ID}" not found.`);
        return;
    }

    // Start scrolling
    const scrollInterval = setInterval(() => {
        scrollContainer.scrollBy(0, 1);
        if (scrollContainer.scrollTop + scrollContainer.clientHeight >= scrollContainer.scrollHeight) {
            clearInterval(scrollInterval);
            console.log("Reached the bottom. Auto-scrolling stopped.");
        }
    }, SCROLL_SPEED);
    console.log("Auto-scrolling started. Click, scroll, or press any key to stop.");

    // Stop scrolling on user interaction and prevent default action
    const stopScrolling = (event) => {
        clearInterval(scrollInterval);
        console.log("Auto-scrolling stopped by user interaction.");

        // Prevent the interaction from triggering actions on the main app
        event.stopPropagation();
        event.preventDefault();

        // Remove event listeners after stopping
        document.removeEventListener("click", stopScrolling, true);
        document.removeEventListener("scroll", stopScrolling, true);
        document.removeEventListener("keydown", stopScrolling, true);
    };

    // Listen for user interactions to stop auto-scrolling
    document.addEventListener("click", stopScrolling, true);
    document.addEventListener("scroll", stopScrolling, true);
    document.addEventListener("keydown", stopScrolling, true);
})();
```
