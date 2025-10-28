# E-Learning-Pemograman-Web-1
Code index.html
'''
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Perumahan Asri - M Fikri Nasrulloh</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h2>Perumahan Asri</h2>
  </header>

  <main>
    <h1>Selamat Datang di Perumahan Asri</h1>

    <p>Perumahan Asri adalah kawasan hunian modern dengan lingkungan hijau yang nyaman bagi keluarga. Setiap rumah dirancang dengan konsep ramah lingkungan dan dilengkapi dengan fasilitas umum yang memadai.</p>

    <p>Dengan lokasi yang strategis, Perumahan Asri mudah dijangkau dari pusat kota, sekolah, dan pusat perbelanjaan. Keamanan 24 jam menjamin ketenangan Anda dan keluarga.</p>

    <p>Kami menyediakan berbagai tipe rumah mulai dari satu lantai hingga dua lantai, dengan desain minimalis dan harga yang terjangkau untuk semua kalangan.</p>

    <div class="button-container">
      <button id="tombolWaktu">Tampilkan Waktu Sekarang</button>
      <button id="tombolInfo">Lihat Info Tipe Rumah</button>
    </div>

    <div id="waktu"></div>
  </main>

  <footer>
    <p>Dibuat oleh: <strong>M Fikri Nasrulloh</strong> | NPM: 23552011337</p>
  </footer>

  <!-- POPUP MODAL -->
  <div id="popup" class="popup">
    <div class="popup-content">
      <h2>Tipe Rumah di Perumahan Asri</h2>
      <img src="https://images.unsplash.com/photo-1560185127-6ed189bf02f4?auto=format&fit=crop&w=800&q=80" alt="Rumah Asri">
      <p><strong>Tipe 36</strong> — Cocok untuk keluarga kecil, terdiri dari 2 kamar tidur dan 1 kamar mandi.</p>
      <p><strong>Tipe 45</strong> — Desain modern dengan ruang tamu luas dan halaman belakang.</p>
      <p><strong>Tipe 60</strong> — Ideal untuk keluarga besar dengan 3 kamar tidur dan garasi.</p>
      <button class="close-btn" id="tutupPopup">Tutup</button>
    </div>
  </div>
  '''

  Code style.css
  '''
  /* ======= GAYA DASAR ======= */
body {
  font-family: Arial, sans-serif;
  color: #ffffff;
  margin: 0;
  padding: 0;
  background: url("https://images.unsplash.com/photo-1600585154340-be6161a56a0c?auto=format&fit=crop&w=1400&q=80") no-repeat center center fixed;
  background-size: cover;
  position: relative;
}

/* Tambahkan overlay agar teks tetap jelas */
body::before {
  content: "";
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 50, 0, 0.6);
  z-index: -1;
}

header {
  background-color: rgba(56, 142, 60, 0.85);
  color: white;
  text-align: center;
  padding: 20px;
  border-bottom: 3px solid #a5d6a7;
}

main {
  padding: 20px;
  max-width: 800px;
  margin: auto;
  background-color: rgba(255, 255, 255, 0.15);
  border-radius: 10px;
  backdrop-filter: blur(5px);
}

h1 {
  text-align: center;
  color: #ffffff;
}

p {
  line-height: 1.6;
  text-align: justify;
}

.button-container {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 30px;
}

button {
  padding: 10px 20px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: 0.3s;
}

button:hover {
  background-color: #2e7d32;
}

footer {
  text-align: center;
  background-color: rgba(200, 230, 201, 0.85);
  padding: 10px;
  margin-top: 20px;
  color: #1b5e20;
  font-weight: bold;
}

#waktu {
  text-align: center;
  font-weight: bold;
  margin-top: 10px;
  color: #ffffff;
  font-size: 18px;
}

/* ===== POPUP MODAL ===== */
.popup {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: none;
  justify-content: center;
  align-items: center;
  z-index: 999;
}

.popup-content {
  background-color: white;
  border-radius: 10px;
  width: 90%;
  max-width: 600px;
  padding: 20px;
  text-align: center;
  color: #1b5e20;
  animation: fadeIn 0.4s ease-in-out;
}

.popup-content h2 {
  margin-bottom: 15px;
  color: #388e3c;
}

.popup-content img {
  width: 100%;
  border-radius: 10px;
  margin-bottom: 15px;
}

.popup-content p {
  text-align: left;
  margin-bottom: 10px;
}

.close-btn {
  background-color: #388e3c;
  color: white;
  padding: 8px 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 15px;
}

.close-btn:hover {
  background-color: #1b5e20;
}

@keyframes fadeIn {
  from {opacity: 0; transform: translateY(-10px);}
  to {opacity: 1; transform: translateY(0);}
}
'''

code script.js
'''
// Tampilkan waktu sekarang
document.getElementById("tombolWaktu").addEventListener("click", function() {
  const waktuSekarang = new Date();
  document.getElementById("waktu").innerHTML =
    "Waktu sekarang: " + waktuSekarang.toLocaleString();
});

// Popup Info Rumah
const popup = document.getElementById("popup");
const tombolInfo = document.getElementById("tombolInfo");
const tutupPopup = document.getElementById("tutupPopup");

tombolInfo.addEventListener("click", function() {
  popup.style.display = "flex";
});

tutupPopup.addEventListener("click", function() {
  popup.style.display = "none";
});

window.addEventListener("click", function(e) {
  if (e.target === popup) {
    popup.style.display = "none";
  }
});
'''

  <script src="script.js"></script>
</body>
</html>
