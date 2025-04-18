<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Unsubscribe | Hirey</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      padding: 50px;
      text-align: center;
    }
    .box {
      background: white;
      padding: 40px;
      max-width: 500px;
      margin: auto;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
      border-radius: 10px;
    }
    h1 {
      color: #333;
    }
    input[type="email"] {
      padding: 10px;
      width: 80%;
      border: 1px solid #ccc;
      border-radius: 5px;
      margin-top: 15px;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      background: #007BFF;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .message {
      margin-top: 20px;
      color: green;
    }
  </style>
</head>
<body>
  <div class="box">
    <h1>Unsubscribe from Emails</h1>
    <p>Enter your email below to stop receiving updates from Hirey.</p>
    <form id="unsubscribe-form">
      <input type="email" id="email" name="email" placeholder="Your email address" required>
      <br>
      <button type="submit">Unsubscribe</button>
    </form>
    <div class="message" id="message"></div>
  </div>

  <script>
    document.getElementById('unsubscribe-form').addEventListener('submit', function(e) {
      e.preventDefault();
      const email = document.getElementById('email').value;

      const formData = new FormData();
      formData.append("email", email);

      fetch('https://script.google.com/macros/s/AKfycbyzuUHLBTwFYizBtnHFyd__1T-SNrX9ojfkkhCEoORR/exec', {
        method: 'POST',
        body: formData
      })
      .then(response => {
        document.getElementById('message').textContent = 'You have been unsubscribed.';
        document.getElementById('unsubscribe-form').reset();
      })
      .catch(() => {
        document.getElementById('message').textContent = 'There was a problem submitting your request.';
      });
    });
  </script>
</body>
</html>
# unsubscribe-page
