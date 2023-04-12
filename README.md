# Pomodoro Timer

This is a simple pomodoro timer web app built using HTML, CSS, and JavaScript.

## Features

- Pomodoro timer to help you stay focused and increase productivity.
- Flomodoro timer for those who prefer to work in shorter intervals.
- Settings to customize the timer duration.
- Change theme button to switch between light and dark mode.

## Usage

1. Clone the repository to your local machine.
2. Open the `index.html` file in your preferred web browser.
3. Use the pomodoro or flomodoro timer to stay focused during work or study sessions.
4. Customize the timer duration in the settings menu.
5. Change the theme by clicking the "Change Theme" button.

## Code Example

```html
<div class="timer-container">
  <div id="stopwatch">00:00</div>
  <button id="toggle">Start</button>
</div>
```

```css
#stopwatch {
  font-size: 5rem;
  padding: 2rem;
}

#toggle {
  background: inherit;
  border: 1.4px solid #212121;
  padding: 0.5rem 1.5rem;
  border-radius: 1rem;
  transition: all 0.3s ease-in-out;
  font-size: 1.1rem;
  font-weight: bold;
}

#toggle:hover {
  cursor: pointer;
  background: #eee;
}
```

```javascript
// Start timer function
function startTimer(duration, display) {
  var timer = duration,
    minutes,
    seconds;
  setInterval(function () {
    minutes = parseInt(timer / 60, 10);
    seconds = parseInt(timer % 60, 10);

    minutes = minutes < 10 ? "0" + minutes : minutes;
    seconds = seconds < 10 ? "0" + seconds : seconds;

    display.textContent = minutes + ":" + seconds;

    if (--timer < 0) {
      timer = duration;
    }
  }, 1000);
}

// Start button event listener
document.getElementById("toggle").addEventListener("click", function () {
  var duration = 25 * 60; // default duration is 25 minutes
  var display = document.querySelector("#stopwatch");
  startTimer(duration, display);
});
```

## Credits

This web app was created by [seesmof](https://github.com/seesmof).

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
