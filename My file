<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>[Your Brand Name] - Merch Store</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #121212;
      color: #f1f1f1;
    }
    header {
      background-color: #1f1f1f;
      padding: 20px;
      text-align: center;
      border-bottom: 1px solid #333;
    }
    header h1 {
      margin: 0;
      font-size: 2.5em;
    }
    nav {
      margin-top: 10px;
    }
    nav a {
      margin: 0 10px;
      color: #00aced;
      text-decoration: none;
    }
    .container {
      max-width: 1000px;
      margin: 40px auto;
      padding: 0 20px;
    }
    .merch-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 30px;
    }
    .merch-item {
      background-color: #1e1e1e;
      padding: 20px;
      border-radius: 8px;
      text-align: center;
      transition: transform 0.3s;
    }
    .merch-item:hover {
      transform: scale(1.05);
    }
    .merch-item img {
      max-width: 100%;
      border-radius: 4px;
    }
    .merch-item h3 {
      margin: 15px 0 10px;
    }
    .merch-item button {
      background-color: #00aced;
      color: #fff;
      border: none;
      padding: 10px 20px;
      border-radius: 4px;
      cursor: pointer;
    }
    .merch-item button:hover {
      background-color: #008cba;
    }

    .cart {
      margin-top: 50px;
    }

    .cart h2 {
      margin-bottom: 15px;
    }

    .cart-list {
      background-color: #1f1f1f;
      padding: 20px;
      border-radius: 8px;
    }

    .cart-item {
      display: flex;
      justify-content: space-between;
      margin-bottom: 10px;
    }

    .cart-total {
      margin-top: 15px;
      font-weight: bold;
    }

    .checkout-btn {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #00aced;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    .checkout-btn:hover {
      background-color: #008cba;
    }

    /* Checkout Modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 999;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0,0,0,0.8);
      justify-content: center;
      align-items: center;
    }

    .modal-content {
      background-color: #1e1e1e;
      padding: 30px;
      border-radius: 8px;
      text-align: center;
      max-width: 400px;
    }

    .close-btn {
      background-color: #333;
      color: white;
      border: none;
      padding: 10px 20px;
      margin-top: 20px;
      cursor: pointer;
      border-radius: 4px;
    }

    footer {
      text-align: center;
      padding: 20px;
      font-size: 0.9em;
      color: #777;
      border-top: 1px solid #333;
      margin-top: 40px;
    }
  </style>
</head>
<body>
  <header>
    <h1>[Your Brand Name]</h1>
    <nav>
      <a href="https://tiktok.com/@yourhandle" target="_blank">TikTok</a>
      <a href="https://youtube.com/@yourhandle" target="_blank">YouTube</a>
      <a href="https://instagram.com/yourhandle" target="_blank">Instagram</a>
    </nav>
  </header>

  <div class="container">
    <h2>Shop the Latest Merch</h2>
    <div class="merch-grid">
      <div class="merch-item">
        <img src="https://via.placeholder.com/300x300.png?text=Shirt+1" alt="Shirt 1">
        <h3>Chill Sports Tee</h3>
        <p>$29.99</p>
        <button onclick="addToCart('Chill Sports Tee', 29.99)">Add to Cart</button>
      </div>
      <div class="merch-item">
        <img src="https://via.placeholder.com/300x300.png?text=Hoodie+1" alt="Hoodie 1">
        <h3>Dark Mode Hoodie</h3>
        <p>$49.99</p>
        <button onclick="addToCart('Dark Mode Hoodie', 49.99)">Add to Cart</button>
      </div>
      <!-- Add more merch items -->
    </div>

    <div class="cart">
      <h2>Your Cart</h2>
      <div class="cart-list" id="cart-list"></div>
      <div class="cart-total" id="cart-total"></div>
      <button class="checkout-btn" onclick="openCheckout()">Checkout</button>
    </div>
  </div>

  <div class="modal" id="checkout-modal">
    <div class="modal-content">
      <h2>Checkout</h2>
      <p>This is a demo checkout. Integrate Stripe or PayPal for real payments.</p>
      <button class="close-btn" onclick="closeCheckout()">Close</button>
    </div>
  </div>

  <footer>
    &copy; 2025 [Your Brand Name]. All rights reserved.
  </footer>

  <script>
    const cart = [];

    function addToCart(name, price) {
      cart.push({ name, price });
      renderCart();
    }

    function removeFromCart(index) {
      cart.splice(index, 1);
      renderCart();
    }

    function renderCart() {
      const cartList = document.getElementById('cart-list');
      const cartTotal = document.getElementById('cart-total');
      cartList.innerHTML = '';
      let total = 0;

      cart.forEach((item, index) => {
        total += item.price;
        const div = document.createElement('div');
        div.className = 'cart-item';
        div.innerHTML = `
          ${item.name} - $${item.price.toFixed(2)}
          <button onclick="removeFromCart(${index})" style="margin-left: 10px;">Remove</button>
        `;
        cartList.appendChild(div);
      });

      cartTotal.textContent = 'Total: $' + total.toFixed(2);
    }

    function openCheckout() {
      if (cart.length === 0) {
        alert("Your cart is empty.");
        return;
      }
      document.getElementById('checkout-modal').style.display = 'flex';
    }

    function closeCheckout() {
      document.getElementById('checkout-modal').style.display = 'none';
    }
  </script>
</body>
</html>
