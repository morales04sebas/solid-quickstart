<!DOCTYPE html>
<html>
<head>
  <title>Real-time Clock</title>
</head>
<body>
  <h1>Real-time Clock</h1>
  <p id="clock"></p>

  <script>
    // function to update the clock every second
    function updateClock() {
      var now = new Date();
      var hours = now.getHours();
      var minutes = now.getMinutes();
      var seconds = now.getSeconds();

      // add leading zeros to minutes and seconds if necessary
      minutes = (minutes < 10 ? "0" : "") + minutes;
      seconds = (seconds < 10 ? "0" : "") + seconds;

      // convert hours from 24-hour time to 12-hour time if necessary
      var meridiem = (hours < 12 ? "AM" : "PM");
      hours = (hours > 12 ? hours - 12 : hours);
      hours = (hours == 0 ? 12 : hours);

      // update the clock display
      var clockDisplay = hours + ":" + minutes + ":" + seconds + " " + meridiem;
      document.getElementById("clock").textContent = clockDisplay;
    }

    // update the clock immediately, then every second
    updateClock();
    setInterval(updateClock, 1000);
  </script>
</body>
</html>
