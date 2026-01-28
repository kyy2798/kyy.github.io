<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>D'Glaze Premium - Multi Language</title>
<!-- Icons & Fonts -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<style>
:root {
    --primary: #2c3e50; 
    --accent: #e67e22; 
    --gold: #f1c40f; 
    --bg: #fdfbf7; 
    --white: #ffffff;
    --gray: #95a5a6;
    --text-dark: #333333;
    --danger: #e74c3c;
    --radius: 12px;
    --shadow: 0 8px 30px rgba(0,0,0,0.08);
}

* { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; -webkit-tap-highlight-color: transparent; }
body { background-color: var(--bg); color: var(--text-dark); padding-bottom: 80px; }

/* --- UI UTILITIES --- */
.container { max-width: 1100px; margin: 0 auto; padding: 20px; }
.btn { border: none; border-radius: 8px; padding: 10px 20px; cursor: pointer; font-weight: 600; transition: 0.2s; display: inline-flex; align-items: center; justify-content: center; gap: 8px; }
.btn-primary { background: var(--primary); color: white; }
.btn-accent { background: var(--accent); color: white; }
.btn-gold { background: var(--gold); color: #444; }
.btn-outline { border: 1px solid #ddd; background: white; color: var(--text-dark); }
.btn:hover { filter: brightness(1.1); transform: translateY(-2px); }
.btn:active { transform: translateY(0); }

/* --- HEADER --- */
header { background: var(--white); padding: 15px 5%; position: sticky; top: 0; z-index: 100; box-shadow: 0 2px 10px rgba(0,0,0,0.05); display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 10px; }
.logo { font-weight: 800; font-size: 1.4rem; color: var(--accent); display: flex; align-items: center; gap: 8px; text-decoration: none; }
.logo span { color: var(--primary); }

nav ul { display: flex; list-style: none; gap: 25px; }
nav a { text-decoration: none; color: var(--text-dark); font-weight: 500; font-size: 0.95rem; transition: 0.3s; position: relative; }
nav a.active, nav a:hover { color: var(--accent); }
nav a.active::after { content:''; position: absolute; bottom: -5px; left:0; width:100%; height:2px; background: var(--accent); }

.header-actions { display: flex; align-items: center; gap: 15px; }
.cart-btn { position: relative; cursor: pointer; font-size: 1.3rem; color: var(--primary); }
.cart-badge { position: absolute; top: -6px; right: -8px; background: var(--accent); color: white; font-size: 0.7rem; width: 20px; height: 20px; border-radius: 50%; display: flex; justify-content: center; align-items: center; border: 2px solid white; }

/* --- LANGUAGE SELECTOR --- */
.lang-select {
    padding: 5px 10px;
    border-radius: 6px;
    border: 1px solid #ddd;
    font-size: 0.85rem;
    outline: none;
    cursor: pointer;
    background-color: #fff;
    color: var(--primary);
    font-weight: 500;
}

/* --- USER DROPDOWN --- */
.user-menu-container { position: relative; }
.user-avatar { width: 40px; height: 40px; border-radius: 50%; object-fit: cover; border: 2px solid var(--accent); cursor: pointer; }
.user-dropdown {
    display: none; position: absolute; top: 55px; right: 0; background: white;
    box-shadow: var(--shadow); border-radius: 8px; width: 220px; padding: 5px; z-index: 101; animation: slideDown 0.2s;
}
.user-dropdown button { width: 100%; text-align: left; padding: 12px; border: none; background: none; cursor: pointer; border-radius: 6px; color: var(--text-dark); font-size: 0.9rem; display: flex; align-items: center; gap: 10px; }
.user-dropdown button:hover { background: #f0f0f0; }
.user-dropdown button.logout { color: var(--danger); }

/* --- PAGE SECTIONS --- */
.section { display: none; animation: fadeIn 0.4s ease; }
.section.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
@keyframes slideDown { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }

.page-title { text-align: center; margin-bottom: 25px; font-size: 1.8rem; color: var(--primary); font-weight: 700; }

/* --- PRODUCT GRID --- */
.grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 20px; }
.card { background: var(--white); border-radius: var(--radius); overflow: hidden; box-shadow: var(--shadow); transition: 0.3s; display: flex; flex-direction: column; }
.card:hover { transform: translateY(-5px); box-shadow: 0 12px 40px rgba(0,0,0,0.12); }
.card-img { width: 100%; height: 200px; object-fit: cover; background: #eee; }
.card-body { padding: 15px; flex-grow: 1; display: flex; flex-direction: column; }
.card-title { font-weight: 700; font-size: 1.1rem; margin-bottom: 5px; color: var(--primary); }
.card-desc { font-size: 0.85rem; color: var(--gray); margin-bottom: 15px; flex-grow: 1; }
.card-price { font-size: 1.2rem; color: var(--accent); font-weight: 700; margin-bottom: 10px; }

/* --- WALLET LIST --- */
.wallet-item { display: flex; justify-content: space-between; align-items: center; background: white; padding: 15px; border-radius: 12px; margin-bottom: 12px; border: 1px solid #eee; }
.wallet-info { display: flex; align-items: center; gap: 15px; }
.wallet-icon { width: 45px; height: 45px; border-radius: 10px; display: flex; justify-content: center; align-items: center; color: white; font-size: 1.2rem; }
.gopay { background: #00AED6; } .ovo { background: #4C3494; } .dana { background: #118EEA; } .bca { background: #0056C3; }

/* --- PROFILE --- */
.profile-header { text-align: center; background: white; padding: 30px; border-radius: 12px; margin-bottom: 20px; }
.profile-img-lg { width: 100px; height: 100px; border-radius: 50%; border: 4px solid var(--gold); margin-bottom: 10px; object-fit: cover; }
.points-card { background: linear-gradient(135deg, #f1c40f 0%, #f39c12 100%); color: white; padding: 15px; border-radius: 12px; margin: 15px 0; display: flex; justify-content: space-between; align-items: center; }
.points-val { font-size: 1.5rem; font-weight: 800; }
.detail-row { display: flex; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid #eee; }

/* --- MODALS --- */
.modal-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.7); z-index: 1000; display: none; justify-content: center; align-items: center; backdrop-filter: blur(4px); }
.modal { background: white; padding: 30px; border-radius: 16px; width: 90%; max-width: 500px; max-height: 90vh; overflow-y: auto; position: relative; animation: slideUp 0.3s; }
@keyframes slideUp { from { transform: translateY(30px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
.close-btn { position: absolute; top: 15px; right: 20px; font-size: 1.5rem; cursor: pointer; color: #aaa; }
.close-btn:hover { color: var(--primary); }

/* --- FORMS --- */
.form-group { margin-bottom: 15px; text-align: left; }
label { display: block; font-weight: 600; margin-bottom: 5px; font-size: 0.9rem; color: #555; }
input, select, textarea { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 8px; font-size: 0.95rem; outline: none; }
input:focus { border-color: var(--accent); }

/* --- CART & CHECKOUT --- */
.cart-item { display: flex; align-items: center; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid #eee; }
.qty-box { display: flex; align-items: center; gap: 10px; background: #f5f5f5; padding: 4px 8px; border-radius: 20px; }
.qty-btn { width: 24px; height: 24px; border-radius: 50%; border: none; background: white; cursor: pointer; font-weight: bold; color: var(--primary); box-shadow: 0 1px 3px rgba(0,0,0,0.1); display: flex; justify-content: center; align-items: center; }

/* Switch */
.switch-container { background: #fff8e1; padding: 15px; border-radius: 8px; display: flex; justify-content: space-between; align-items: center; margin: 15px 0; border: 1px solid #ffeeba; }
.switch { position: relative; display: inline-block; width: 44px; height: 24px; }
.switch input { opacity: 0; width: 0; height: 0; }
.slider { position: absolute; cursor: pointer; top: 0; left: 0; right: 0; bottom: 0; background-color: #ccc; transition: .4s; border-radius: 34px; }
.slider:before { position: absolute; content: ""; height: 18px; width: 18px; left: 3px; bottom: 3px; background-color: white; transition: .4s; border-radius: 50%; }
input:checked + .slider { background-color: var(--gold); }
input:checked + .slider:before { transform: translateX(20px); }

/* QRIS */
.qris-area { text-align: center; margin: 15px 0; padding: 20px; background: #f9f9f9; border-radius: 8px; border: 2px dashed #ccc; }

/* --- MOBILE NAV --- */
.mobile-nav { position: fixed; bottom: 0; left: 0; width: 100%; background: white; display: none; justify-content: space-around; padding: 12px 10px; border-top: 1px solid #eee; box-shadow: 0 -2px 10px rgba(0,0,0,0.05); z-index: 99; }
.mn-item { text-align: center; color: #bbb; cursor: pointer; flex: 1; font-size: 0.75rem; }
.mn-item i { display: block; font-size: 1.3rem; margin-bottom: 4px; margin-bottom: 5px; }
.mn-item.active { color: var(--accent); }

/* --- TOAST --- */
.toast { position: fixed; bottom: 90px; left: 50%; transform: translateX(-50%); background: rgba(44, 62, 80, 0.95); color: white; padding: 12px 24px; border-radius: 30px; font-size: 0.9rem; z-index: 2000; opacity: 0; transition: 0.3s; pointer-events: none; white-space: nowrap; }
.toast.show { opacity: 1; bottom: 100px; }

@media (max-width: 768px) {
    header nav { display: none; }
    .mobile-nav { display: flex; }
    .container { padding: 15px; }
}
</style>
</head>
<body>

<!-- TOAST NOTIFICATION -->
<div id="toast" class="toast">Pesan notifikasi</div>

<!-- HEADER -->
<header>
    <a href="#" onclick="navTo('menu')" class="logo">
        <i class="fas fa-circle-notch"></i> D'Glaze <span>Premium</span>
    </a>

    <!-- Language Selector -->
    <select id="lang-selector" class="lang-select" onchange="changeLanguage(this.value)">
        <option value="id">🇮🇩 ID</option>
        <option value="en">🇺🇸 EN</option>
        <option value="zh">🇨🇳 中文</option>
    </select>

    <nav>
        <ul>
            <li><a href="#" onclick="navTo('menu', this)" class="active" data-i18n="nav.menu">Menu</a></li>
            <li><a href="#" onclick="navTo('wallet', this)" data-i18n="nav.wallet">Dompet</a></li>
            <li><a href="#" onclick="navTo('location', this)" data-i18n="nav.location">Lokasi</a></li>
            <li><a href="#" onclick="navTo('orders', this)" data-i18n="nav.orders">Pesanan</a></li>
        </ul>
    </nav>

    <div class="header-actions">
        <div class="cart-btn" onclick="openCart()">
            <i class="fas fa-shopping-bag"></i>
            <div class="cart-badge" id="cart-badge">0</div>
        </div>

        <!-- Guest State -->
        <button id="btn-login-guest" class="btn btn-primary" onclick="showLoginModal()" style="padding: 8px 16px; font-size: 0.8rem;" data-i18n="btn.login">Masuk</button>

        <!-- Logged In State -->
        <div id="user-area" class="user-menu-container" style="display: none;">
            <img src="" id="header-avatar" class="user-avatar" onclick="toggleUserMenu()">
            <div id="user-dropdown" class="user-dropdown">
                <button onclick="navTo('profile'); toggleUserMenu();"><i class="fas fa-user-circle"></i> <span data-i18n="nav.profile">Profil Saya</span></button>
                <button onclick="navTo('wallet'); toggleUserMenu();"><i class="fas fa-wallet"></i> <span data-i18n="nav.wallet">Dompet</span></button>
                <button class="logout" onclick="doLogout()"><i class="fas fa-sign-out-alt"></i> <span data-i18n="btn.logout">Keluar</span></button>
            </div>
        </div>
    </div>
</header>

<!-- MAIN CONTENT -->
<main class="container">

    <!-- 1. MENU PAGE -->
    <section id="page-menu" class="section active">
        <h2 class="page-title" data-i18n="page.menu.title">Menu Favorit</h2>
        <div class="grid" id="product-grid"></div>
    </section>

    <!-- 2. WALLET PAGE -->
    <section id="page-wallet" class="section">
        <h2 class="page-title" data-i18n="page.wallet.title">Metode Pembayaran</h2>
        <div class="card" style="padding: 20px; margin-bottom: 20px; border-left: 5px solid var(--accent);">
            <h3 data-i18n="wallet.connect_title">Hubungkan E-Wallet / Kartu</h3>
            <p style="color:#666; font-size:0.9rem; margin-bottom:10px;" data-i18n="wallet.connect_desc">Simpan kartu untuk pembayaran cepat.</p>
            <button class="btn btn-gold" onclick="openAddWalletModal()"><i class="fas fa-plus"></i> <span data-i18n="wallet.add_btn">Tambah Baru</span></button>
        </div>
        <div id="wallet-list"></div>
    </section>

    <!-- 3. LOCATION PAGE -->
    <section id="page-location" class="section">
        <h2 class="page-title" data-i18n="page.location.title">Lokasi Kami</h2>
        <div class="card" style="padding:0; overflow:hidden; margin-bottom:20px;">
            <div style="padding:15px; border-bottom:1px solid #eee;">
                <h3 style="color:var(--accent);"><i class="fas fa-map-marker-alt"></i> Jakarta Timur</h3>
                <p style="font-size:0.9rem; margin-top:5px;">Jl. Hj. Juhaman No. 12, Jakarta Timur</p>
            </div>
            <iframe width="100%" height="250" frameborder="0" style="border:0;" src="https://maps.google.com/maps?q=Jl.+Hj+Juhaman,+Jakarta+Timur&t=&z=15&ie=UTF8&iwloc=&output=embed"></iframe>
        </div>
    </section>

    <!-- 4. PROFILE PAGE -->
    <section id="page-profile" class="section">
        <h2 class="page-title" data-i18n="page.profile.title">Profil Saya</h2>
        <div class="profile-header">
            <img src="" id="prof-img" class="profile-img-lg">
            <h3 id="prof-name">Nama User</h3>
            <p id="prof-email" style="color:#666;">email@example.com</p>
            <div class="points-card">
                <div>
                    <div style="font-size:0.8rem; opacity:0.9;" data-i18n="profile.points_avail">Poin Tersedia</div>
                    <div class="points-val" id="prof-points">0</div>
                </div>
                <i class="fas fa-coins fa-2x" style="opacity:0.5;"></i>
            </div>
            <button class="btn btn-outline" onclick="openEditProfileModal()"><i class="fas fa-edit"></i> <span data-i18n="profile.edit_btn">Edit Profil</span></button>
        </div>
        <div class="card" style="padding:20px;">
            <div class="detail-row">
                <span data-i18n="profile.phone">No HP</span>
                <strong id="disp-phone">-</strong>
            </div>
            <div class="detail-row">
                <span data-i18n="profile.address">Alamat</span>
                <strong id="disp-address">-</strong>
            </div>
        </div>
    </section>

    <!-- 5. ORDERS PAGE -->
    <section id="page-orders" class="section">
        <h2 class="page-title" data-i18n="page.orders.title">Riwayat Pesanan</h2>
        <div id="orders-list">
            <div style="text-align:center; padding: 40px; color:#999;">
                <i class="fas fa-receipt fa-3x" style="margin-bottom:10px;"></i>
                <p data-i18n="orders.empty">Belum ada pesanan.</p>
            </div>
        </div>
    </section>

</main>

<!-- MOBILE NAV -->
<div class="mobile-nav">
    <div class="mn-item active" onclick="navTo('menu')"><i class="fas fa-utensils"></i><span data-i18n="nav.menu">Menu</span></div>
    <div class="mn-item" onclick="navTo('wallet')"><i class="fas fa-wallet"></i><span data-i18n="nav.wallet">Dompet</span></div>
    <div class="mn-item" onclick="navTo('location')"><i class="fas fa-map-marked-alt"></i><span data-i18n="nav.location">Lokasi</span></div>
    <div class="mn-item" onclick="navTo('profile')"><i class="fas fa-user"></i><span data-i18n="nav.profile">Profil</span></div>
    <div class="mn-item" onclick="navTo('orders')"><i class="fas fa-receipt"></i><span data-i18n="nav.orders">Pesanan</span></div>
</div>

<!-- MODAL: LOGIN -->
<div id="modal-login" class="modal-overlay">
    <div class="modal" style="text-align: center;">
        <span class="close-btn" onclick="closeModal('modal-login')">&times;</span>
        <h2 data-i18n="login.welcome">Selamat Datang</h2>
        <p style="margin-bottom:20px; color:#666;" data-i18n="login.desc">Masuk untuk mulai pesan donatmu.</p>
        <div style="display:grid; gap:10px;">
            <button class="btn btn-outline" onclick="doLogin('google')"><i class="fab fa-google"></i> <span data-i18n="login.btn_google">Masuk dengan Google</span></button>
            <button class="btn btn-outline" onclick="doLogin('facebook')"><i class="fab fa-facebook-f"></i> <span data-i18n="login.btn_fb">Masuk dengan Facebook</span></button>
            <button class="btn btn-outline" onclick="doLogin('email')"><i class="fas fa-envelope"></i> <span data-i18n="login.btn_email">Masuk dengan Email</span></button>
        </div>
    </div>
</div>

<!-- MODAL: SETUP PROFILE (FIRST TIME) -->
<div id="modal-setup" class="modal-overlay">
    <div class="modal">
        <span class="close-btn" onclick="closeModal('modal-setup')">&times;</span>
        <h3 data-i18n="setup.title">Lengkapi Data Diri</h3>
        <p style="font-size:0.85rem; color:#666; margin-bottom:15px;" data-i18n="setup.desc">Data ini diperlukan untuk pengiriman.</p>
        <div class="form-group">
            <label data-i18n="setup.label_phone">Nomor WhatsApp</label>
            <input type="tel" id="setup-phone" placeholder="0812...">
        </div>
        <div class="form-group">
            <label data-i18n="setup.label_address">Alamat Lengkap</label>
            <textarea id="setup-address" rows="2" placeholder="Nama Jalan, No Rumah..."></textarea>
        </div>
        <button class="btn btn-primary" style="width:100%" onclick="saveSetup()" data-i18n="setup.btn_save">Simpan Data</button>
    </div>
</div>

<!-- MODAL: CART -->
<div id="modal-cart" class="modal-overlay">
    <div class="modal">
        <span class="close-btn" onclick="closeModal('modal-cart')">&times;</span>
        <h3 style="margin-bottom:20px;" data-i18n="cart.title">Keranjang Belanja</h3>
        <div id="cart-items-container"></div>
        <div style="margin-top:20px; border-top:1px solid #eee; padding-top:15px;">
            <div style="display:flex; justify-content:space-between; font-size:1.1rem; font-weight:700; margin-bottom:15px;">
                <span data-i18n="cart.total">Total</span>
                <span id="cart-total-display">Rp 0</span>
            </div>
            <button class="btn btn-accent" style="width:100%" onclick="processCheckout()" data-i18n="cart.checkout">Checkout Sekarang</button>
        </div>
    </div>
</div>

<!-- MODAL: CHECKOUT & QRIS -->
<div id="modal-checkout" class="modal-overlay">
    <div class="modal" style="text-align: center;">
        <span class="close-btn" onclick="closeModal('modal-checkout')">&times;</span>
        <h3 data-i18n="checkout.title">Konfirmasi Pembayaran</h3>
        <div class="qris-area">
            <i class="fas fa-qrcode fa-5x" style="color:#333; margin-bottom:10px;"></i>
            <p>QRIS D'Glaze Premium</p>
            <p id="checkout-total-display" style="font-weight:bold; font-size:1.2rem; color:var(--accent);">Rp 0</p>
        </div>
        <div class="switch-container">
            <div style="text-align:left;">
                <div style="font-size:0.9rem; font-weight:600;" data-i18n="checkout.use_points">Gunakan Poin?</div>
                <div style="font-size:0.8rem; color:#888;">500 Poin = Rp 5.000</div>
            </div>
            <label class="switch">
                <input type="checkbox" id="point-toggle" onchange="togglePoints()">
                <span class="slider"></span>
            </label>
        </div>
        <button class="btn btn-primary" style="width:100%" onclick="finishOrder()" data-i18n="checkout.confirm">Saya Sudah Bayar</button>
    </div>
</div>

<script>
    /* --- DATA & STATE --- */
    let currentLang = 'id';
    let isLoggedIn = false;
    let cart = [];
    let user = {
        name: "Guest User",
        email: "guest@dglaze.com",
        phone: "-",
        address: "-",
        points: 1250
    };

    // DATA PRODUK LENGKAP 3 BAHASA
    const products = [
        { id: 1, name: "Coklat Bomb", name_en: "Choco Bomb", name_zh: "原味甜甜圈", price: 8000, img: "chocobomb.jpg", desc: "Klasik lembut dengan glaze coklat manis.", desc_en: "Soft classic with sweet glaze.", desc_zh: "柔软经典配甜甜糖衣。" },
        { id: 2, name: "Berrybliss", name_en: "Berrybliss", name_zh: "巧克力巧脆珠", price: 10000, img: "berrybliss.jpg", desc: "Glaze berry dan buah berry segar manis.", desc_en: "Berry glaze and sweet fresh berries.", desc_zh: "比利时巧克力配彩色脆珠。" },
        { id: 3, name: "Matcha Crunch", name_en: "Almond Crunch", name_zh: "杏仁脆片", price: 12000, img: "matchaalmond.jpg", desc: "Kepingan almond renyah di atas glaze.", desc_en: "Crunchy almond slices on glaze.", desc_zh: "糖衣上的脆杏仁片。" },
        { id: 4, name: "Tiramisu", name_en: "Tiramisu", name_zh: "提拉米苏", price: 15000, img: "tiramisu.jpg", desc: "Rasa kopi premium dengan krim lembut.", desc_en: "Premium coffee taste with soft cream.", desc_zh: "优质咖啡味配柔软奶油。" },
        { id: 5, name: "Coklat Putih Berry", name_en: "White Choco Berry", name_zh: "草莓爆发", price: 12000, img: "whitechocateberry.jpg", desc: "Coklat Putih yang creamy dipadukan dengan buah berry segar yang segar.", desc_en: "Creamy White Chocolate combined with fresh fresh berries. ", desc_zh: "新鲜真实草莓酱。" },
        { id: 6, name: "Keju Berlipat", name_en: "Double Cheese", name_zh: "奶酪小口", price: 11000, img: "doublecheese.jpg", desc: "Keju gurih yang nikmat di setiap gigitan.", desc_en: "Delicious savory cheese in every bite", desc_zh: "每一口都有咸融奶酪。" },
    ];

    /* --- TRANSLATION FULL DICTIONARY --- */
    const translations = {
        "nav.menu": { id: "Menu", en: "Menu", zh: "菜单" },
        "nav.wallet": { id: "Dompet", en: "Wallet", zh: "钱包" },
        "nav.location": { id: "Lokasi", en: "Location", zh: "地点" },
        "nav.orders": { id: "Pesanan", en: "Orders", zh: "订单" },
        "nav.profile": { id: "Profil Saya", en: "My Profile", zh: "我的资料" },
        "btn.login": { id: "Masuk", en: "Login", zh: "登录" },
        "btn.logout": { id: "Keluar", en: "Logout", zh: "退出" },
        "btn.add": { id: "Tambah", en: "Add", zh: "添加" },
        
        "page.menu.title": { id: "Menu Favorit", en: "Favorite Menu", zh: "精选菜单" },
        "page.wallet.title": { id: "Metode Pembayaran", en: "Payment Methods", zh: "付款方式" },
        "page.location.title": { id: "Lokasi Kami", en: "Our Location", zh: "我们的位置" },
        "page.profile.title": { id: "Profil Saya", en: "My Profile", zh: "我的资料" },
        "page.orders.title": { id: "Riwayat Pesanan", en: "Order History", zh: "订单历史" },
        
        "wallet.connect_title": { id: "Hubungkan E-Wallet / Kartu", en: "Connect E-Wallet / Card", zh: "关联电子钱包/银行卡" },
        "wallet.connect_desc": { id: "Simpan kartu untuk pembayaran cepat.", en: "Save card for quick checkout.", zh: "保存卡片以快速结账。" },
        "wallet.add_btn": { id: "Tambah Baru", en: "Add New", zh: "添加新卡" },
        
        "profile.points_avail": { id: "Poin Tersedia", en: "Available Points", zh: "可用积分" },
        "profile.edit_btn": { id: "Edit Profil", en: "Edit Profile", zh: "编辑资料" },
        "profile.phone": { id: "No HP", en: "Phone No.", zh: "电话号码" },
        "profile.address": { id: "Alamat", en: "Address", zh: "地址" },
        
        "orders.empty": { id: "Belum ada pesanan.", en: "No orders yet.", zh: "暂无订单。" },
        
        "notification.default": { id: "Pesan notifikasi", en: "Notification message", zh: "通知消息" },
        "notification.add_cart": { id: "Masuk keranjang!", en: "Added to cart!", zh: "已加入购物车！" },
        "notification.login_success": { id: "Berhasil masuk!", en: "Login successful!", zh: "登录成功！" },
        
        "login.welcome": { id: "Selamat Datang", en: "Welcome", zh: "欢迎" },
        "login.desc": { id: "Masuk untuk mulai pesan donatmu.", en: "Login to order your donuts.", zh: "登录以订购您的甜甜圈。" },
        "login.btn_google": { id: "Masuk dengan Google", en: "Login with Google", zh: "使用谷歌登录" },
        "login.btn_fb": { id: "Masuk dengan Facebook", en: "Login with Facebook", zh: "使用脸书登录" },
        "login.btn_email": { id: "Masuk dengan Email", en: "Login with Email", zh: "使用电子邮箱登录" },
        
        "setup.title": { id: "Lengkapi Data Diri", en: "Complete Profile", zh: "完善个人资料" },
        "setup.desc": { id: "Data ini diperlukan untuk pengiriman.", en: "Required for delivery.", zh: "送货所需资料。" },
        "setup.label_phone": { id: "Nomor WhatsApp", en: "WhatsApp Number", zh: "WhatsApp 号码" },
        "setup.label_address": { id: "Alamat Lengkap", en: "Full Address", zh: "完整地址" },
        "setup.btn_save": { id: "Simpan Data", en: "Save Data", zh: "保存资料" },
        
        "cart.title": { id: "Keranjang Belanja", en: "Shopping Cart", zh: "购物车" },
        "cart.total": { id: "Total", en: "Total", zh: "总计" },
        "cart.checkout": { id: "Checkout Sekarang", en: "Checkout Now", zh: "立即结账" },
        "cart.empty": { id: "Keranjang kosong", en: "Cart is empty", zh: "购物车是空的" },
        
        "checkout.title": { id: "Konfirmasi Pembayaran", en: "Payment Confirmation", zh: "付款确认" },
        "checkout.use_points": { id: "Gunakan Poin?", en: "Use Points?", zh: "使用积分?" },
        "checkout.confirm": { id: "Saya Sudah Bayar", en: "I Have Paid", zh: "我已付款" },
        "checkout.success": { id: "Pesanan Berhasil!", en: "Order Placed!", zh: "下单成功！" }
    };

    /* --- TRANSLATION LOGIC --- */
    function changeLanguage(lang) {
        currentLang = lang;
        const elements = document.querySelectorAll('[data-i18n]');
        
        elements.forEach(el => {
            const key = el.getAttribute('data-i18n');
            if (translations[key] && translations[key][lang]) {
                if(el.innerHTML.includes('<i')) {
                     const icon = el.querySelector('i');
                     if(icon) {
                        el.innerHTML = ''; 
                        el.appendChild(icon);
                        el.appendChild(document.createTextNode(' ' + translations[key][lang]));
                     }
                } else {
                    el.innerText = translations[key][lang];
                }
            }
        });

        // RENDER ULANG PRODUK & CART AGAR NAMA BERUBAH
        renderProducts();
        renderCart();
    }

    /* --- CORE FUNCTIONS --- */
    function navTo(pageId, linkEl) {
        document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
        document.getElementById('page-' + pageId).classList.add('active');
        if(linkEl) {
            document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
            linkEl.classList.add('active');
        }
        window.scrollTo(0,0);
    }

    function renderProducts() {
        const grid = document.getElementById('product-grid');
        grid.innerHTML = '';
        
        products.forEach(p => {
            let nameKey, descKey;
            if (currentLang === 'id') { nameKey = p.name; descKey = p.desc; }
            else if (currentLang === 'en') { nameKey = p.name_en; descKey = p.desc_en; }
            else { nameKey = p.name_zh; descKey = p.desc_zh; }
            
            const card = document.createElement('div');
            card.className = 'card';
            card.innerHTML = `
                <img src="${p.img}" class="card-img" alt="${nameKey}">
                <div class="card-body">
                    <div class="card-title">${nameKey}</div>
                    <div class="card-desc">${descKey}</div>
                    <div class="card-price">Rp ${p.price.toLocaleString('id-ID')}</div>
                    <button class="btn btn-primary" style="width:100%" onclick="addToCart(${p.id})">
                        <i class="fas fa-plus"></i> <span>${translations['btn.add'][currentLang]}</span>
                    </button>
                </div>
            `;
            grid.appendChild(card);
        });
    }

    function addToCart(id) {
        const product = products.find(p => p.id === id);
        const existing = cart.find(c => c.id === id);
        if (existing) { existing.qty++; } 
        else { cart.push({ ...product, qty: 1 }); }
        updateCartBadge();
        showToast(translations['notification.add_cart'][currentLang]);
    }

    function updateCartBadge() {
        const totalQty = cart.reduce((sum, item) => sum + item.qty, 0);
        document.getElementById('cart-badge').innerText = totalQty;
    }

    function openCart() { renderCart(); document.getElementById('modal-cart').style.display = 'flex'; }

    function renderCart() {
        const container = document.getElementById('cart-items-container');
        container.innerHTML = '';
        let total = 0;
        
        if (cart.length === 0) {
            container.innerHTML = `<p style="text-align:center; color:#999;">${translations['cart.empty'][currentLang]}</p>`;
        } else {
            cart.forEach((item, index) => {
                let nameKey;
                if (currentLang === 'id') nameKey = item.name;
                else if (currentLang === 'en') nameKey = item.name_en;
                else nameKey = item.name_zh;

                const subtotal = item.price * item.qty;
                total += subtotal;
                
                const div = document.createElement('div');
                div.className = 'cart-item';
                div.innerHTML = `
                    <div style="display:flex; align-items:center; gap:10px;">
                        <img src="${item.img}" style="width:50px; height:50px; border-radius:8px; object-fit:cover;">
                        <div>
                            <div style="font-weight:600; font-size:0.9rem;">${nameKey}</div>
                            <div style="font-size:0.85rem; color:var(--accent);">Rp ${item.price.toLocaleString('id-ID')}</div>
                        </div>
                    </div>
                    <div class="qty-box">
                        <button class="qty-btn" onclick="changeQty(${index}, -1)">-</button>
                        <span style="font-size:0.9rem; width:15px; text-align:center;">${item.qty}</span>
                        <button class="qty-btn" onclick="changeQty(${index}, 1)">+</button>
                    </div>
                `;
                container.appendChild(div);
            });
        }
        document.getElementById('cart-total-display').innerText = 'Rp ' + total.toLocaleString('id-ID');
    }

    function changeQty(index, delta) {
        cart[index].qty += delta;
        if (cart[index].qty <= 0) { cart.splice(index, 1); }
        renderCart(); updateCartBadge();
    }

    function closeModal(id) { document.getElementById(id).style.display = 'none'; }

    function processCheckout() {
        closeModal('modal-cart');
        let total = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
        document.getElementById('checkout-total-display').innerText = 'Rp ' + total.toLocaleString('id-ID');
        document.getElementById('modal-checkout').style.display = 'flex';
    }

    function togglePoints() {
        if(document.getElementById('point-toggle').checked && user.points < 500) {
            showToast("Poin tidak cukup");
            document.getElementById('point-toggle').checked = false;
        }
    }

    function finishOrder() {
        closeModal('modal-checkout');
        cart = []; updateCartBadge();
        showToast(translations['checkout.success'][currentLang]);
        // Simpan order dummy
        const historyList = document.getElementById('orders-list');
        const orderHtml = `
            <div class="card" style="padding:15px; margin-bottom:10px; border-left:4px solid var(--accent);">
                <div style="display:flex; justify-content:space-between; margin-bottom:5px;">
                    <strong>#ORD-${Math.floor(Math.random()*10000)}</strong>
                    <span style="color:var(--gold);">Selesai</span>
                </div>
                <p style="font-size:0.85rem; color:#666;">${new Date().toLocaleDateString()}</p>
            </div>
        `;
        if(historyList.innerText.includes(translations['orders.empty'][currentLang])) { historyList.innerHTML = orderHtml; } 
        else { historyList.insertAdjacentHTML('afterbegin', orderHtml); }
    }

    /* --- AUTH --- */
    function showLoginModal() { document.getElementById('modal-login').style.display = 'flex'; }
    function doLogin(method) {
        isLoggedIn = true; closeModal('modal-login');
        document.getElementById('btn-login-guest').style.display = 'none';
        document.getElementById('user-area').style.display = 'flex';
        document.getElementById('header-avatar').src = "https://picsum.photos/seed/avatar1/100/100";
        if(user.phone === "-") { document.getElementById('modal-setup').style.display = 'flex'; }
        else { updateUserDisplay(); showToast(translations['notification.login_success'][currentLang]); }
    }
    function saveSetup() {
        user.phone = document.getElementById('setup-phone').value;
        user.address = document.getElementById('setup-address').value;
        closeModal('modal-setup'); updateUserDisplay();
    }
    function updateUserDisplay() {
        document.getElementById('prof-name').innerText = user.name;
        document.getElementById('prof-email').innerText = user.email;
        document.getElementById('prof-points').innerText = user.points;
        document.getElementById('prof-img').src = "https://picsum.photos/seed/avatar1/200/200";
        document.getElementById('disp-phone').innerText = user.phone;
        document.getElementById('disp-address').innerText = user.address;
    }
    function doLogout() {
        isLoggedIn = false; document.getElementById('btn-login-guest').style.display = 'inline-flex';
        document.getElementById('user-area').style.display = 'none'; toggleUserMenu(); showToast("Logged Out");
    }
    function toggleUserMenu() {
        const dd = document.getElementById('user-dropdown');
        dd.style.display = dd.style.display === 'block' ? 'none' : 'block';
    }
    function openAddWalletModal() { showToast("Fitur Demo"); }
    function openEditProfileModal() {
        document.getElementById('modal-setup').style.display = 'flex';
        document.getElementById('setup-phone').value = user.phone !== "-" ? user.phone : "";
        document.getElementById('setup-address').value = user.address !== "-" ? user.address : "";
    }
    function showToast(msg) {
        const t = document.getElementById('toast'); t.innerText = msg; t.classList.add('show');
        setTimeout(() => t.classList.remove('show'), 3000);
    }

    window.onload = function() {
        renderProducts();
        document.getElementById('wallet-list').innerHTML = `
            <div class="wallet-item">
                <div class="wallet-info">
                    <div class="wallet-icon gopay"><i class="fas fa-wallet"></i></div>
                    <div>
                        <div style="font-weight:600;">GoPay</div>
                        <div style="font-size:0.8rem; color:#888;">0812-xxxx-xxxx</div>
                    </div>
                </div>
                <i class="fas fa-check-circle" style="color:var(--primary);"></i>
            </div>
        `;
    };
</script>
</body>
</html>
