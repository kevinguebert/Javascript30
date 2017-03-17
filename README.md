# Javascript 30

Tracking my progress from https://javascript30.com

## Project 01 - Javascript Drum Kit

*Enhancements*:
- Added "Click" event listener: you can now tap on each `div` and play the sound
    ```
    function keyTouched(e) {
        var target = e.target || e.srcElement;
        if(!target.getAttribute('data-key')) {
            if(target.parentElement) {
                if(target.parentElement.className === "key") {
                    target = target.parentElement;
                }
            }
        }
        playSound({keyCode: target.getAttribute('data-key')});
    }
    ```

- Added CSS style `-webkit-tap-highlight-color: transparent;` to the `html` element so the click event does not highlight the text
- Added CSS style `cursor: pointer` for the `key` div elements to showcase that a user can click on a key
