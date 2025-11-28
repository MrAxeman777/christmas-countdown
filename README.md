# christmas-countdown
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Christmas & New Year Countdown</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f0f8ff;
      color: #333;
      padding: 50px;
    }
    h1 {
      color: #d32f2f;
    }
    #countdown {
      font-size: 2em;
      margin: 20px 0;
    }
    .creator {
      margin-top: 40px;
    }
    .creator img {
      width: 150px;
      border-radius: 50%;
    }
  </style>
</head>
<body>
  <h1>Christmas & New Year Countdown</h1>
  <div id="countdown">Loading...</div>

  <div class="creator">
    <p>Creator:</p>
    <img src="https://i.imgur.com/rO0fN3x.jpeg" alt="Ashwin Sharma">
    <p>Ashwin Sharma</p>
  </div>

  <script>
    function updateCountdown() {
      const now = new Date();
      const christmas = new Date(now.getFullYear(), 11, 25); // Dec 25
      const newYear = new Date(now.getFullYear() + 1, 0, 1); // Jan 1 next year

      let target = now < christmas ? christmas : newYear;
      let diff = target - now;

      let days = Math.floor(diff / (1000 * 60 * 60 * 24));
      let hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      let minutes = Math.floor((diff / (1000 * 60)) % 60);
      let seconds = Math.floor((diff / 1000) % 60);

      document.getElementById('countdown').textContent =
        `${days} days, ${hours} hours, ${minutes} minutes, ${seconds} seconds until ${now < christmas ? "Christmas!" : "New Year!"}`;
    }

    setInterval(updateCountdown, 1000);
    updateCountdown();
  </script>
</body>
</html>


