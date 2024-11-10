---
layout: single
title: "Autoscroll SBJKT"
description: "Easily add the autoscroll bookmarklet to your bookmarks bar"
---

<link rel="stylesheet" href="assets/css/style.css">

# Autoscroll SBJKT <img class="logo__img" src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20.453' height='14.612' fill='%238C89FF' fill-rule='evenodd' xmlns:v='https://vecta.io/nano'%3E%3Cpath d='M7.201 7.306l1.746 1.746a1.81 1.81 0 0 0 2.561 0l1.746-1.746-.011-.011c1.683 1.683 1.683 4.392.011 6.064a4.28 4.28 0 0 1-6.053-6.053zm11.985.014l.014-.014a4.28 4.28 0 1 0-6.053 0h0l1.746-1.746a1.81 1.81 0 0 1 2.561 0L19.2 7.306zM7.301 7.311l.005-.005L5.56 5.56a1.81 1.81 0 0 0-2.561 0L1.253 7.306l.015.015-.015-.015a4.28 4.28 0 0 1 6.053-6.053 4.28 4.28 0 0 1 0 6.053z'/%3E%3C/svg%3E" alt="sbjkt logo.">

Drag the button below to your bookmarks bar to enable autoscrolling on pages with the element ID **mg-gallery**.

<a href="javascript:(function(){const%20SCROLL_SPEED=5;const%20SCROLL_ELEMENT_ID='mg-gallery';if(!window.location.hostname.endsWith('.sbjkt.xyz')%20&&%20window.location.hostname!=='sbjkt.xyz'){console.warn('Autoscroll%20SBJKT%20only%20works%20on%20sbjkt.xyz%20and%20its%20subdomains');return;}const%20scrollContainer=document.getElementById(SCROLL_ELEMENT_ID);if(!scrollContainer){console.error(`Scrollable%20element%20with%20ID%20%22${SCROLL_ELEMENT_ID}%22%20not%20found.`);return;}const%20scrollInterval=setInterval(()=>{scrollContainer.scrollBy(0,1);if((scrollContainer.scrollTop+scrollContainer.clientHeight)>=scrollContainer.scrollHeight){clearInterval(scrollInterval);console.log('Reached%20the%20bottom.%20Auto-scrolling%20stopped.');}},SCROLL_SPEED);console.log('Auto-scrolling%20started.%20Press%20any%20key%20or%20click%20to%20stop.');const%20stopScrolling=(event)=>{clearInterval(scrollInterval);console.log('Auto-scrolling%20stopped%20by%20user%20interaction.');event.stopPropagation();event.preventDefault();document.removeEventListener('click',stopScrolling,true);document.removeEventListener('keydown',stopScrolling,true);};document.addEventListener('click',stopScrolling,true);document.addEventListener('keydown',stopScrolling,true);})()" class="btn btn-primary"><img class="logo__img" src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20.453' height='14.612' fill='%238C89FF' fill-rule='evenodd' xmlns:v='https://vecta.io/nano'%3E%3Cpath d='M7.201 7.306l1.746 1.746a1.81 1.81 0 0 0 2.561 0l1.746-1.746-.011-.011c1.683 1.683 1.683 4.392.011 6.064a4.28 4.28 0 0 1-6.053-6.053zm11.985.014l.014-.014a4.28 4.28 0 1 0-6.053 0h0l1.746-1.746a1.81 1.81 0 0 1 2.561 0L19.2 7.306zM7.301 7.311l.005-.005L5.56 5.56a1.81 1.81 0 0 0-2.561 0L1.253 7.306l.015.015-.015-.015a4.28 4.28 0 0 1 6.053-6.053 4.28 4.28 0 0 1 0 6.053z'/%3E%3C/svg%3E" alt="sbjkt logo."> Autoscroll SBJKT</a>

## Installation Instructions

1. Drag the **Autoscroll SBJKT** button above to your bookmarks bar.
2. Click it on sbjkt.xyz or its subdomains where you want autoscroll enabled.
3. To cancel scrolling, simply click or press any key on your keyboard.

---

## Source Code

Here's the bookmarklet code for reference:

```javascript
javascript: (function () {
    const SCROLL_SPEED = 5;
    const SCROLL_ELEMENT_ID = "mg-gallery";

    // Ensure the domain is correct, allowing subdomains
    if (!window.location.hostname.endsWith(".sbjkt.xyz") && window.location.hostname !== "sbjkt.xyz") {
        console.warn("Autoscroll SBJKT only works on sbjkt.xyz and its subdomains");
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

    console.log("Auto-scrolling started. Press any key or click to stop.");

    // Stop scrolling on key press or mouse click, and prevent default action
    const stopScrolling = (event) => {
        clearInterval(scrollInterval);
        console.log("Auto-scrolling stopped by user interaction.");

        // Prevent the interaction from triggering actions on the main app
        event.stopPropagation();
        event.preventDefault();

        // Remove event listeners after stopping
        document.removeEventListener("click", stopScrolling, true);
        document.removeEventListener("keydown", stopScrolling, true);
    };

    // Listen for user interactions to stop auto-scrolling
    document.addEventListener("click", stopScrolling, true);
    document.addEventListener("keydown", stopScrolling, true);
})();
```
