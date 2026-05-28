<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pendaftaran Ujian - Verifikasi</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f172a, #1e2937);
            color: #e2e8f0;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        /* --- STYLES UNTUK VERIFIKASI (Dari Anda) --- */
        .container {
            text-align: center;
            max-width: 420px;
            padding: 40px 30px;
            background: rgba(15, 23, 42, 0.95);
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid #334155;
            transition: opacity 0.5s ease;
        }

        h1 {
            font-size: 28px;
            margin-bottom: 12px;
            color: #f1f5f9;
        }

        .divider {
            width: 80px;
            height: 3px;
            background: linear-gradient(to right, #3b82f6, #60a5fa);
            margin: 15px auto;
            border-radius: 2px;
        }

        p {
            font-size: 17px;
            color: #cbd5e1;
            margin-bottom: 35px;
            line-height: 1.5;
        }

        .slider-container {
            position: relative;
            width: 100%;
            height: 60px;
            background: #1e2937;
            border-radius: 50px;
            overflow: hidden;
            border: 2px solid #334155;
            cursor: grab;
        }

        .slider-track {
            position: absolute;
            height: 100%;
            background: linear-gradient(to right, #3b82f6, #22c55e);
            width: 0%;
            transition: width 0.1s;
        }

        .slider-thumb {
            position: absolute;
            width: 58px;
            height: 58px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            left: 0;
            transition: left 0.1s;
            user-select: none;
        }

        .success {
            animation: successPulse 1s;
        }

        @keyframes successPulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.08); }
            100% { transform: scale(1); }
        }

        .footer {
            margin-top: 30px;
            font-size: 13px;
            color: #64748b;
        }

        /* --- STYLES UNTUK HALAMAN HASIL (BARU) --- */
        #exam-result {
            display: none; /* Disembunyikan awalnya */
            text-align: center;
            max-width: 500px;
            width: 90%;
            padding: 40px;
            background: rgba(30, 41, 55, 0.95);
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid #3b82f6;
            animation: fadeIn 0.8s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .result-title {
            font-size: 24px;
            color: #60a5fa;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 1px;
            border-bottom: 1px solid #334155;
            padding-bottom: 15px;
        }

        .info-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            font-size: 16px;
            border-bottom: 1px dashed #334155;
            padding-bottom: 8px;
        }

        .label {
            color: #94a3b8;
            font-weight: 600;
        }

        .value {
            color: #f1f5f9;
            font-weight: bold;
            text-align: right;
        }

        .status-active {
            color: #4ade80;
        }

        .btn-link {
            display: inline-block;
            margin-top: 25px;
            padding: 12px 25px;
            background: linear-gradient(to right, #3b82f6, #2563eb);
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-weight: bold;
            transition: transform 0.2s;
        }

        .btn-link:hover {
            transform: scale(1.05);
            box-shadow: 0 0 15px rgba(59, 130, 246, 0.5);
        }

    </style>
</head>
<body>

    <!-- BAGIAN 1: VERIFIKASI (Akan hilang setelah sukses) -->
    <div class="container" id="verification-box">
        <h1>Verifikasi Keamanan</h1>
        <div class="divider"></div>
        <p>Geser tombol ke kanan untuk melanjutkan</p>
        
        <div class="slider-container" id="slider">
            <div class="slider-track" id="track"></div>
            <div class="slider-thumb" id="thumb">→</div>
        </div>

        <div class="footer">
            Powered by Security Check
        </div>
    </div>

    <!-- BAGIAN 2: HASIL UJIAN (Muncul setelah sukses) -->
    <div id="exam-result">
        <h2 class="result-title">Pendaftaran Ujian</h2>
        
        <div class="info-row">
            <span class="label">KODE</span>
            <span class="value">BELAJAR.ID</span>
        </div>
        <div class="info-row">
            <span class="label">MAPEL</span>
            <span class="value">PJOK & AGAMA</span>
        </div>
        <div class="info-row">
            <span class="label">MULAI</span>
            <span class="value">28 MEI</span>
        </div>
        <div class="info-row">
            <span class="label">AKHIR</span>
            <span class="value">30 MEI</span>
        </div>
        <div class="info-row" style="border-bottom: none;">
            <span class="label">STATUS</span>
            <span class="value status-active">AKTIF ✅️</span>
        </div>

        <a href="https://s.id/BELAJAR-GO-ID" target="_blank" class="btn-link">
            WEBSITE UJIAN : s.id/BELAJAR-GO-ID
        </a>
    </div>

    <script>
        const slider = document.getElementById('slider');
        const thumb = document.getElementById('thumb');
        const track = document.getElementById('track');
        const verificationBox = document.getElementById('verification-box');
        const examResult = document.getElementById('exam-result');
        
        let isDragging = false;
        let startX = 0;
        let currentX = 0;
        // Pastikan lebar dihitung setelah elemen dimuat
        const maxWidth = slider.offsetWidth - thumb.offsetWidth;

        function updateSlider() {
            const percentage = Math.min(Math.max(0, currentX / maxWidth), 1);
            thumb.style.left = `${currentX}px`;
            track.style.width = `${percentage * 100}%`;
        }

        function completeVerification() {
            thumb.innerHTML = '✓';
            thumb.style.background = '#22c55e';
            thumb.classList.add('success');
            
            // Efek transisi
            setTimeout(() => {
                // Sembunyikan kotak verifikasi
                verificationBox.style.opacity = '0';
                
                setTimeout(() => {
                    verificationBox.style.display = 'none';
                    // Tampilkan hasil ujian
                    examResult.style.display = 'block';
                }, 500); // Waktu tunggu untuk animasi fade out
                
            }, 800);
        }

        // Mouse events
        thumb.addEventListener('mousedown', (e) => {
            isDragging = true;
            startX = e.clientX - currentX;
            thumb.style.cursor = 'grabbing';
        });

        document.addEventListener('mousemove', (e) => {
            if (!isDragging) return;
            e.preventDefault(); // Mencegah seleksi teks
            currentX = Math.min(Math.max(0, e.clientX - startX), maxWidth);
            updateSlider();
        });

        document.addEventListener('mouseup', () => {
            if (!isDragging) return;
            isDragging = false;
            thumb.style.cursor = 'grab';
            
            if (currentX > maxWidth * 0.85) {
                completeVerification();
            } else {
                // Kembali ke awal
                currentX = 0;
                updateSlider();
            }
        });

        // Touch support (mobile)
        thumb.addEventListener('touchstart', (e) => {
            isDragging = true;
            startX = e.touches[0].clientX - currentX;
        }, {passive: false});

        document.addEventListener('touchmove', (e) => {
            if (!isDragging) return;
            e.preventDefault(); // Mencegah scroll layar saat geser slider
            currentX = Math.min(Math.max(0, e.touches[0].clientX - startX), maxWidth);
            updateSlider();
        }, {passive: false});

        document.addEventListener('touchend', () => {
            if (!isDragging) return;
            isDragging = false;
            
            if (currentX > maxWidth * 0.85) {
                completeVerification();
            } else {
                currentX = 0;
                updateSlider();
            }
        });
    </script>
</body>
</html>
