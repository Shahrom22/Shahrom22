<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Firebase Auth</title>
</head>
<body>
  <h1>Register or Login</h1>
  <input type="email" id="email" placeholder="Enter your email">
  <input type="password" id="password" placeholder="Enter your password">
  <button onclick="register()">Submit</button>

  <!-- Firebase SDK-ҳо -->
  <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-auth.js"></script>

  <script>
    // Firebase Config
    const firebaseConfig = {
      apiKey: "AIzaSyA3IwBi-EWmjawWPh13gHaioShKCQbE_6A",
      authDomain: "mywebcoin-bot.firebaseapp.com",
      projectId: "mywebcoin-bot",
      storageBucket: "mywebcoin-bot.appspot.com",
      messagingSenderId: "523064192512",
      appId: "1:523064192512:web:7fd246eef1aa1f1f2432e5"
    };

    // Ибтидоии Firebase
    firebase.initializeApp(firebaseConfig);

    // Функсияи бақайдгирӣ
    function register() {
      const email = document.getElementById('email').value;
      const password = document.getElementById('password').value;

      firebase.auth().createUserWithEmailAndPassword(email, password)
        .then((userCredential) => {
          // Бақайдгирии муваффақ
          alert("User registered successfully!");
          console.log(userCredential);
        })
        .catch((error) => {
          // Хато
          alert("Error: " + error.message);
          console.error(error);
        });
    }
  </script>
</body>
</html>
