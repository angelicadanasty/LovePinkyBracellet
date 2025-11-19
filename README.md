# LovePinkyBracellet

<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pinky Bracelet - 12 H Kelompok 11</title>
    <!-- Memuat Tailwind CSS untuk styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <!-- Font Awesome untuk ikon keranjang -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">
    <!-- Library untuk generate QR Code secara dinamis -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    
    <style>
        /* Konfigurasi warna pastel khusus */
        :root {
            --pastel-pink: #fbcfe8; /* pink-300 */
            --pastel-purple: #d8b4fe; /* violet-300 */
            --bg-light: #fff7fa; /* Sangat muda, hampir putih */
        }
        
        .bg-primary { background-color: var(--pastel-pink); }
        .bg-secondary { background-color: var(--pastel-purple); }
        .text-primary { color: #db2777; /* Rose 600 */ }
        .text-secondary { color: #7c3aed; /* Violet 600 */ }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-light);
            scroll-behavior: smooth;
        }

        /* Coquette Styling */
        .coquette-border {
            border: 4px solid var(--pastel-pink);
            box-shadow: 0 10px 15px -3px rgba(219, 39, 119, 0.1), 0 4px 6px -2px rgba(219, 39, 119, 0.05);
        }
        .coquette-heading {
            text-shadow: 2px 2px 4px rgba(255, 255, 255, 0.5);
            letter-spacing: 0.1em;
        }
        .coquette-button {
            transition: all 0.3s ease;
            transform: translateY(0);
        }
        .coquette-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.06);
        }
    </style>
</head>
<body class="min-h-screen">

    <!-- Navigasi (Header) -->
    <header class="sticky top-0 z-50 bg-white shadow-lg border-b-2 border-primary/50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-3 flex justify-between items-center">
            <div class="flex flex-col items-start">
                <a href="#home" class="text-3xl font-extrabold text-primary coquette-heading">Pinky Bracelet</a>
                <p class="text-xs text-secondary font-semibold mt-1">12 H • Kelompok 11</p>
                <p class="text-xs text-gray-500">Asty dan Angelica</p>
            </div>
            
            <nav class="hidden md:flex space-x-8">
                <a href="#home" class="text-lg font-medium text-gray-700 hover:text-primary transition">Beranda</a>
                <a href="#about" class="text-lg font-medium text-gray-700 hover:text-primary transition">Tentang Kami</a>
                <a href="#products" class="text-lg font-medium text-gray-700 hover:text-primary transition">Produk</a>
                <a href="#testimonials" class="text-lg font-medium text-gray-700 hover:text-primary transition">Testimoni</a>
            </nav>

            <!-- Ikon Keranjang -->
            <button id="cart-icon" class="relative p-2 bg-primary text-white rounded-full shadow-lg coquette-button" onclick="toggleCartModal(true)">
                <i class="fas fa-shopping-cart text-xl"></i>
                <span id="cart-count" class="absolute -top-1 -right-1 flex items-center justify-center h-5 w-5 bg-red-500 text-white text-xs font-bold rounded-full border-2 border-white">
                    0
                </span>
            </button>
        </div>
    </header>

    <main class="max-w-7xl mx-auto p-4 sm:p-6 lg:p-8">
        
        <!-- Bagian 1: Beranda (Home) -->
        <section id="home" class="h-[60vh] md:h-[70vh] flex items-center justify-center bg-primary rounded-xl coquette-border mb-12" style="background-image: url('https://placehold.co/1200x500/fecaca/8b5cf6?text=%F0%9F%8C%B8+Pinky+Bracelet+Collection+%F0%9F%8C%B8'); background-size: cover; background-position: center;">
            <div class="text-center p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-xl">
                <h1 class="text-4xl sm:text-6xl font-extrabold text-pink-600 coquette-heading mb-4">
                    Selamat Datang, Gadis Manis!
                </h1>
                <p class="text-xl sm:text-2xl text-violet-600 font-medium">
                    Temukan aksesoris yang membuat harimu semakin indah.
                </p>
            </div>
        </section>

        <!-- Bagian 2: Tentang Kami (About Us) -->
        <section id="about" class="py-16">
            <h2 class="text-4xl font-bold text-center text-secondary mb-10 coquette-heading">Tentang Kami</h2>
            <div class="max-w-3xl mx-auto p-6 bg-white rounded-lg coquette-border text-center">
                <p class="text-xl text-gray-700 leading-relaxed">
                    Halo! Kami sebagai Owner dari <span class="text-primary font-semibold">Pinky Bracelet</span> dengan nama Asty dan Angelica. Semoga kalian puas dengan produk kami. Kami hadir untuk menambah keceriaan di setiap penampilanmu!
                </p>
                <!-- Ikon Bunga Coquette -->
                <div class="mt-4 text-4xl text-primary">🌸🎀✨</div>
            </div>
        </section>

        <!-- Bagian 3: Daftar Produk (Products) -->
        <section id="products" class="py-16">
            <h2 class="text-4xl font-bold text-center text-primary mb-10 coquette-heading">Koleksi Manis Kami</h2>
            <div id="product-list" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 gap-8">
                
                <!-- Produk 1: Gelang Warna Warni -->
                <div class="bg-white p-6 rounded-xl shadow-lg coquette-border flex flex-col items-center">
                    <img src="https://media.karousell.com/media/photos/products/2025/6/20/beads_bracelet__gelang_manik___1750427608_2409c04d_progressive.jpg" onerror="this.onerror=null;this.src='https://placehold.co/400x200/fbcfe8/db2777?text=Gelang+Warna+Warni';" alt="Gelang Warna Warni" class="w-full h-48 object-cover rounded-lg mb-4 coquette-border">
                    <h3 class="text-2xl font-semibold text-secondary mb-2">Gelang Warna Warni</h3>
                    <p class="text-lg font-bold text-primary mb-4">Rp. 10.000</p>
                    <p class="text-gray-600 text-center mb-4">Gelang manik-manik penuh warna yang ceria, cocok untuk gaya *vibrant* kamu!</p>
                    <button onclick="addToCart({id: 'p1', name: 'Gelang Warna Warni', price: 10000})" class="coquette-button w-full py-2 bg-primary text-white font-bold rounded-full hover:bg-pink-400">
                        <i class="fas fa-cart-plus mr-2"></i> Tambahkan ke Keranjang
                    </button>
                </div>

                <!-- Produk 2: Gelang Y2K -->
                <div class="bg-white p-6 rounded-xl shadow-lg coquette-border flex flex-col items-center">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRVMsy88qks5m7h7i2SFeY04eMNI4UKThyTmnSKsTOmhw&s" onerror="this.onerror=null;this.src='https://placehold.co/400x200/d8b4fe/7c3aed?text=Gelang+Y2K';" alt="Gelang Y2K" class="w-full h-48 object-cover rounded-lg mb-4 coquette-border">
                    <h3 class="text-2xl font-semibold text-primary mb-2">Gelang Y2K</h3>
                    <p class="text-lg font-bold text-secondary mb-4">Rp. 10.000</p>
                    <p class="text-gray-600 text-center mb-4">Gelang dengan nuansa tahun 2000-an, *cute* dan *nostalgic*!</p>
                    <button onclick="addToCart({id: 'p2', name: 'Gelang Y2K', price: 10000})" class="coquette-button w-full py-2 bg-secondary text-white font-bold rounded-full hover:bg-violet-400">
                        <i class="fas fa-cart-plus mr-2"></i> Tambahkan ke Keranjang
                    </button>
                </div>

            </div>
        </section>

        <!-- Bagian 4: Testimoni Pelanggan (Google Form) -->
        <section id="testimonials" class="py-16">
            <h2 class="text-4xl font-bold text-center text-secondary mb-10 coquette-heading">Bagikan Pengalaman Manismu!</h2>
            
            <!-- Google Form Embed untuk Testimoni -->
            <div class="max-w-4xl mx-auto p-4 bg-white rounded-xl shadow-2xl coquette-border">
                <p class="text-center text-gray-600 mb-6">Kami ingin mendengar pendapat Anda! Silakan isi formulir Google Forms di bawah ini. Testimoni Anda bersifat rahasia dan hanya dapat dilihat oleh Admin.</p>
                
                <div class="w-full">
                    <!-- Iframe Google Form Disesuaikan agar responsif -->
                    <iframe 
                        src="https://docs.google.com/forms/d/e/1FAIpQLSdZ6rSDktlMzbnKnVbIYVejPzbrx0T8ddF--nrHVADEnjb4jg/viewform?embedded=true" 
                        class="w-full rounded-xl coquette-border"
                        height="550" 
                        frameborder="0" 
                        marginheight="0" 
                        marginwidth="0">
                        Memuat...
                    </iframe>
                </div>
                
                <p class="text-xs text-center text-gray-500 mt-4">Data Anda langsung dikumpulkan oleh Admin melalui Google Formulir.</p>
            </div>
            
        </section>

        <!-- Bagian 5: Formulir Pemesanan (Order Form) -->
        <section id="order" class="py-16">
            <h2 class="text-4xl font-bold text-center text-primary mb-10 coquette-heading">Konfirmasi Pemesanan & Pembayaran</h2>
            <div class="max-w-3xl mx-auto p-8 bg-white rounded-xl shadow-2xl coquette-border">
                
                <div id="order-summary-display" class="mb-6 p-4 border-b border-pink-200">
                    <h3 class="text-xl font-semibold text-secondary mb-2">Ringkasan Pesanan Anda</h3>
                    <p class="text-gray-600 italic">Keranjang kosong. Silakan tambahkan produk terlebih dahulu.</p>
                </div>

                <form id="order-form">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                        <div>
                            <label for="order-name" class="block text-gray-700 font-medium mb-1">Nama Lengkap</label>
                            <input type="text" id="order-name" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary focus:border-primary" required>
                        </div>
                        <div>
                            <label for="order-phone" class="block text-gray-700 font-medium mb-1">Nomor Telepon (WhatsApp)</label>
                            <input type="tel" id="order-phone" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary focus:border-primary" required>
                        </div>
                    </div>
                    <div class="mb-6">
                        <label for="order-address" class="block text-gray-700 font-medium mb-1">Alamat Lengkap</label>
                        <textarea id="order-address" rows="3" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary focus:border-primary resize-none" required></textarea>
                    </div>

                    <!-- Opsi Pembayaran -->
                    <div class="bg-primary/20 p-5 rounded-lg mb-6">
                        <h3 class="text-xl font-bold text-primary mb-3">Metode Pembayaran (Transfer DANA)</h3>
                        <p class="text-gray-700 mb-4">Silakan transfer total pembayaran Anda ke salah satu opsi di bawah:</p>
                        
                        <div class="flex flex-col md:flex-row gap-4 items-center mb-4">
                            <!-- Link DANA / Nomor -->
                            <div class="p-4 bg-white rounded-lg shadow w-full md:w-1/2">
                                <p class="font-semibold text-secondary mb-2">Via Link Transfer:</p>
                                <a href="https://link.dana.id/minta?full_url=https://qr.dana.id/v1/281012012023052082211598" target="_blank" class="text-sm text-blue-600 hover:underline break-all">Klik untuk Link DANA</a>
                                <p class="mt-2 text-sm text-gray-700">Atau Nomor: <span class="font-mono font-bold">081211234744</span></p>
                            </div>

                            <!-- QRIS DANA - Generated Barcode -->
                            <div class="p-4 bg-white rounded-lg shadow w-full md:w-1/2 text-center">
                                <p class="font-semibold text-secondary mb-2">Scan QRIS (DANA)</p>
                                <!-- DIV ini akan diisi oleh QR Code yang digenerate JS -->
                                <div id="qrcode" class="mx-auto w-[150px] h-[150px] border-2 border-secondary rounded-lg p-1"></div>
                                <p class="text-xs mt-1 text-gray-500">Scan barcode di atas menggunakan aplikasi DANA/bank kamu.</p>
                            </div>
                        </div>
                    </div>

                    <!-- Tombol Konfirmasi -->
                    <button type="submit" id="confirm-order-button" class="coquette-button w-full py-4 bg-secondary text-white text-xl font-bold rounded-lg hover:bg-violet-600 disabled:bg-gray-400" disabled>
                        Konfirmasi Pesanan via WhatsApp
                    </button>
                    <p class="text-xs text-center text-gray-500 mt-2">Setelah menekan tombol, Anda akan diarahkan ke WhatsApp untuk menyelesaikan konfirmasi.</p>
                </form>
            </div>
        </section>
        
    </main>

    <!-- Footer -->
    <footer class="bg-primary mt-12 py-8 text-center text-white">
        <p class="text-lg">&copy; 2025 Pinky Bracelet. Dibuat dengan cinta oleh Asty & Angelica.</p>
    </footer>

    <!-- Modal Keranjang (Cart Modal) -->
    <div id="cart-modal" class="fixed inset-0 bg-black bg-opacity-50 hidden justify-center items-center z-[100]">
        <div class="bg-white p-6 md:p-8 rounded-xl w-11/12 max-w-lg coquette-border">
            <h3 class="text-2xl font-bold text-primary mb-4 flex justify-between items-center">
                Keranjang Belanjaku <i class="fas fa-shopping-bag text-secondary"></i>
            </h3>
            <div id="cart-items-list" class="space-y-3 max-h-80 overflow-y-auto mb-4 border-b pb-4">
                <!-- Item keranjang akan dimuat di sini -->
            </div>
            <div class="flex justify-between items-center text-xl font-bold text-gray-800 border-t pt-4">
                <span>Total:</span>
                <span id="cart-total-price" class="text-pink-600">Rp. 0</span>
            </div>
            <div class="mt-6 flex flex-col space-y-3">
                <a href="#order" onclick="toggleCartModal(false)" id="checkout-button-link" class="coquette-button text-center py-3 bg-secondary text-white font-bold rounded-lg hover:bg-violet-600">
                    Lanjut ke Pemesanan
                </a>
                <button onclick="toggleCartModal(false)" class="coquette-button py-2 border border-gray-300 text-gray-700 font-medium rounded-lg hover:bg-gray-100">
                    Lanjutkan Belanja
                </button>
            </div>
        </div>
    </div>

    <!-- Modal Pesan (Toast/Feedback Message) -->
    <div id="message-modal" class="fixed top-5 right-5 z-[101] p-4 bg-green-500 text-white rounded-lg shadow-xl transition-transform transform translate-x-full hidden">
        <p id="message-text"></p>
    </div>

    <!-- Script Utama (JavaScript) -->
    <script type="module">
        // Firebase code and imports are removed since testimonials now use Google Forms.

        const cart = JSON.parse(localStorage.getItem('pinky_bracelet_cart')) || [];
        const CART_KEY = 'pinky_bracelet_cart';
        
        // --- UTILITY FUNCTIONS ---

        // Fungsi untuk menampilkan pesan notifikasi/toast
        function showMessage(text, type = 'success') {
            const modal = document.getElementById('message-modal');
            const textEl = document.getElementById('message-text');
            
            modal.classList.remove('bg-green-500', 'bg-red-500', 'hidden');
            if (type === 'success') {
                modal.classList.add('bg-green-500');
            } else {
                modal.classList.add('bg-red-500');
            }
            textEl.textContent = text;
            
            // Tampilkan modal
            modal.classList.remove('translate-x-full');
            
            // Sembunyikan setelah 3 detik
            setTimeout(() => {
                modal.classList.add('translate-x-full');
                setTimeout(() => {
                    modal.classList.add('hidden');
                }, 300); // Tunggu sampai transisi selesai
            }, 3000);
        }

        // Fungsi untuk memformat harga ke format IDR
        function formatPrice(price) {
            return new Intl.NumberFormat('id-ID', {
                style: 'currency',
                currency: 'IDR',
                minimumFractionDigits: 0
            }).format(price);
        }

        // --- QR CODE GENERATION ---
        function generateQRCode() {
            const qrcodeContainer = document.getElementById('qrcode');
            // Pastikan library QRCode sudah dimuat (disediakan oleh CDN di head)
            if (qrcodeContainer && window.QRCode) {
                // Data yang akan dienkripsi dalam QR Code (URL tujuan transfer DANA)
                const qrData = 'https://link.dana.id/minta?full_url=https://qr.dana.id/v1/281012012023052082211598';
                
                // Bersihkan kontainer sebelum membuat QR baru
                qrcodeContainer.innerHTML = ''; 

                // Inisialisasi generator QR Code
                new QRCode(qrcodeContainer, {
                    text: qrData,
                    width: 140, 
                    height: 140,
                    colorDark: "#7c3aed", // Warna Violet 600 (text-secondary)
                    colorLight: "#ffffff",
                    correctLevel: QRCode.CorrectLevel.H // Level koreksi error tinggi
                });
                console.log("QR Code for DANA link generated successfully.");
            } else {
                console.warn('QR Code container atau library (qrcode.min.js) belum siap.');
            }
        }

        // --- CART & ORDER LOGIC ---

        function saveCart() {
            localStorage.setItem(CART_KEY, JSON.stringify(cart));
            updateCartUI();
        }

        window.addToCart = function(product) {
            const existingItem = cart.find(item => item.id === product.id);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({ ...product, quantity: 1 });
            }
            saveCart();
            showMessage(`${product.name} ditambahkan ke keranjang!`, 'success');
        }

        function updateCartUI() {
            const countEl = document.getElementById('cart-count');
            const itemsListEl = document.getElementById('cart-items-list');
            const totalEl = document.getElementById('cart-total-price');
            const checkoutBtn = document.getElementById('confirm-order-button');
            const orderSummaryDisplay = document.getElementById('order-summary-display');

            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            
            countEl.textContent = totalItems;
            totalEl.textContent = formatPrice(totalPrice);
            checkoutBtn.disabled = totalItems === 0;

            // Update Cart Modal
            itemsListEl.innerHTML = '';
            if (cart.length === 0) {
                itemsListEl.innerHTML = '<p class="text-center text-gray-500 italic">Keranjang belanja Anda kosong.</p>';
            } else {
                cart.forEach(item => {
                    const itemEl = document.createElement('div');
                    itemEl.className = 'flex justify-between items-center p-2 bg-primary/10 rounded-lg';
                    itemEl.innerHTML = `
                        <div>
                            <p class="font-semibold text-gray-800">${item.name}</p>
                            <p class="text-sm text-gray-600">${item.quantity} x ${formatPrice(item.price)}</p>
                        </div>
                        <div class="flex items-center space-x-2">
                            <button onclick="changeQuantity('${item.id}', -1)" class="text-red-500 hover:text-red-700 font-bold p-1"><i class="fas fa-minus"></i></button>
                            <span class="font-mono text-lg">${item.quantity}</span>
                            <button onclick="changeQuantity('${item.id}', 1)" class="text-green-500 hover:text-green-700 font-bold p-1"><i class="fas fa-plus"></i></button>
                        </div>
                    `;
                    itemsListEl.appendChild(itemEl);
                });
            }

            // Update Order Summary
            if (totalItems > 0) {
                orderSummaryDisplay.innerHTML = `
                    <h3 class="text-xl font-semibold text-secondary mb-2">Ringkasan Pesanan Anda</h3>
                    <ul class="list-disc list-inside space-y-1 text-gray-700">
                        ${cart.map(item => `<li>${item.quantity}x ${item.name} (${formatPrice(item.price * item.quantity)})</li>`).join('')}
                    </ul>
                    <p class="text-lg font-bold mt-3 text-pink-600">Total Akhir: ${formatPrice(totalPrice)}</p>
                `;
            } else {
                 orderSummaryDisplay.innerHTML = `
                    <h3 class="text-xl font-semibold text-secondary mb-2">Ringkasan Pesanan Anda</h3>
                    <p class="text-gray-600 italic">Keranjang kosong. Silakan tambahkan produk terlebih dahulu.</p>
                `;
            }
        }

        window.changeQuantity = function(id, delta) {
            const itemIndex = cart.findIndex(item => item.id === id);
            if (itemIndex > -1) {
                cart[itemIndex].quantity += delta;
                if (cart[itemIndex].quantity <= 0) {
                    cart.splice(itemIndex, 1); // Hapus jika kuantitas <= 0
                }
                saveCart();
                updateCartUI(); // Update UI keranjang yang mungkin sedang terbuka
            }
        }

        window.toggleCartModal = function(show) {
            const modal = document.getElementById('cart-modal');
            if (show) {
                modal.classList.remove('hidden');
                modal.classList.add('flex');
            } else {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
            }
            updateCartUI(); // Pastikan UI keranjang di-refresh saat dibuka
        }

        document.getElementById('order-form').addEventListener('submit', (e) => {
            e.preventDefault();
            // Nomor WA untuk pemesanan/Order (62...)
            const orderWaUrlNumber = '6281211234744'; 

            if (cart.length === 0) {
                showMessage("Keranjang Anda kosong. Silakan pilih produk terlebih dahulu.", 'error');
                return;
            }

            const name = document.getElementById('order-name').value.trim();
            const address = document.getElementById('order-address').value.trim();
            const phone = document.getElementById('order-phone').value.trim();
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);

            // Buat ringkasan pesanan untuk WhatsApp
            let message = `*Konfirmasi Pesanan Pinky Bracelet*\n\n`;
            message += `*Nama:* ${name}\n`;
            message += `*No. HP:* ${phone}\n`;
            message += `*Alamat:* ${address}\n\n`;
            message += `*Detail Pesanan:*\n`;
            cart.forEach(item => {
                message += `- ${item.quantity}x ${item.name} (${formatPrice(item.price * item.quantity)})\n`;
            });
            message += `\n*TOTAL PEMBAYARAN:* ${formatPrice(totalPrice)}\n\n`;
            message += `*Metode Pembayaran: Transfer DANA/QRIS*\n`;
            message += `(Lampirkan bukti transfer di chat ini, ya!)\n\n`;
            message += `Terima kasih! Kami akan segera memproses pesanan Anda. ✨`;

            const whatsappUrl = `https://wa.me/${orderWaUrlNumber}?text=${encodeURIComponent(message)}`;
            
            // Bersihkan keranjang setelah konfirmasi (asumsi user akan melanjutkan ke WA)
            cart.length = 0;
            saveCart();
            document.getElementById('order-form').reset();
            
            showMessage("Pesanan dikonfirmasi! Anda akan diarahkan ke WhatsApp.", 'success');
            
            // Arahkan ke WhatsApp
            window.open(whatsappUrl, '_blank');
        });

        // --- INITIALIZATION ---
        
        window.onload = function() {
            // Firebase init removed
            updateCartUI();
            generateQRCode(); // Panggil fungsi generate QR Code saat halaman dimuat
        };

    </script>
</body>
</html>
