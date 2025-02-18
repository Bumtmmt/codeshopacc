# codeshopacc
code shop
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shop Acc Xịn Nhất - Random5Sao Demo</title>
  <style>
    /* Reset & Base */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: Arial, sans-serif; background: #f4f4f4; color: #333; line-height: 1.6; }
    a { text-decoration: none; }
    ul { list-style: none; }
    
    /* Header */
    .header {
      background: #2c3e50; color: #fff; padding: 15px 20px; text-align: center;
    }
    .header img { max-width: 120px; margin-bottom: 10px; }
    .header h1 { font-size: 32px; }
    .header p { font-size: 14px; }
    
    /* Navbar */
    .navbar {
      background: #34495e; overflow-x: auto; white-space: nowrap;
    }
    .navbar a {
      display: inline-block; color: #fff; padding: 10px 15px; font-weight: bold;
      transition: background 0.3s;
    }
    .navbar a:hover { background: #2c3e50; }
    
    /* Banner */
    .banner {
      background: url('banner.jpg') no-repeat center center/cover;
      color: #fff; text-align: center; padding: 80px 20px;
    }
    .banner h2 { font-size: 48px; margin-bottom: 10px; }
    .banner p { font-size: 20px; margin-bottom: 20px; }
    .btn { background: #e74c3c; color: #fff; padding: 12px 30px; font-size: 18px; border-radius: 5px; transition: background 0.3s, transform 0.3s; }
    .btn:hover { background: #c0392b; transform: translateY(-3px); }
    
    /* Notification */
    .notice {
      background: #f1c40f; color: #2c3e50; text-align: center; padding: 10px;
      font-weight: bold; margin: 10px 0;
    }
    
    /* Section Container */
    section { padding: 40px 20px; max-width: 1200px; margin: 20px auto; background: #fff; border-radius: 5px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); }
    h2.section-title { text-align: center; font-size: 36px; margin-bottom: 30px; color: #2c3e50; }
    
    /* Filter Buttons & Product Grid */
    .filter-buttons { text-align: center; margin-bottom: 30px; }
    .filter-buttons button {
      background: #bdc3c7; border: none; padding: 10px 20px; margin: 0 5px; cursor: pointer; border-radius: 5px; transition: background 0.3s;
    }
    .filter-buttons button.active, .filter-buttons button:hover { background: #e74c3c; color: #fff; }
    .product-grid { display: flex; flex-wrap: wrap; justify-content: space-around; }
    .product-item {
      background: #fff; width: 300px; margin: 15px; border-radius: 5px; overflow: hidden;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1); transition: transform 0.3s, box-shadow 0.3s;
      opacity: 0; animation: fadeIn 0.5s forwards;
    }
    .product-item:hover { transform: translateY(-5px); box-shadow: 0 4px 15px rgba(0,0,0,0.2); }
    .product-item img { width: 100%; height: 200px; object-fit: cover; }
    .product-info { padding: 15px; }
    .product-info h3 { font-size: 22px; margin-bottom: 10px; color: #2c3e50; }
    .product-info p { font-size: 16px; margin-bottom: 10px; }
    .price { font-size: 20px; color: #e74c3c; font-weight: bold; margin-bottom: 15px; }
    
    /* Order & Topup History */
    .history-section { margin-bottom: 20px; }
    .history-section table { width: 100%; border-collapse: collapse; }
    .history-section th, .history-section td { padding: 10px; border: 1px solid #ddd; text-align: center; }
    .history-section .total { font-size: 20px; font-weight: bold; text-align: right; padding: 10px; }
    
    /* Forms (Topup & Recharge) */
    .form-group { margin-bottom: 15px; }
    .form-group label { display: block; margin-bottom: 5px; }
    .form-group input, .form-group select { width: 100%; padding: 10px; border: 1px solid #ccc; border-radius: 5px; }
    
    /* Wheel (Vòng quay) */
    .wheel-container { position: relative; width: 300px; height: 300px; margin: 20px auto; }
    .wheel {
      width: 100%; height: 100%; border-radius: 50%; border: 10px solid #f1c40f;
      background: conic-gradient(
        #e74c3c 0deg 60deg,
        #3498db 60deg 120deg,
        #2ecc71 120deg 180deg,
        #9b59b6 180deg 240deg,
        #f39c12 240deg 300deg,
        #e67e22 300deg 360deg
      );
      transition: transform 4s cubic-bezier(0.33, 1, 0.68, 1);
    }
    .spin-btn { display: block; margin: 20px auto; padding: 10px 20px; background: #e74c3c; color: #fff; border: none; border-radius: 5px; cursor: pointer; font-size: 18px; transition: background 0.3s; }
    .spin-btn:hover { background: #c0392b; }
    
    /* Affiliate */
    .affiliate-section ul { list-style: none; padding-left: 0; }
    .affiliate-section li { padding: 8px 0; font-size: 16px; }
    
    /* Footer */
    footer { background: #2c3e50; color: #fff; padding: 20px; text-align: center; }
    footer p { font-size: 14px; }
    
    /* Animation */
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    
    /* Responsive */
    @media (max-width: 768px) {
      .product-grid { flex-direction: column; align-items: center; }
      .navbar { flex-direction: column; }
    }
  </style>
</head>
<body>
  <!-- Header -->
  <header class="header">
    <img src="logo.png" alt="Logo Shop">
    <h1>Shop Acc Xịn Nhất</h1>
    <p>Acc chất lượng, giá tốt, uy tín hàng đầu</p>
  </header>
  
  <!-- Navbar -->
  <nav class="navbar">
    <a href="#home">Trang Chủ</a>
    <a href="#buy">Mua Tài Khoản</a>
    <a href="#randomLQ">Random LQ</a>
    <a href="#orderHistory">Lịch Sử Mua Hàng</a>
    <a href="#ranking">Bảng Xếp Hạng</a>
    <a href="#affiliate">Tiếp Thị Liên Kết</a>
    <a href="#topup">Nạp Tiền</a>
    <a href="#bank">Ngân Hàng</a>
    <a href="#invoice">Hoá Đơn</a>
    <a href="#recharge">Nạp Thẻ</a>
    <a href="#other">Khác</a>
    <a href="#blog">Bài Viết</a>
    <a href="#api">Tài Liệu API</a>
    <a href="#contact">Liên Hệ</a>
    <a href="#login">Đăng Nhập</a>
  </nav>
  
  <!-- Banner -->
  <section class="banner" id="home">
    <h2>Chào mừng đến với Shop Acc Xịn Nhất</h2>
    <p>Mua acc game, acc social, acc VIP và nhiều loại acc khác với giá cực sốc!</p>
    <a class="btn" href="#products">Xem Sản Phẩm</a>
  </section>
  
  <!-- Notice -->
  <div class="notice">
    CHÀO MỪNG ANH EM TRỞ LẠI VỚI SHOP RANDOM5SAO - Đừng quên theo dõi các event sắp tới!
  </div>
  
  <!-- Sản Phẩm -->
  <section class="product-section" id="products">
    <h2 class="section-title">Sản Phẩm Nổi Bật</h2>
    <div class="filter-buttons">
      <button class="filter-btn active" data-filter="all">Tất cả</button>
      <button class="filter-btn" data-filter="game">Acc Game</button>
      <button class="filter-btn" data-filter="social">Acc Social</button>
      <button class="filter-btn" data-filter="vip">Acc VIP</button>
    </div>
    <div class="product-grid" id="productGrid">
      <!-- Sản phẩm sẽ được render bởi JS -->
    </div>
  </section>
  
  <!-- Giỏ Hàng (Demo) -->
  <section class="product-section" id="cart">
    <h2 class="section-title">Giỏ Hàng</h2>
    <table>
      <thead>
        <tr>
          <th>Tên Sản Phẩm</th>
          <th>Số Lượng</th>
          <th>Giá</th>
          <th>Thao Tác</th>
        </tr>
      </thead>
      <tbody id="cartTable">
        <tr>
          <td>Acc Game Siêu Xịn 1</td>
          <td>1</td>
          <td>1.500.000₫</td>
          <td><button class="btn">Xóa</button></td>
        </tr>
      </tbody>
    </table>
    <p class="total">Tổng: 1.500.000₫</p>
    <a class="btn" href="#">Thanh Toán</a>
  </section>
  
  <!-- Lịch Sử Mua Hàng -->
  <section class="product-section" id="orderHistory">
    <h2 class="section-title">Lịch Sử Mua Hàng</h2>
    <table>
      <thead>
        <tr>
          <th>Mã Đơn</th>
          <th>Sản Phẩm</th>
          <th>Số Lượng</th>
          <th>Giá</th>
          <th>Thời Gian</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>...006</td>
          <td>Acc VIP Trải Nghiệm 100% Nổ</td>
          <td>1</td>
          <td>25.000₫</td>
          <td>3 phút trước</td>
        </tr>
        <!-- Mục mẫu khác -->
      </tbody>
    </table>
  </section>
  
  <!-- Lịch Sử Nạp Tiền -->
  <section class="product-section" id="topupHistory">
    <h2 class="section-title">Lịch Sử Nạp Tiền</h2>
    <table>
      <thead>
        <tr>
          <th>Tài Khoản</th>
          <th>Số Tiền</th>
          <th>Ngân Hàng</th>
          <th>Thời Gian</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>...ABC</td>
          <td>50.000₫</td>
          <td>ACB</td>
          <td>7 phút trước</td>
        </tr>
        <!-- Mục mẫu khác -->
      </tbody>
    </table>
  </section>
  
  <!-- Form Nạp Tiền -->
  <section class="product-section" id="topup">
    <h2 class="section-title">Nạp Tiền</h2>
    <form id="topupForm">
      <div class="form-group">
        <label for="topupAmount">Số Tiền:</label>
        <input type="number" id="topupAmount" placeholder="Nhập số tiền cần nạp" required>
      </div>
      <div class="form-group">
        <label for="bankSelect">Chọn Ngân Hàng:</label>
        <select id="bankSelect" required>
          <option value="">Chọn ngân hàng</option>
          <option value="acb">ACB</option>
          <option value="vietcombank">Vietcombank</option>
          <option value="mb">MB</option>
        </select>
      </div>
      <button class="btn" type="submit">Nạp Tiền Ngay</button>
    </form>
  </section>
  
  <!-- Form Nạp Thẻ -->
  <section class="product-section" id="recharge">
    <h2 class="section-title">Nạp Thẻ</h2>
    <form id="rechargeForm">
      <div class="form-group">
        <label for="cardNumber">Số Seri Thẻ:</label>
        <input type="text" id="cardNumber" placeholder="Nhập số seri thẻ" required>
      </div>
      <div class="form-group">
        <label for="cardPIN">Mã PIN:</label>
        <input type="text" id="cardPIN" placeholder="Nhập mã PIN thẻ" required>
      </div>
      <button class="btn" type="submit">Nạp Thẻ Ngay</button>
    </form>
  </section>
  
  <!-- Vòng Quay May Mắn -->
  <section class="product-section" id="wheel">
    <h2 class="section-title">Vòng Quay May Mắn</h2>
    <div class="wheel-container">
      <div class="wheel" id="spinWheel"></div>
    </div>
    <button class="spin-btn" id="spinBtn">Quay Ngay</button>
    <p id="wheelResult" style="text-align:center; font-weight:bold; color:#e74c3c; margin-top:15px;"></p>
  </section>
  
  <!-- Tiếp Thị Liên Kết -->
  <section class="product-section" id="affiliate">
    <h2 class="section-title">Tiếp Thị Liên Kết</h2>
    <ul>
      <li><strong>Link 1:</strong> <a href="https://affiliate.example.com/abc" target="_blank">https://affiliate.example.com/abc</a></li>
      <li><strong>Link 2:</strong> <a href="https://affiliate.example.com/def" target="_blank">https://affiliate.example.com/def</a></li>
      <li><strong>Link 3:</strong> <a href="https://affiliate.example.com/ghi" target="_blank">https://affiliate.example.com/ghi</a></li>
      <!-- Các liên kết khác -->
    </ul>
  </section>
  
  <!-- Footer -->
  <footer id="contact">
    <p>© 2025 Shop Acc Xịn Nhất. Mọi quyền được bảo lưu.</p>
    <p>Liên hệ: 090xxxxxxx | Email: shopacc@gmail.com</p>
  </footer>
  
  <!-- JavaScript -->
  <script>
    // Dữ liệu sản phẩm mẫu (30 mục)
    const products = [
      { id: 1, name: "Acc Game Siêu Xịn 1", category: "game", price: "1.500.000₫", image: "acc1.jpg" },
      { id: 2, name: "Acc Game Siêu Xịn 2", category: "game", price: "1.600.000₫", image: "acc1.jpg" },
      { id: 3, name: "Acc Game Siêu Xịn 3", category: "game", price: "1.700.000₫", image: "acc1.jpg" },
      { id: 4, name: "Acc Game Siêu Xịn 4", category: "game", price: "1.800.000₫", image: "acc1.jpg" },
      { id: 5, name: "Acc Game Siêu Xịn 5", category: "game", price: "1.900.000₫", image: "acc1.jpg" },
      { id: 6, name: "Acc Game Siêu Xịn 6", category: "game", price: "2.000.000₫", image: "acc1.jpg" },
      { id: 7, name: "Acc Game Siêu Xịn 7", category: "game", price: "2.100.000₫", image: "acc1.jpg" },
      { id: 8, name: "Acc Game Siêu Xịn 8", category: "game", price: "2.200.000₫", image: "acc1.jpg" },
      { id: 9, name: "Acc Game Siêu Xịn 9", category: "game", price: "2.300.000₫", image: "acc1.jpg" },
      { id: 10, name: "Acc Game Siêu Xịn 10", category: "game", price: "2.400.000₫", image: "acc1.jpg" },
      { id: 11, name: "Acc Social Chất Lượng 1", category: "social", price: "800.000₫", image: "acc2.jpg" },
      { id: 12, name: "Acc Social Chất Lượng 2", category: "social", price: "850.000₫", image: "acc2.jpg" },
      { id: 13, name: "Acc Social Chất Lượng 3", category: "social", price: "900.000₫", image: "acc2.jpg" },
      { id: 14, name: "Acc Social Chất Lượng 4", category: "social", price: "950.000₫", image: "acc2.jpg" },
      { id: 15, name: "Acc Social Chất Lượng 5", category: "social", price: "1.000.000₫", image: "acc2.jpg" },
      { id: 16, name: "Acc Social Chất Lượng 6", category: "social", price: "1.050.000₫", image: "acc2.jpg" },
      { id: 17, name: "Acc Social Chất Lượng 7", category: "social", price: "1.100.000₫", image: "acc2.jpg" },
      { id: 18, name: "Acc Social Chất Lượng 8", category: "social", price: "1.150.000₫", image: "acc2.jpg" },
      { id: 19, name: "Acc Social Chất Lượng 9", category: "social", price: "1.200.000₫", image: "acc2.jpg" },
      { id: 20, name: "Acc Social Chất Lượng 10", category: "social", price: "1.250.000₫", image: "acc2.jpg" },
      { id: 21, name: "Acc VIP Độc Quyền 1", category: "vip", price: "3.000.000₫", image: "acc3.jpg" },
      { id: 22, name: "Acc VIP Độc Quyền 2", category: "vip", price: "3.100.000₫", image: "acc3.jpg" },
      { id: 23, name: "Acc VIP Độc Quyền 3", category: "vip", price: "3.200.000₫", image: "acc3.jpg" },
      { id: 24, name: "Acc VIP Độc Quyền 4", category: "vip", price: "3.300.000₫", image: "acc3.jpg" },
      { id: 25, name: "Acc VIP Độc Quyền 5", category: "vip", price: "3.400.000₫", image: "acc3.jpg" },
      { id: 26, name: "Acc VIP Độc Quyền 6", category: "vip", price: "3.500.000₫", image: "acc3.jpg" },
      { id: 27, name: "Acc VIP Độc Quyền 7", category: "vip", price: "3.600.000₫", image: "acc3.jpg" },
      { id: 28, name: "Acc VIP Độc Quyền 8", category: "vip", price: "3.700.000₫", image: "acc3.jpg" },
      { id: 29, name: "Acc VIP Độc Quyền 9", category: "vip", price: "3.800.000₫", image: "acc3.jpg" },
      { id: 30, name: "Acc VIP Độc Quyền 10", category: "vip", price: "3.900.000₫", image: "acc3.jpg" }
    ];
    const productGrid = document.getElementById("productGrid");
    function renderProducts(filter) {
      productGrid.innerHTML = "";
      const filtered = filter === "all" ? products : products.filter(p => p.category === filter);
      filtered.forEach((p, index) => {
        const productDiv = document.createElement("div");
        productDiv.className = "product-item";
        productDiv.style.animationDelay = (index * 0.1) + "s";
        productDiv.innerHTML = `
          <img src="${p.image}" alt="${p.name}">
          <div class="product-info">
            <h3>${p.name}</h3>
            <p>Miêu tả ngắn gọn về sản phẩm.</p>
            <p class="price">${p.price}</p>
            <a class="btn" href="#">Mua Ngay</a>
          </div>
        `;
        productGrid.appendChild(productDiv);
      });
    }
    renderProducts("all");
    document.querySelectorAll(".filter-btn").forEach(btn => {
      btn.addEventListener("click", function() {
        document.querySelectorAll(".filter-btn").forEach(b => b.classList.remove("active"));
        this.classList.add("active");
        renderProducts(this.getAttribute("data-filter"));
      });
    });
    
    // Vòng quay may mắn
    const spinBtn = document.getElementById("spinBtn");
    const spinWheel = document.getElementById("spinWheel");
    const wheelResult = document.getElementById("wheelResult");
    const prizes = ['10% Giảm Giá', '5% Giảm Giá', 'Acc Miễn Phí', '20% Giảm Giá', 'Acc Bán Chạy', 'Chúc May Mắn'];
    spinBtn.addEventListener('click', function() {
      const randomDegree = Math.floor(Math.random() * 720) + 720;
      spinWheel.style.transform = `rotate(${randomDegree}deg)`;
      setTimeout(() => {
        const actualDegree = randomDegree % 360;
        const prizeIndex = Math.floor((360 - actualDegree) / (360 / prizes.length)) % prizes.length;
        wheelResult.textContent = "Bạn trúng: " + prizes[prizeIndex];
      }, 4000);
    });
    
    // Form Nạp Tiền
    document.getElementById("topupForm").addEventListener("submit", function(e) {
      e.preventDefault();
      alert("Yêu cầu nạp tiền đang được xử lý!");
    });
    // Form Nạp Thẻ
    document.getElementById("rechargeForm").addEventListener("submit", function(e) {
      e.preventDefault();
      alert("Yêu cầu nạp thẻ đang được xử lý!");
    });
  </script>
</body>
</html>
