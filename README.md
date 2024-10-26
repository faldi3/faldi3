<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IndoCiptaBersama - Fashion Indonesia</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>IndoCiptaBersama</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="products.html">Produk</a>
      <a href="cart.html">Keranjang</a>
    </nav>
  </header>

  <main>
    <h2>Selamat Datang di IndoCiptaBersama</h2>
    <p>Kami menyediakan produk fashion berkualitas dengan sentuhan Indonesia.</p>
  </main>
</body>
</html>
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Katalog Produk - IndoCiptaBersama</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>IndoCiptaBersama</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="cart.html">Keranjang</a>
    </nav>
  </header>

  <main>
    <h2>Katalog Produk</h2>
    <div class="product-list">
      <div class="product-item">
        <a href="product.html">
          <img src="images/jaket1.jpg" alt="Jaket Tradisional">
          <h3>Jaket Tradisional</h3>
          <p>Rp 350,000</p>
        </a>
        <button onclick="addToCart('Jaket Tradisional')">Tambah ke Keranjang</button>
      </div>
      <!-- Tambah produk lain di sini -->
    </div>
  </main>
</body>
<script src="script.js"></script>
</html>
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Detail Produk - IndoCiptaBersama</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>IndoCiptaBersama</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="products.html">Produk</a>
      <a href="cart.html">Keranjang</a>
    </nav>
  </header>

  <main>
    <h2>Jaket Tradisional</h2>
    <img src="images/jaket1.jpg" alt="Jaket Tradisional">
    <p>Harga: Rp 350,000</p>
    <p>Deskripsi: Jaket tradisional dengan bahan berkualitas dan desain unik khas Indonesia.</p>
    <button onclick="addToCart('Jaket Tradisional')">Tambah ke Keranjang</button>
  </main>
</body>
<script src="script.js"></script>
</html>
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Keranjang - IndoCiptaBersama</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Keranjang</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="products.html">Produk</a>
    </nav>
  </header>

  <main>
    <h2>Keranjang Belanja</h2>
    <div id="cart-items"></div>
    <button onclick="checkout()">Lanjut ke Checkout</button>
  </main>
</body>
<script src="script.js"></script>
</html>
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Checkout - IndoCiptaBersama</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Checkout</h1>
    <nav>
      <a href="index.html">Home</a>
    </nav>
  </header>

  <main>
    <h2>Detail Pembayaran</h2>
    <form id="checkout-form">
      <label>Nama Lengkap:</label><br>
      <input type="text" required><br><br>

      <label>Alamat:</label><br>
      <input type="text" required><br><br>

      <button type="submit">Bayar Sekarang</button>
    </form>
  </main>
</body>
<script src="script.js"></script>
</html>
body {
  font-family: Arial, sans-serif;
}

header {
  background-color: #0080ff;
  color: white;
  padding: 10px;
  text-align: center;
}

nav a {
  margin: 0 10px;
  color: white;
  text-decoration: none;
}

.product-list {
  display: flex;
  flex-wrap: wrap;
}

.product-item {
  border: 1px solid #ddd;
  padding: 10px;
  margin: 10px;
  width: 200px;
  text-align: center;
}

button {
  background-color: #0080ff;
  color: white;
  border: none;
  padding: 10px;
}
let cart = [];

function addToCart(productName) {
  cart.push(productName);
  alert(`${productName} ditambahkan ke keranjang`);
  updateCart();
}

function updateCart() {
  const cartItems = document.getElementById('cart-items');
  if (cartItems) {
    cartItems.innerHTML = cart.map(item => `<p>${item}</p>`).join('');
  }
}

function checkout() {
  if (cart.length === 0) {
    alert('Keranjang kosong');
  } else {
    window.location.href = 'checkout.html';
  }
}
