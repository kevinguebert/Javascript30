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

## Project 02 - JS and CSS Clock

*Enhancements*:
- Updated the width of the minute and hour hands to more reflect a clock with the hour hand being the smallest, minute being a bit bigger, and seconds being the largest
- Added a circle in the middle to "hold" to hands in the center (I didn't like how they didn't all meet at one point)
- Applied a border radius to the hands to make them feel less rigid
- Updated the hour hand to also be a percentage of the minutes in the hour:
  ```
  const hours = now.getHours();
  const hoursDegrees = ((hours / 12) * 360 + 90);
  const nextHours = hours + 1;
  if(hours === 24) nextHours = 1;
  const nextHoursDegrees = ((nextHours / 12) * 360 + 90);
  const h = hoursDegrees + ((nextHoursDegrees - hoursDegrees) * (minutes / 60));
  hourHand.style.transform = `rotate(${h}deg)`;
  ```
