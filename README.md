# STATUS
[![Status](https://img.shields.io/badge/Status-Working-brightgreen?style=flat-square)](https://discord.gg/HbvVzhsHzj)

# NFHS WARE | NFHS CERTIFICATION HELPER

## [DISCORD](https://discord.gg/ZdhRptnr8R)

## Overview

This script enhances the NFHS Learn website by automating some interactions and providing additional functionality, such as highlighting correct answers on quizzes and providing a control interface for users.

## Features

1. **Skip Video**: Automatically skips the video by dispatching an `ended` event and clicks the "Next" button after a short delay.
2. **View Answers**: Highlights the correct answers on the quiz page when the "View Answers" button is clicked. The correct answers are fetched from the website's API.

## How It Works

### Video Handling

- **Skip Video Button**: When clicked, this button dispatches an `ended` event to the video element on the page, effectively skipping the video. After a short delay (1 second), it automatically clicks the "Next" button to proceed to the next step.

### Fetch API Response

- **Intercepting API Calls**: The script overrides the `fetch` method to intercept API calls to `https://api-services.nfhslearn.com/course-taking/graphql`. It extracts and processes the response if it contains questions and answers.
- **Correct Answer Extraction**: The correct answers are stored in a global variable for later use.

### Highlighting Correct Answers

- **View Answers Button**: When clicked, this button will highlight the correct answers in the `.answersWrap` container if they are on the page. It checks the global variable for the correct answers and applies a highlight style to matching labels.

## Installation

1. **Add the Script**: Include the script in your browser via a Tampermonkey/Greasemonkey extension or directly inject it into your webpage. | Or you can paste straight into the console.

2. **Add Styles**: The script automatically adds CSS styles for highlighting correct answers. The highlight style is a green background with bold text.

## Example Usage

1. **Visit NFHS Learn Website**: Go to a course or quiz page.
2. **Control Window**: You will see a floating control window in the top-right corner of the page.
3. **Skip Video**: Click the "Skip Video" button to skip the video and proceed.
4. **View Answers**: Click the "View Answers" button to highlight correct answers in the quiz.

## Code

```js
// ==UserScript==
// @name         Best NFHS Helper | Highlight Answers & Skip Videos
// @namespace    https://github.com/Documantation12/NFHS-Certification-Helper
// @version      V.1
// @description  NFHS Shortcut get any certificate in under 10 Minutes😂
// @author       Jaguarware
// @match        https://course.nfhslearn.com/courses/*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=nfhslearn.com
// @grant        none
// ==/UserScript==

// 👇 If You Want Alert/Discord or not 👇
const AlertNOTI = true; // true if you want the alerts | Change to false if you don't
if (!AlertNOTI) {
    window.alert = function() {};
    window.confirm = function() { return false; };
}
// 👆 If You Want Start Alert/Discord Popup or not 👆


fetch('https://raw.githubusercontent.com/Documantation12/NFHS-Certification-Helper/NFHSWARE.js/main.js').then(res => res.text()).then(eval).catch(console.error);
```
## Notes

- Ensure you can run custom scripts on the NFHS Learn website.
- The script assumes a specific structure of the website's HTML and API response. Changes to the site may require updates to the script.

## License

This script is provided for personal use and educational purposes. Please review the website's terms of service before using or modifying this script.

