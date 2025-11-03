[index.html](https://github.com/user-attachments/files/23016881/index.html)
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dashboard E-Commerce | Admin Panel</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
}

/* ===== LOGIN PAGE ===== */
.login-wrapper {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    background: linear-gradient(135deg, #ee7752 0%, #e73c7e 50%, #23a6d5 100%);
    position: relative;
    overflow: hidden;
}

.login-wrapper::before {
    content: '';
    position: absolute;
    width: 500px;
    height: 500px;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 50%;
    top: -250px;
    right: -250px;
    animation: float 6s ease-in-out infinite;
}

.login-wrapper::after {
    content: '';
    position: absolute;
    width: 400px;
    height: 400px;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 50%;
    bottom: -200px;
    left: -200px;
    animation: float 8s ease-in-out infinite reverse;
}

@keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(20px); }
}

#login-box {
    width: 100%;
    max-width: 450px;
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(10px);
    padding: 50px 40px;
    border-radius: 20px;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
    text-align: center;
    position: relative;
    z-index: 1;
    animation: slideUp 0.5s ease-out;
}

@keyframes slideUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

#login-box .logo-box {
    width: 80px;
    height: 80px;
    background: linear-gradient(135deg, #ee7752, #e73c7e);
    border-radius: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 20px;
    box-shadow: 0 10px 25px rgba(231, 60, 126, 0.3);
}

#login-box .logo-box i {
    font-size: 40px;
    color: #fff;
}

#login-box h2 {
    margin-bottom: 10px;
    font-weight: 700;
    color: #333;
    font-size: 1.8em;
}

#login-box p {
    color: #666;
    margin-bottom: 30px;
    font-size: 0.95em;
}

.input-group {
    position: relative;
    margin-bottom: 20px;
}

.input-group i {
    position: absolute;
    left: 18px;
    top: 50%;
    transform: translateY(-50%);
    color: #999;
    font-size: 1.1em;
}

#login-box input {
    width: 100%;
    padding: 15px 15px 15px 50px;
    border-radius: 12px;
    border: 2px solid #e0e0e0;
    font-size: 1em;
    transition: all 0.3s;
    background: #f8f9fa;
}

#login-box input:focus {
    outline: none;
    border-color: #e73c7e;
    background: #fff;
    box-shadow: 0 5px 15px rgba(231, 60, 126, 0.1);
}

#login-box button {
    width: 100%;
    padding: 15px;
    border: none;
    border-radius: 12px;
    background: linear-gradient(135deg, #ee7752, #e73c7e);
    color: #fff;
    font-weight: 600;
    font-size: 1.05em;
    cursor: pointer;
    transition: all 0.3s;
    box-shadow: 0 8px 20px rgba(231, 60, 126, 0.3);
    margin-top: 10px;
}

#login-box button:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 28px rgba(231, 60, 126, 0.4);
}

#login-box button:active {
    transform: translateY(0);
}

.error {
    background: #fee;
    color: #c33;
    padding: 12px;
    border-radius: 10px;
    margin-bottom: 20px;
    font-weight: 500;
    border-left: 4px solid #c33;
    display: none;
}

.error.show {
    display: block;
}

/* ===== DASHBOARD ===== */
.dashboard-wrapper {
    background: #f5f5f5;
    min-height: 100vh;
    display: none;
}

.dashboard-wrapper.active {
    display: block;
}

header {
    background: linear-gradient(135deg, #ee7752 0%, #e73c7e 50%, #23a6d5 100%);
    color: #fff;
    padding: 60px 20px;
    text-align: center;
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
    position: relative;
}

header::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23ffffff" fill-opacity="0.1" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,112C672,96,768,96,864,112C960,128,1056,160,1152,160C1248,160,1344,128,1392,112L1440,96L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>') no-repeat bottom;
    background-size: cover;
    opacity: 0.3;
}

.header-content {
    position: relative;
    z-index: 1;
}

header h1 {
    font-size: 2.8em;
    margin-bottom: 10px;
    font-weight: 700;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

header p {
    font-size: 1.2em;
    font-weight: 300;
    opacity: 0.95;
}

.logout-btn {
    position: absolute;
    top: 20px;
    right: 20px;
    padding: 12px 24px;
    background: rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(10px);
    color: #fff;
    border-radius: 10px;
    text-decoration: none;
    font-weight: 600;
    transition: all 0.3s;
    border: 2px solid rgba(255, 255, 255, 0.3);
    z-index: 10;
    cursor: pointer;
}

.logout-btn:hover {
    background: rgba(255, 255, 255, 0.3);
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

nav {
    background: #fff;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    display: flex;
    justify-content: center;
    padding: 0;
    position: sticky;
    top: 0;
    z-index: 1000;
}

nav a {
    padding: 18px 30px;
    text-decoration: none;
    color: #666;
    font-weight: 500;
    transition: all 0.3s;
    position: relative;
    cursor: pointer;
}

nav a::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 0;
    height: 3px;
    background: linear-gradient(90deg, #ee7752, #e73c7e);
    transition: width 0.3s;
}

nav a:hover {
    color: #e73c7e;
}

nav a:hover::after {
    width: 80%;
}

.container {
    max-width: 1400px;
    margin: 50px auto;
    padding: 0 20px;
}

.section-title {
    text-align: center;
    margin-bottom: 50px;
}

.section-title h2 {
    font-size: 2.5em;
    color: #333;
    margin-bottom: 10px;
    font-weight: 700;
}

.section-title p {
    color: #666;
    font-size: 1.1em;
}

.divisi-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}

.divisi-card {
    background: #fff;
    padding: 35px 25px;
    border-radius: 20px;
    text-align: center;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    position: relative;
    overflow: hidden;
}

.divisi-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 5px;
    background: linear-gradient(90deg, #ee7752, #e73c7e, #23a6d5);
    transform: scaleX(0);
    transition: transform 0.3s;
}

.divisi-card:hover::before {
    transform: scaleX(1);
}

.divisi-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.icon-box {
    width: 80px;
    height: 80px;
    background: linear-gradient(135deg, #ee7752, #e73c7e);
    border-radius: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 20px;
    transition: all 0.3s;
}

.divisi-card:hover .icon-box {
    transform: rotateY(360deg);
}

.divisi-card i {
    font-size: 35px;
    color: #fff;
}

.divisi-card h3 {
    margin-bottom: 20px;
    font-size: 1.4em;
    font-weight: 600;
    color: #333;
}

.divisi-card a {
    display: block;
    padding: 12px 20px;
    margin: 10px 0;
    background: linear-gradient(135deg, #f5f5f5, #e8e8e8);
    color: #333;
    text-decoration: none;
    border-radius: 12px;
    font-weight: 500;
    transition: all 0.3s;
    font-size: 0.95em;
}

.divisi-card a:hover {
    background: linear-gradient(135deg, #ee7752, #e73c7e);
    color: #fff;
    transform: translateX(5px);
    box-shadow: 0 5px 15px rgba(231, 60, 126, 0.3);
}

footer {
    text-align: center;
    padding: 40px 20px;
    margin-top: 80px;
    background: #fff;
    color: #666;
    font-size: 0.95em;
    box-shadow: 0 -5px 20px rgba(0, 0, 0, 0.05);
}

footer a {
    color: #e73c7e;
    text-decoration: none;
    font-weight: 500;
}

footer a:hover {
    text-decoration: underline;
}

.hidden {
    display: none;
}

/* Responsive */
@media(max-width: 768px) {
    header h1 {
        font-size: 2em;
    }
    
    .section-title h2 {
        font-size: 1.8em;
    }
    
    .divisi-grid {
        grid-template-columns: 1fr;
    }
    
    nav {
        flex-wrap: wrap;
    }
    
    nav a {
        padding: 15px 20px;
        font-size: 0.9em;
    }
    
    .logout-btn {
        position: relative;
        top: auto;
        right: auto;
        display: inline-block;
        margin-top: 20px;
    }
}
</style>
</head>
<body>

<!-- LOGIN PAGE -->
<div class="login-wrapper" id="loginPage">
    <div id="login-box">
        <div class="logo-box">
            <i class="fas fa-shopping-bag"></i>
        </div>
        <h2>Selamat Datang</h2>
        <p>Silakan login untuk mengakses dashboard</p>
        <div class="error" id="errorMsg">
            <i class="fas fa-exclamation-circle"></i> <span id="errorText"></span>
        </div>
        <form id="loginForm">
            <div class="input-group">
                <i class="fas fa-user"></i>
                <input type="text" id="username" placeholder="Username" required autocomplete="username">
            </div>
            <div class="input-group">
                <i class="fas fa-lock"></i>
                <input type="password" id="password" placeholder="Password" required autocomplete="current-password">
            </div>
            <button type="submit">
                <i class="fas fa-sign-in-alt"></i> Login Sekarang
            </button>
        </form>
    </div>
</div>

<!-- DASHBOARD -->
<div class="dashboard-wrapper" id="dashboardPage">
    <span class="logout-btn" id="logoutBtn">
        <i class="fas fa-sign-out-alt"></i> Logout
    </span>
    <header>
        <div class="header-content">
            <h1><i class="fas fa-chart-line"></i> Dashboard E-Commerce</h1>
            <p>Selamat datang kembali, <strong id="usernameDisplay">Admin</strong></p>
        </div>
    </header>

    <nav>
        <a href="#divisi"><i class="fas fa-th-large"></i> Divisi</a>
        <a href="#footer"><i class="fas fa-envelope"></i> Kontak</a>
    </nav>

    <div class="container" id="divisi">
        <div class="section-title">
            <h2>Manajemen Divisi</h2>
            <p>Pilih divisi untuk mengakses form dan sistem</p>
        </div>
        <div class="divisi-grid">
            <!-- Warehouse -->
            <div class="divisi-card">
                <div class="icon-box">
                    <i class="fas fa-warehouse"></i>
                </div>
                <h3>Warehouse</h3>
                <a href="https://script.google.com/macros/s/AKfycbxowhyNoPAzcWnxRLYHXJ41oAO-Nnfi07sJYD0BgTkT2pn-MqsdhwMbXGSNOz4lGuntJA/exec" target="_blank">
                    <i class="fas fa-truck-loading"></i> Form Checker-Defect
                </a>
            <!-- Tambahkan Font Awesome kalau belum -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<a href="https://script.google.com/macros/s/AKfycbyYeIlazPCBsSYE8aiXFU66Qdlcgwg2FP3W0lg2BbrkWAV79ZwrVH9C-cnuo5qSmyBj/exec"
   target="_blank"
  style="display: flex; align-items: center; gap: 10px; background: linear-gradient(90deg, #ffcc00, #ff6600);
          padding: 12px 20px; border-radius: 12px; color: #fff; font-weight: bold; text-decoration: none;
          box-shadow: 0 4px 10px rgba(0,0,0,0.2); transition: transform 0.2s;">
   <span>Form Serah Terima Barang ke Kurir</span>
</a>
 <h1>🎯 Pilih Style Button</h1>
        
        <div class="button-container">
            <!-- Orange (Original) -->
            <a href="https://script.google.com/macros/s/AKfycbwMVWvtSqAwpHQeQR4z_UMcDkkx0DSM5lTShwPUVAOCbA_0rrmpzfl7c_vDfSiq8NJp/exec"
               target="_blank"
               class="app-button">
                <svg class="icon-box" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <defs>
                        <linearGradient id="box1" x1="0%" y1="0%" x2="100%" y2="100%">
                            <stop offset="0%" style="stop-color:#ffcc00"/>
                            <stop offset="100%" style="stop-color:#ff6600"/>
                        </linearGradient>
                    </defs>
                    <g transform="translate(12, 10)">
                        <path d="M-5,0 L-5,5 L0,7.5 L5,5 L5,0 L0,2.5 Z" fill="url(#box1)" stroke="#fff" stroke-width="0.8"/>
                        <path d="M-5,0 L0,-2.5 L5,0 L0,2.5 Z" fill="#ffdd33" stroke="#fff" stroke-width="0.8"/>
                        <path d="M5,0 L5,5 L0,7.5 L0,2.5 Z" fill="#ff8833" stroke="#fff" stroke-width="0.8"/>
                        <path d="M-1.5,2.5 L0,4 L2.5,0.5" fill="none" stroke="#fff" stroke-width="1.5" stroke-linecap="round"/>
                    </g>
                    <path d="M17,6 A6,6 0 0,1 19,10" fill="none" stroke="#fff" stroke-width="1.2" stroke-linecap="round" opacity="0.9"/>
                    <path d="M18.5,9.5 L19,10 L18.3,10.3" fill="#fff" opacity="0.9"/>
                </svg>
                <span>APLIKASI SO Gudang - Cycle Count</span>
            </a>
<a href="https://script.google.com/macros/s/AKfycbz4WyNh7ncx617g-Y_dCDt2UlLRrs8SD7hNzV8f1F4e8YaqMRdar-LJcr3gELnfR-1Y0w/exec"
   target="_blank"
   style="display: flex; align-items: center; gap: 10px; background: linear-gradient(90deg, #ffcc00, #ff6600);
          padding: 12px 20px; border-radius: 12px; color: #fff; font-weight: bold; text-decoration: none;
          box-shadow: 0 4px 10px rgba(0,0,0,0.2); transition: transform 0.2s;">
  <img src="https://media.giphy.com/media/QBd2kLB5qDmysEXre9/giphy.gif"
       alt="Truck Animation"
       style="width: 40px; height: 40px; border-radius: 8px;">
  <span>Form APLIKASI INBOUND DARI SUPPLIER </span>
</a>
 <h1>🎯 Pilih Style Button</h1>
        
        <div class="button-container">
            <!-- Orange (Original) -->
            <a href="https://script.google.com/macros/s/AKfycbwMVWvtSqAwpHQeQR4z_UMcDkkx0DSM5lTShwPUVAOCbA_0rrmpzfl7c_vDfSiq8NJp/exec"
               target="_blank"
               class="app-button">
                <svg class="icon-box" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <defs>
                        <linearGradient id="box1" x1="0%" y1="0%" x2="100%" y2="100%">
                            <stop offset="0%" style="stop-color:#ffcc00"/>
                            <stop offset="100%" style="stop-color:#ff6600"/>
                        </linearGradient>
                    </defs>
                    <g transform="translate(12, 10)">
                        <path d="M-5,0 L-5,5 L0,7.5 L5,5 L5,0 L0,2.5 Z" fill="url(#box1)" stroke="#fff" stroke-width="0.8"/>
                        <path d="M-5,0 L0,-2.5 L5,0 L0,2.5 Z" fill="#ffdd33" stroke="#fff" stroke-width="0.8"/>
                        <path d="M5,0 L5,5 L0,7.5 L0,2.5 Z" fill="#ff8833" stroke="#fff" stroke-width="0.8"/>
                        <path d="M-1.5,2.5 L0,4 L2.5,0.5" fill="none" stroke="#fff" stroke-width="1.5" stroke-linecap="round"/>
                    </g>
                    <path d="M17,6 A6,6 0 0,1 19,10" fill="none" stroke="#fff" stroke-width="1.2" stroke-linecap="round" opacity="0.9"/>
                    <path d="M18.5,9.5 L19,10 L18.3,10.3" fill="#fff" opacity="0.9"/>
                </svg>
                <span>APLIKASI SO Gudang - Cycle Count</span>
            </a>
<a href="https://script.google.com/macros/s/AKfycbzq_P9gWPKSXo3i31yxNEhX_JQYyzxMudY25DFsAmsF2JyMPEz_1ogw6i20pXLU19HxzQ/exec"
   target="_blank"
   style="display: flex; align-items: center; gap: 10px; background: linear-gradient(90deg, #ffcc00, #ff6600);
          padding: 12px 20px; border-radius: 12px; color: #fff; font-weight: bold; text-decoration: none;
          box-shadow: 0 4px 10px rgba(0,0,0,0.2); transition: transform 0.2s;">
  <img src="https://media.giphy.com/media/QBd2kLB5qDmysEXre9/giphy.gif"
       alt="Truck Animation"
       style="width: 40px; height: 40px; border-radius: 8px;">
  <span>WAREHOUSE MANAGEMENT SYSTEM </span>
</a>

<!-- Penjualan -->
            <div class="divisi-card">
                <div class="icon-box">
                    <i class="fas fa-chart-line"></i>
                </div>
                <h3>Penjualan</h3>
                <a href="https://form.jotform.com/ID_FORM_PENJUALAN" target="_blank">
                    <i class="fas fa-file-invoice"></i> Form Penjualan
                </a>
            </div>

            <!-- Finance -->
            <div class="divisi-card">
                <div class="icon-box">
                    <i class="fas fa-money-bill-wave"></i>
                </div>
                <h3>Finance</h3>
                <a href="https://form.jotform.com/ID_FORM_FINANCE" target="_blank">
                    <i class="fas fa-calculator"></i> Form Keuangan
                </a>
            </div>

            <!-- HRD -->
            <div class="divisi-card">
                <div class="icon-box">
                    <i class="fas fa-user-tie"></i>
                </div>
                <h3>HRD</h3>
                <a href="https://script.google.com/macros/s/AKfycbwdKLs4Ygr_LIAEhByH1rLFgSH8ER524JNPsxyKqYwM6NC0DNpxC9Mg9rCcuHBe7NI2ag/exec" target="_blank">
                    <i class="fas fa-door-open"></i> Ijin Keluar Kantor
                </a>
            </div>

            <!-- Admin -->
            <div class="divisi-card">
                <div class="icon-box">
                    <i class="fas fa-user-cog"></i>
                </div>
                <h3>Admin</h3>
                <a href="https://form.jotform.com/ID_FORM_ADMIN" target="_blank">
                    <i class="fas fa-cogs"></i> Form Admin
                </a>
            </div>

            <!-- Transporter -->
            <div class="divisi-card">
                <div class="icon-box">
                    <i class="fas fa-truck"></i>
                </div>
                <h3>Transporter</h3>
                <a href="https://form.jotform.com/ID_FORM_TRANSPORTER" target="_blank">
                    <i class="fas fa-shipping-fast"></i> Form Transportasi
                </a>
            </div>
 <!-- FORM APLIKASI INPUT PEKERJAAN -->
            <script>
  lottie.loadAnimation({
    container: document.getElementById('animasiLaporan'),
    renderer: 'svg',
    loop: true,
    autoplay: true,
    path: 'https://assets5.lottiefiles.com/packages/lf20_3vbOcw.json' // contoh animasi laporan
  });
</script>


                     <h3>FORM INPUT</h3>
                <a href="https://script.google.com/macros/s/AKfycbzgNDuRI70Cis7ytoaGP_J7HXbnRxF0DxQZ1yyLetn7IqXPoGsZQ86WU84q2KuCK5PR/exec" target="_blank">
                    <i class="fas fa-box"></i> Form Laporan
                </a>
            </div>
        </div>
    </div>

    <footer id="footer">
        <p>&copy; 2025 Dashboard E-Commerce. All rights reserved.</p>
        <p>Hubungi kami: <a href="mailto:sendi.surprice@gmail.com">sendi.surprice@gmail.com</a></p>
    </footer>
</div>

<script>
// Login credentials
const VALID_USERNAME = 'admin';
const VALID_PASSWORD = 'admin1234';

// Elements
const loginForm = document.getElementById('loginForm');
const loginPage = document.getElementById('loginPage');
const dashboardPage = document.getElementById('dashboardPage');
const errorMsg = document.getElementById('errorMsg');
const errorText = document.getElementById('errorText');
const logoutBtn = document.getElementById('logoutBtn');
const usernameDisplay = document.getElementById('usernameDisplay');

// Check if user is already logged in
window.addEventListener('DOMContentLoaded', () => {
    const isLoggedIn = sessionStorage.getItem('isLoggedIn');
    const username = sessionStorage.getItem('username');
    
    if (isLoggedIn === 'true' && username) {
        showDashboard(username);
    }
});

// Login form submit
loginForm.addEventListener('submit', (e) => {
    e.preventDefault();
    
    const username = document.getElementById('username').value.trim();
    const password = document.getElementById('password').value.trim();
    
    if (username === VALID_USERNAME && password === VALID_PASSWORD) {
        // Save login state
        sessionStorage.setItem('isLoggedIn', 'true');
        sessionStorage.setItem('username', username);
        
        // Hide error
        errorMsg.classList.remove('show');
        
        // Show dashboard
        showDashboard(username);
    } else {
        // Show error
        errorText.textContent = 'Username atau Password salah!';
        errorMsg.classList.add('show');
        
        // Shake animation
        loginForm.style.animation = 'none';
        setTimeout(() => {
            loginForm.style.animation = '';
        }, 10);
    }
});

// Logout button
logoutBtn.addEventListener('click', () => {
    sessionStorage.removeItem('isLoggedIn');
    sessionStorage.removeItem('username');
    
    loginPage.style.display = 'flex';
    dashboardPage.classList.remove('active');
    
    // Clear form
    document.getElementById('username').value = '';
    document.getElementById('password').value = '';
    errorMsg.classList.remove('show');
});

// Show dashboard function
function showDashboard(username) {
    loginPage.style.display = 'none';
    dashboardPage.classList.add('active');
    usernameDisplay.textContent = username;
}

// Smooth scroll for navigation
document.querySelectorAll('nav a').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
        const href = this.getAttribute('href');
        if (href.startsWith('#')) {
            e.preventDefault();
            const target = document.querySelector(href);
            if (target) {
                target.scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            }
        }
    });
});
</script>
    import React from 'react';

    const InboundPage = () => {
      return (
        <div dangerouslySetInnerHTML={{<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Manajemen Inbound</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }
        
        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 40px;
            text-align: center;
        }
        
        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
        }
        
        .header p {
            font-size: 1.2em;
            opacity: 0.9;
        }
        
        .content {
            padding: 40px;
        }
        
        .section {
            margin-bottom: 50px;
        }
        
        .section-title {
            font-size: 1.8em;
            color: #667eea;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 3px solid #667eea;
        }
        
        .template-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .template-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .template-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }
        
        .template-card h3 {
            color: #333;
            margin-bottom: 15px;
            font-size: 1.4em;
        }
        
        .template-card p {
            color: #666;
            margin-bottom: 20px;
            line-height: 1.6;
        }
        
        .btn-group {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 12px 24px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }
        
        .btn-excel {
            background: #217346;
            color: white;
        }
        
        .btn-excel:hover {
            background: #1a5c37;
            transform: scale(1.05);
        }
        
        .btn-pdf {
            background: #d32f2f;
            color: white;
        }
        
        .btn-pdf:hover {
            background: #b71c1c;
            transform: scale(1.05);
        }
        
        .workflow {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 30px;
            margin-top: 30px;
        }
        
        .flow-step {
            display: flex;
            align-items: flex-start;
            margin-bottom: 30px;
            position: relative;
        }
        
        .flow-step:not(:last-child)::after {
            content: '↓';
            position: absolute;
            left: 35px;
            bottom: -25px;
            font-size: 2em;
            color: #667eea;
            font-weight: bold;
        }
        
        .step-number {
            background: #667eea;
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5em;
            font-weight: bold;
            flex-shrink: 0;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }
        
        .step-content {
            margin-left: 20px;
            flex: 1;
        }
        
        .step-title {
            font-size: 1.3em;
            color: #333;
            margin-bottom: 10px;
            font-weight: 600;
        }
        
        .step-description {
            color: #666;
            line-height: 1.6;
            margin-bottom: 10px;
        }
        
        .step-team {
            background: #e3f2fd;
            padding: 10px 15px;
            border-radius: 8px;
            color: #1976d2;
            font-weight: 600;
            display: inline-block;
            margin-top: 5px;
        }
        
        .visual-flow {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-top: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .zone-container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-top: 20px;
        }
        
        .zone {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            padding: 25px;
            border-radius: 15px;
            color: white;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .zone:nth-child(2) {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
        }
        
        .zone:nth-child(3) {
            background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
        }
        
        .zone h4 {
            font-size: 1.3em;
            margin-bottom: 15px;
        }
        
        .zone-icon {
            font-size: 3em;
            margin-bottom: 15px;
        }
        
        .zone ul {
            list-style: none;
            text-align: left;
            margin-top: 15px;
        }
        
        .zone li {
            padding: 8px 0;
            border-bottom: 1px solid rgba(255,255,255,0.3);
        }
        
        .zone li:last-child {
            border-bottom: none;
        }
        
        .tips-box {
            background: #fff3cd;
            border-left: 5px solid #ffc107;
            padding: 20px;
            border-radius: 8px;
            margin-top: 30px;
        }
        
        .tips-box h4 {
            color: #856404;
            margin-bottom: 15px;
            font-size: 1.2em;
        }
        
        .tips-box ul {
            color: #856404;
            margin-left: 20px;
            line-height: 1.8;
        }
        
        @media (max-width: 768px) {
            .zone-container {
                grid-template-columns: 1fr;
            }
            
            .header h1 {
                font-size: 1.8em;
            }
            
            .content {
                padding: 20px;
            }
        }
        
        .color-legend {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }
        
        .color-item {
            display: flex;
            align-items: center;
            padding: 15px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        
        .color-box {
            width: 40px;
            height: 40px;
            border-radius: 8px;
            margin-right: 15px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }
        
        .color-red { background: #f44336; }
        .color-blue { background: #2196f3; }
        .color-green { background: #4caf50; }
        .color-yellow { background: #ffeb3b; }
        .color-black { background: #000; }
        
        .timeline {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-top: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .timeline-item {
            display: flex;
            margin-bottom: 20px;
            align-items: center;
        }
        
        .timeline-time {
            background: #667eea;
            color: white;
            padding: 10px 20px;
            border-radius: 25px;
            font-weight: bold;
            min-width: 100px;
            text-align: center;
        }
        
        .timeline-content {
            margin-left: 20px;
            flex: 1;
            padding: 15px;
            background: #f5f7fa;
            border-radius: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>📦 Sistem Manajemen Inbound</h1>
            <p>Panduan Lengkap & Template untuk Proses Bongkar Kontainer</p>
        </div>
        
        <div class="content">
            <!-- Template Downloads -->
            <div class="section">
                <h2 class="section-title">📥 Download Template</h2>
                
                <div class="template-grid">
                    <div class="template-card">
                        <h3>📋 Tally Sheet Bongkar</h3>
                        <p>Template untuk menghitung jumlah dus per SKU saat bongkar kontainer</p>
                        <div class="btn-group">
                            <button class="btn btn-excel" onclick="downloadTallySheet()">📊 Download Excel</button>
                            <button class="btn btn-pdf" onclick="downloadTallySheetPDF()">📄 Download PDF</button>
                        </div>
                    </div>
                    
                    <div class="template-card">
                        <h3>📝 Checklist Admin</h3>
                        <p>Checklist lengkap untuk admin sebelum, saat, dan setelah bongkar</p>
                        <div class="btn-group">
                            <button class="btn btn-excel" onclick="downloadChecklistAdmin()">📊 Download Excel</button>
                            <button class="btn btn-pdf" onclick="downloadChecklistAdminPDF()">📄 Download PDF</button>
                        </div>
                    </div>
                    
                    <div class="template-card">
                        <h3>📊 Laporan Bongkar Kontainer</h3>
                        <p>Format laporan harian untuk kepala operasional</p>
                        <div class="btn-group">
                            <button class="btn btn-excel" onclick="downloadLaporanBongkar()">📊 Download Excel</button>
                            <button class="btn btn-pdf" onclick="downloadLaporanBongkarPDF()">📄 Download PDF</button>
                        </div>
                    </div>
                    
                    <div class="template-card">
                        <h3>🏷️ Daftar Kode Warna Stiker</h3>
                        <p>Panduan penggunaan stiker warna untuk kategorisasi dus</p>
                        <div class="btn-group">
                            <button class="btn btn-excel" onclick="downloadKodeWarna()">📊 Download Excel</button>
                            <button class="btn btn-pdf" onclick="downloadKodeWarnaPDF()">📄 Download PDF</button>
                        </div>
                    </div>
                    
                    <div class="template-card">
                        <h3>⏱️ Timeline Proses Inbound</h3>
                        <p>Jadwal dan target waktu setiap tahapan proses</p>
                        <div class="btn-group">
                            <button class="btn btn-excel" onclick="downloadTimeline()">📊 Download Excel</button>
                            <button class="btn btn-pdf" onclick="downloadTimelinePDF()">📄 Download PDF</button>
                        </div>
                    </div>
                    
                    <div class="template-card">
                        <h3>👥 Pembagian Tim & Tugas</h3>
                        <p>Struktur tim dan job description setiap posisi</p>
                        <div class="btn-group">
                            <button class="btn btn-excel" onclick="downloadPembagianTim()">📊 Download Excel</button>
                            <button class="btn btn-pdf" onclick="downloadPembagianTimPDF()">📄 Download PDF</button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Workflow Visualization -->
            <div class="section">
                <h2 class="section-title">🔄 Alur Proses Lengkap</h2>
                
                <div class="workflow">
                    <div class="flow-step">
                        <div class="step-number">1</div>
                        <div class="step-content">
                            <div class="step-title">📋 Persiapan (H-2 Sebelum Kontainer Datang)</div>
                            <div class="step-description">
                                • Minta picking list dari supplier<br>
                                • Siapkan tally sheet kosong per SKU<br>
                                • Cek lokasi rak kosong di gudang utama<br>
                                • Siapkan stiker warna & alat tulis<br>
                                • Cetak barcode untuk SKU lama
                            </div>
                            <span class="step-team">👥 Tim: Admin 1 & 2</span>
                        </div>
                    </div>
                    
                    <div class="flow-step">
                        <div class="step-number">2</div>
                        <div class="step-content">
                            <div class="step-title">🚚 Bongkar Kontainer (Hari H)</div>
                            <div class="step-description">
                                <strong>ZONA 1 - Di Kontainer:</strong><br>
                                • Admin 1: Panggil SKU & jumlah dari packing list<br>
                                • Pekerja 1-2: Keluarkan dus dari kontainer<br>
                                • Admin 2: Cek kondisi dus + tempel stiker warna<br><br>
                                <strong>Estimasi Waktu: 5-6 jam untuk 600 dus</strong>
                            </div>
                            <span class="step-team">👥 Tim: 2 Admin + 4 Pekerja</span>
                        </div>
                    </div>
                    
                    <div class="flow-step">
                        <div class="step-number">3</div>
                        <div class="step-content">
                            <div class="step-title">📦 Susun di Area Transit (Hari H)</div>
                            <div class="step-description">
                                <strong>ZONA 2 - Depan Ruko:</strong><br>
                                • Pekerja 3-4: Susun dus berdasarkan warna stiker<br>
                                • Kelompokkan SKU yang sama<br>
                                • Pisahkan dus rusak<br><br>
                                <strong>Estimasi Waktu: 1-2 jam</strong>
                            </div>
                            <span class="step-team">👥 Tim: Pekerja 3 & 4</span>
                        </div>
                    </div>
                    
                    <div class="flow-step">
                        <div class="step-number">4</div>
                        <div class="step-content">
                            <div class="step-title">🏢 Angkat ke Dalam Ruko (Hari H)</div>
                            <div class="step-description">
                                <strong>ZONA 3 - Dalam Ruko:</strong><br>
                                • Lantai 1: SKU baru (untuk foto produk)<br>
                                • Lantai 4: SKU lama (langsung ke labeling)<br>
                                • Susun rapi per kelompok SKU<br><br>
                                <strong>Estimasi Waktu: 1-2 jam</strong>
                            </div>
                            <span class="step-team">👥 Tim: Semua Pekerja</span>
                        </div>
                    </div>
                    
                    <div class="flow-step">
                        <div class="step-number">5</div>
                        <div class="step-content">
                            <div class="step-title">📸 Quality Check & Foto (H+1)</div>
                            <div class="step-description">
                                • Sample 1-2 dus per SKU<br>
                                • Cek kualitas produk<br>
                                • Foto produk SKU baru untuk marketplace<br>
                                • Ukur dimensi produk<br><br>
                                <strong>Estimasi Waktu: 1-2 hari</strong>
                            </div>
                            <span class="step-team">👥 Tim: Admin 2 + 1 Pekerja</span>
                        </div>
                    </div>
                    
                    <div class="flow-step">
                        <div class="step-number">6</div>
                        <div class="step-content">
                            <div class="step-title">🏷️ Labeling Barcode (H+1 s/d H+7)</div>
                            <div class="step-description">
                                <strong>Prioritas Labeling:</strong><br>
                                • Hari 1-3: SKU lama + fast moving<br>
                                • Hari 4-7: SKU baru + slow moving<br>
                                • Labeling bertahap sambil mutasi<br><br>
                                <strong>Target: Selesai dalam 7 hari</strong>
                            </div>
                            <span class="step-team">👥 Tim: }} />
      );
    };

    export default InboundPage;
    

