#<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقع تواصل بسيط</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>موقع تواصل بسيط</h1>
        <div id="chat-box" class="chat-box"></div>
        <input type="text" id="message" placeholder="اكتب رسالتك هنا..." />
        <button id="send-btn">إرسال</button>
    </div>
    <script src="script.js"></script>
</body>
</html>





body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.container {
    background: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    width: 300px;}
.chat-box {
    height: 200px;
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 10px;
    overflow-y: scroll;
    margin-bottom: 10px;}
.message {margin: 5px 0;}
.user1 {color: blue}
.user2 {color: green;}
let currentUser = "user1"; // لتحديد المستخدم الحالي
document.getElementById('send-btn').addEventListener('click', function() {
    const messageInput = document.getElementById('message');
    const message = messageInput.value.trim();
    if (message) {
        addMessage(message, currentUser);
        messageInput.value = ''; // مسح حقل الإدخال
        currentUser = currentUser === "user1" ? "user2" : "user1"; // تبديل المستخد}});
function addMessage(message, user) {
    const chatBox = document.getElementById('chat-box');
    const messageDiv = document.createElement('div');
    messageDiv.className = `message ${user}`;
    messageDiv.textContent = `${user}: ${message}`;
    chatBox.appendChild(messageDiv);
    chatBox.scrollTop = chatBox.scrollHeight; // التمرير لأسفل عند إضافة رسالة جديدة}
