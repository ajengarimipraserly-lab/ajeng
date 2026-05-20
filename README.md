<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes, viewport-fit=cover">
  <title>Ajeng • Keuangan Jajan</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #f9efe2 0%, #f4e5d3 100%);
      font-family: 'Segoe UI', 'Inter', system-ui, -apple-system, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      padding: 20px;
    }

    .app-container {
      max-width: 480px;
      width: 100%;
      background: rgba(255, 251, 245, 0.9);
      backdrop-filter: blur(18px);
      background: #fffdf7;
      border-radius: 42px;
      box-shadow: 0 25px 50px -10px rgba(90, 60, 40, 0.25), inset 0 1px 0 rgba(255,255,240,0.7);
      padding: 24px 20px 30px;
      border: 1px solid rgba(200, 160, 120, 0.2);
      display: flex;
      flex-direction: column;
      gap: 24px;
    }

    /* Header */
    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo-icon {
      background: #c49a6c;
      color: white;
      width: 44px;
      height: 44px;
      border-radius: 18px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 26px;
      font-weight: 600;
      background: linear-gradient(135deg, #b5835a, #8b5a3c);
      box-shadow: 0 8px 14px rgba(140, 90, 50, 0.3);
    }

    .brand h1 {
      font-size: 2.2rem;
      font-weight: 700;
      letter-spacing: -0.5px;
      color: #4a3320;
      line-height: 1;
    }
    .brand span {
      font-size: 0.9rem;
      color: #9b7b62;
      font-weight: 500;
      display: block;
      letter-spacing: 0.3px;
    }

    .saldo-card {
      background: #f3ede5;
      border-radius: 100px;
      padding: 10px 20px;
      background: #f6efe4;
      box-shadow: 0 4px 8px rgba(0,0,0,0.02);
      border: 1px solid #e7d7c4;
    }
    .saldo-label {
      font-size: 0.7rem;
      text-transform: uppercase;
      letter-spacing: 0.8px;
      color: #8b6f55;
    }
    .saldo-value {
      font-weight: 700;
      font-size: 1.3rem;
      color: #4a3722;
    }

    /* Menu grid */
    .menu-section {
      display: flex;
      flex-direction: column;
      gap: 14px;
    }

    .section-title {
      font-size: 1rem;
      font-weight: 600;
      color: #5e4532;
      letter-spacing: 0.3px;
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 4px;
    }

    .menu-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
    }

    .menu-item {
      background: white;
      border-radius: 24px;
      padding: 18px 10px 16px;
      background: #fefcf7;
      border: 1px solid #f0e2d0;
      box-shadow: 0 10px 18px -8px rgba(120, 70, 30, 0.12);
      transition: all 0.2s ease;
      cursor: pointer;
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      backdrop-filter: blur(2px);
      position: relative;
    }

    .menu-item:active {
      transform: scale(0.96);
      background: #faf3e9;
      box-shadow: 0 5px 10px rgba(110, 70, 30, 0.2);
      border-color: #cdb194;
    }

    .emoji-badge {
      font-size: 2.4rem;
      filter: drop-shadow(0 6px 6px rgba(0,0,0,0.1));
      margin-bottom: 6px;
    }

    .menu-name {
      font-weight: 700;
      font-size: 0.95rem;
      color: #4b3621;
      line-height: 1.3;
      margin-bottom: 6px;
      text-transform: capitalize;
    }

    .price-tag {
      background: #efe3d3;
      border-radius: 30px;
      padding: 5px 14px;
      font-weight: 700;
      font-size: 0.9rem;
      color: #5e3e28;
      background: #f4e8db;
      letter-spacing: 0.2px;
      border: 1px solid #dacbbc;
    }

    /* Riwayat */
    .riwayat-box {
      background: #faf7f2;
      border-radius: 28px;
      padding: 16px 14px;
      border: 1px solid #e7d7c4;
      display: flex;
      flex-direction: column;
      gap: 10px;
      max-height: 200px;
      overflow-y: auto;
    }

    .history-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-weight: 600;
      color: #5a4330;
    }

    .clear-btn {
      background: none;
      border: none;
      color: #b48b6b;
      font-weight: 600;
      font-size: 0.8rem;
      cursor: pointer;
      padding: 6px 12px;
      border-radius: 30px;
      background: #f1e7db;
      transition: 0.2s;
    }
    .clear-btn:active {
      background: #e3cfba;
      color: #4d3320;
    }

    .history-list {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 8px;
      font-size: 0.9rem;
    }

    .history-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px dashed #e2cfb5;
      padding-bottom: 6px;
    }

    .history-left {
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .history-emoji {
      font-size: 1.2rem;
    }
    .history-desc {
      font-weight: 500;
      color: #4b3621;
    }
    .history-price {
      font-weight: 700;
      color: #7b4d2e;
    }
    .empty-message {
      color: #b9a088;
      font-style: italic;
      text-align: center;
      padding: 10px 0;
    }

    .total-footer {
      display: flex;
      justify-content: space-between;
      font-weight: 700;
      font-size: 1.1rem;
      background: #efe3d3;
      padding: 12px 16px;
      border-radius: 20px;
      color: #3e2e1f;
      margin-top: 4px;
    }

    button {
      background: none;
      border: none;
      font-family: inherit;
    }

    /* scroll styling */
    .riwayat-box::-webkit-scrollbar {
      width: 4px;
    }
    .riwayat-box::-webkit-scrollbar-track {
      background: #f3ede5;
      border-radius: 10px;
    }
    .riwayat-box::-webkit-scrollbar-thumb {
      background: #ccb191;
      border-radius: 10px;
    }
  </style>
</head>
<body>
<div class="app-container">
  <!-- Header aplikasi AJENG -->
  <div class="header">
    <div class="brand">
      <div class="logo-icon">🪷</div>
      <div>
        <h1>Ajeng</h1>
        <span>jajan hemat • happy</span>
      </div>
    </div>
    <div class="saldo-card">
      <div class="saldo-label">💸 total jajan</div>
      <div class="saldo-value" id="totalDisplay">Rp0</div>
    </div>
  </div>

  <!-- Menu grid: Kopi, Dimsum Mentai, Chikuro, Dubai Chewy Cocie -->
  <div class="menu-section">
    <div class="section-title">
      <span>🍽️</span> Menu Favorit
    </div>
    <div class="menu-grid">
      <!-- Kopi -->
      <div class="menu-item" data-menu="Kopi" data-price="25000">
        <div class="emoji-badge">☕</div>
        <div class="menu-name">Kopi</div>
        <div class="price-tag">Rp25.000</div>
      </div>
      <!-- Dimsum Mentai -->
      <div class="menu-item" data-menu="Dimsum Mentai" data-price="32000">
        <div class="emoji-badge">🥟</div>
        <div class="menu-name">Dimsum Mentai</div>
        <div class="price-tag">Rp32.000</div>
      </div>
      <!-- Chikuro -->
      <div class="menu-item" data-menu="Chikuro" data-price="18000">
        <div class="emoji-badge">🍢</div>
        <div class="menu-name">Chikuro</div>
        <div class="price-tag">Rp18.000</div>
      </div>
      <!-- Dubai Chewy Cocie -->
      <div class="menu-item" data-menu="Dubai Chewy Cocie" data-price="27000">
        <div class="emoji-badge">🍪</div>
        <div class="menu-name">Dubai Chewy Cocie</div>
        <div class="price-tag">Rp27.000</div>
      </div>
    </div>
  </div>

  <!-- Riwayat Transaksi -->
  <div>
    <div class="history-header">
      <span>📋 Riwayat Jajan</span>
      <button class="clear-btn" id="clearHistoryBtn">🗑️ Hapus semua</button>
    </div>
    <div class="riwayat-box" id="historyContainer">
      <ul class="history-list" id="historyList">
        <li class="empty-message">Belum ada transaksi. Klik menu di atas 👆</li>
      </ul>
    </div>
    <div class="total-footer">
      <span>Total pengeluaran</span>
      <span id="totalPengeluaran">Rp0</span>
    </div>
  </div>
</div>

<script>
  (function() {
    // Nama aplikasi: Ajeng
    // Data menu (sesuai permintaan)
    const menuItems = document.querySelectorAll('.menu-item');
    
    // State keuangan
    let transactions = []; // array of { name, price, timestamp }
    
    // Element DOM
    const historyListEl = document.getElementById('historyList');
    const totalDisplayEl = document.getElementById('totalDisplay');
    const totalPengeluaranEl = document.getElementById('totalPengeluaran');
    const clearBtn = document.getElementById('clearHistoryBtn');
    
    // Format rupiah
    const formatRupiah = (amount) => {
      return 'Rp' + amount.toLocaleString('id-ID');
    };
    
    // Simpan ke localStorage
    const saveToStorage = () => {
      try {
        localStorage.setItem('ajeng_jajan_transactions', JSON.stringify(transactions));
      } catch (e) {
        // fallback silently
      }
    };
    
    // Muat dari localStorage
    const loadFromStorage = () => {
      try {
        const stored = localStorage.getItem('ajeng_jajan_transactions');
        if (stored) {
          transactions = JSON.parse(stored);
          // validasi sederhana
          if (!Array.isArray(transactions)) transactions = [];
        } else {
          transactions = [];
        }
      } catch (e) {
        transactions = [];
      }
    };
    
    // Hitung total
    const calculateTotal = () => {
      return transactions.reduce((sum, t) => sum + (t.price || 0), 0);
    };
    
    // Update UI: history list, total, saldo display
    const renderUI = () => {
      // Update history list
      if (!historyListEl) return;
      
      if (transactions.length === 0) {
        historyListEl.innerHTML = '<li class="empty-message">Belum ada transaksi. Klik menu di atas 👆</li>';
      } else {
        // Tampilkan maksimal 8 item terbaru agar tidak penuh (tapi tetap bisa scroll)
        const recent = [...transactions].reverse(); // terbaru di atas
        historyListEl.innerHTML = recent.map(t => {
          const timeStr = t.timestamp ? new Date(t.timestamp).toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' }) : '';
          return `
            <li class="history-item">
              <div class="history-left">
                <span class="history-emoji">🧾</span>
                <span class="history-desc">${t.name || 'Menu'}</span>
                <span style="font-size:0.7rem; color:#b29578;">${timeStr}</span>
              </div>
              <span class="history-price">${formatRupiah(t.price)}</span>
            </li>
          `;
        }).join('');
      }
      
      // Update total
      const total = calculateTotal();
      if (totalDisplayEl) totalDisplayEl.textContent = formatRupiah(total);
      if (totalPengeluaranEl) totalPengeluaranEl.textContent = formatRupiah(total);
    };
    
    // Tambah transaksi
    const addTransaction = (name, price) => {
      if (!name || typeof price !== 'number' || price <= 0) return;
      
      const newTransaction = {
        name: name,
        price: price,
        timestamp: new Date().toISOString(),
      };
      
      transactions.push(newTransaction);
      saveToStorage();
      renderUI();
      
      // Efek kecil opsional: getar halus? tidak diperlukan, cukup UI update.
    };
    
    // Hapus semua riwayat
    const clearAllHistory = () => {
      if (transactions.length === 0) return;
      
      // Konfirmasi ramah
      if (confirm('Hapus semua riwayat jajan di Ajeng?')) {
        transactions = [];
        saveToStorage();
        renderUI();
      }
    };
    
    // Event listener untuk setiap menu item (bisa diklik)
    const attachMenuEvents = () => {
      menuItems.forEach(item => {
        item.addEventListener('click', function(e) {
          // Ambil data dari atribut
          const menuName = this.getAttribute('data-menu');
          const priceStr = this.getAttribute('data-price');
          const price = parseInt(priceStr, 10);
          
          if (!menuName || isNaN(price)) return;
          
          // Tambahkan transaksi
          addTransaction(menuName, price);
          
          // Feedback kecil: ubah sementara warna? opsional, biarkan animasi scale.
        });
      });
    };
    
    // Clear button event
    if (clearBtn) {
      clearBtn.addEventListener('click', clearAllHistory);
    }
    
    // Inisialisasi aplikasi
    const init = () => {
      loadFromStorage();
      renderUI();
      attachMenuEvents();
    };
    
    // Jalankan setelah DOM siap
    window.addEventListener('DOMContentLoaded', init);
  })();
</script>
</body>
</html>
