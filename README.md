# Skripsi
# Panduan Instalasi dan Penggunaan Program

# 1. Scraping Data Menggunakan YouTube API v3

Deskripsi:
Langkah pertama adalah melakukan scraping data dari YouTube menggunakan YouTube API v3. Untuk melakukannya, Anda memerlukan API key.
Cara Mendapatkan API Key YouTube API v3:
Buka Google Cloud Console.
Login dengan akun Google Anda.
Buat proyek baru atau pilih proyek yang ada.
Aktifkan YouTube Data API v3 dari menu API & Services > Enable APIs and Services.
Pergi ke Credentials, buat kredensial baru, pilih API key.
Salin API key tersebut, karena akan digunakan dalam kode scraping.

# 2. Proses Pemrosesan Dataset

Deskripsi:
Dataset yang diperoleh dari scraping perlu diolah menjadi format conversation untuk mendukung fine-tuning model Llama 2.
Langkah-langkah Pemrosesan Dataset:
Bersihkan data mentah hasil scraping agar hanya berisi informasi relevan seperti teks komentar atau judul video.

# 3. Fine-Tuning Model Llama 2

Deskripsi:
Proses fine-tuning menggunakan model Llama 2 untuk menerjemahkan bahasa gaul.
Syarat dan Ketentuan Model Llama 2:
Dapatkan lisensi dari Meta AI melalui halaman resmi Meta AI.
Setelah mendapatkan lisensi, unduh model Llama 2 dari:
Hugging Face Repository.
GitHub Repository Resmi Llama 2.
Proses Fine-Tuning:
Gunakan framework seperti Hugging Face Transformers atau PEFT (Parameter-Efficient Fine-Tuning).
Konfigurasikan parameter pelatihan seperti berikut:
LoRA (Low-Rank Adaptation) atau QLoRA (Quantized LoRA) untuk efisiensi.
BitsandBytes untuk penghematan memori.
Argumen pelatihan seperti learning_rate, num_train_epochs, dan per_device_train_batch_size.
Pastikan Anda menggunakan dataset yang sudah diformat untuk fine-tuning.
Rekomendasi Platform dan GPU:
Gunakan Google Colab (gratis) dengan GPU T4 untuk proses fine-tuning.
Estimasi resource:
Memori GPU: 5.7GB.
Durasi Pelatihan: ~40 menit (tergantung ukuran dataset dan parameter).

setelah finetuning selesai, anda dapat menyimpan model pada akun huggingface anda untuk memudahkan integrasi chatbot selanjutnya
atau jika anda menjalankan dilokal anda dapat mengunduh modelnya

# 4. Chatbot Menggunakan Streamlit

Deskripsi:
Setelah fine-tuning selesai, chatbot dikembangkan menggunakan Streamlit. Chatbot ini diakses melalui ngrok.
Langkah Menjalankan Chatbot:
1. Login akun huggingface anda, dan insert token anda yang anda buat di huggingface
2. Jalankan Cell Chatbot, akan muncul write app.py
3. setelah muncul jalankan cell berikutnya untuk menjalankan chatbot menggunakan ngrok
4. lalu akan muncul sebuah link, anda klik saja, dan chatbot berhasil jalan. biasanya akan memakan waktu lama dikarenakan chatbot akan mengunduh model terlebih dahulu
