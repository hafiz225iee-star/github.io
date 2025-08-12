<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Memon Workers - Online Store</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f8f8f8;
      margin: 0;
      padding: 0;
    }
    header {
      background: #2c3e50;
      color: white;
      padding: 15px 20px;
      text-align: center;
      font-size: 24px;
      font-weight: bold;
    }
    .products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin: 20px;
      gap: 20px;
    }
    .product {
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.15);
      width: 250px;
      padding: 15px;
      text-align: center;
    }
    .product img {
      max-width: 100%;
      border-radius: 6px;
    }
    .product h3 {
      margin: 10px 0 5px;
    }
    .product p {
      font-size: 14px;
      color: #555;
      height: 40px;
    }
    .buttons {
      margin-top: 10px;
    }
    button {
      background-color: #3498db;
      border: none;
      color: white;
      padding: 10px 15px;
      margin: 5px;
      border-radius: 4px;
      cursor: pointer;
      font-weight: bold;
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #2980b9;
    }
    /* Chat widget */
    #chat-btn {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #27ae60;
      border: none;
      border-radius: 50%;
      width: 60px;
      height: 60px;
      cursor: pointer;
      box-shadow: 0 2px 8px rgba(0,0,0,0.3);
      font-size: 30px;
      color: white;
    }
    #chat-box {
      display: none;
      position: fixed;
      bottom: 90px;
      right: 20px;
      width: 300px;
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 12px rgba(0,0,0,0.25);
      padding: 15px;
      font-size: 14px;
    }
    #chat-box textarea {
      width: 100%;
      height: 80px;
      margin-bottom: 10px;
      border-radius: 4px;
      border: 1px solid #ccc;
      padding: 8px;
      resize: none;
    }
    #chat-box button {
      background: #27ae60;
      width: 100%;
    }
    /* Responsive */
    @media (max-width: 600px) {
      .products {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>
<body>

<header>Memon Workers</header>

<div class="products">
  <div class="product">
    <img src="https://via.placeholder.com/250x150?text=Clothing+Item" alt="Clothing" />
    <h3>Stylish T-Shirt</h3>
    <p>High quality cotton t-shirt.</p>
    <div class="buttons">
      <button onclick="orderNow('Stylish T-Shirt')">Order Now</button>
      <button onclick="addToCart('Stylish T-Shirt')">Add to Cart</button>
    </div>
  </div>

  <div class="product">
    <img src="https://via.placeholder.com/250x150?text=Electronics+Item" alt="Electronics" />
    <h3>Wireless Headphones</h3>
    <p>Noise-cancelling over-ear headphones.</p>
    <div class="buttons">
      <button onclick="orderNow('Wireless Headphones')">Order Now</button>
      <button onclick="addToCart('Wireless Headphones')">Add to Cart</button>
    </div>
  </div>

  <div class="product">
    <img src="https://via.placeholder.com/250x150?text=Accessory" alt="Accessories" />
    <h3>Leather Wallet</h3>
    <p>Genuine leather wallet with multiple slots.</p>
    <div class="buttons">
      <button onclick="orderNow('Leather Wallet')">Order Now</button>
      <button onclick="addToCart('Leather Wallet')">Add to Cart</button>
    </div>
  </div>
</div>

<!-- Chat button -->
<button id="chat-btn" title="Chat with us" onclick="toggleChat()">💬</button>

<!-- Chat box -->
<div id="chat-box">
  <textarea id="chat-message" placeholder="Type your message..."></textarea>
  <button onclick="sendMessage()">Send</button>
</div>

<script>
  function orderNow(product) {
    alert('Thank you for ordering: ' + product + '. Our team will contact you soon!');
  }
  function addToCart(product) {
    alert(product + ' added to cart!');
  }
  function toggleChat() {
    const chatBox = document.getElementById('chat-box');
    if (chatBox.style.display === 'block') {
      chatBox.style.display = 'none';
    } else {
      chatBox.style.display = 'block';
    }
  }
  function sendMessage() {
    const msg = document.getElementById('chat-message').value.trim();
    if (msg) {
      alert('Your message has been sent: ' + msg + '\nOur support will contact you soon.');
      document.getElementById('chat-message').value = '';
      toggleChat();
    } else {
      alert('Please type a message before sending.');
    }
  }
</script>

</body>
</html>
