# CNNBusTruck
Klasifikasi Truck 🚚 dan Bus 🚌 Repo ini berisi proyek CNN dengan TensorFlow untuk klasifikasi gambar truk dan bus. Model dilatih dengan dataset gambar, dijalankan di Google Colab, dan terintegrasi dengan Gradio untuk antarmuka interaktif dalam menguji model.

#Fitur Utama

    Dataset:
        Dataset disimpan di Google Drive dengan struktur direktori terpisah untuk data latih (train), validasi (validation), dan uji (test).
        Gambar dalam format .jpg atau .png diolah menggunakan ImageDataGenerator dari TensorFlow untuk normalisasi (rescaling ke rentang 0-1) dan augmentasi data sederhana.
        Data diatur untuk klasifikasi biner (truk 🚚 vs. bus 🚌) dengan ukuran gambar 150x150 piksel.
    Model CNN:
        Model dibangun menggunakan arsitektur Sequential dari TensorFlow Keras dengan lapisan berikut:
            Tiga lapisan konvolusi (Conv2D) dengan jumlah filter bertambah (32, 64, 128) dan aktivasi ReLU.
            Lapisan MaxPooling2D untuk mengurangi dimensi spasial.
            Lapisan Flatten untuk mengubah data menjadi vektor.
            Lapisan Dense dengan 512 unit dan aktivasi ReLU, diikuti oleh Dropout (0.5) untuk mencegah overfitting.
            Lapisan output dengan 1 unit dan aktivasi sigmoid untuk klasifikasi biner (truk 🚚 atau bus 🚌).
        Model dikompilasi dengan optimizer Adam, fungsi kerugian binary_crossentropy, dan metrik akurasi.
    Pelatihan:
        Model dilatih selama 10 epoch (dapat disesuaikan) menggunakan generator data untuk efisiensi memori.
        Jumlah langkah per epoch dan validasi dihitung berdasarkan ukuran dataset dan batch size (32).
        Riwayat pelatihan (akurasi dan loss) dicetak untuk analisis performa.
    Antarmuka Pengguna:
        Menggunakan Gradio untuk membuat antarmuka interaktif yang memungkinkan pengguna mengunggah gambar kendaraan (bus 🚌 atau truk 🚚) dan mendapatkan prediksi kelas.
        Fungsi classify_image mengubah gambar input menjadi format yang sesuai (resize ke 150x150, normalisasi), lalu memprediksi kelas menggunakan model yang telah dilatih.
    Fungsionalitas Tambahan:
        Kode menyertakan fungsi count_images untuk menghitung jumlah gambar di setiap direktori dataset, membantu memverifikasi ukuran data.
        Pemeriksaan ketersediaan GPU untuk mempercepat pelatihan.

#Tujuan

Proyek ini bertujuan untuk:

    Membangun model deep learning untuk klasifikasi biner gambar kendaraan (truk 🚚 dan bus 🚌).
    Menyediakan antarmuka yang mudah digunakan untuk menguji model secara real-time.
    Memanfaatkan Google Colab dan Google Drive untuk pengelolaan data dan pelatihan yang efisien.

#Teknologi yang Digunakan

    Bahasa Pemrograman: Python
    Library:
        TensorFlow/Keras untuk pembangunan dan pelatihan model CNN.
        Gradio untuk antarmuka pengguna.
        PIL untuk pengolahan gambar.
        NumPy untuk manipulasi array.
    Platform: Google Colab (dengan dukungan GPU opsional).

#Cara Menjalankan
    Download Dataset:https://tinyurl.com/VehicleDatasett, lalu simpan pada google drive dengan nama vehicle_datasett
    Copy Paste seluruh code pada file BusTruck.ipynb pada Notebook baru google collab
    Hubungkan Google Colab dengan Google Drive untuk mengakses dataset.
    Instal dependensi seperti Gradio.
    Jalankan kode untuk melatih model dan meluncurkan antarmuka Gradio.
    Unggah gambar melalui antarmuka Gradio untuk mengklasifikasikan kendaraan (truk 🚚 atau bus 🚌).

Catatan

    Dataset harus diatur dalam struktur direktori yang sesuai (train, validation, test) dengan subfolder untuk masing-masing kelas (truk 🚚 dan bus 🚌).
    Model dapat ditingkatkan dengan augmentasi data tambahan, penyesuaian arsitektur, atau peningkatan jumlah epoch untuk akurasi yang lebih baik.
