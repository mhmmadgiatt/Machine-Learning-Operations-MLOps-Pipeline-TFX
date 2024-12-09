# Submission 2: Machine Learning Operations (MLOps) Hate Speech Detection  
Nama: Muhammad Giat

Username Dicoding: mhmmadgiatt

| | Deskripsi |  
| ----------- | ----------- |  
| **Dataset** | Dataset yang digunakan dalam proyek ini adalah [Hate Speech Detection Dataset](https://www.kaggle.com/datasets/aditya1220/hate-speech-detection-dataset/data). Dataset ini memiliki struktur yang terdiri dari direktori gambar berlabel, serta tiga file CSV: `Training_meme_dataset.csv`, `Testing_meme_dataset.csv`, dan `Validation_meme_dataset.csv`. Setiap file CSV berisi metadata terkait gambar, termasuk kolom `image_name` yang menjadi identifier unik untuk setiap gambar, `sentence` yang berisi teks pada gambar, dan `label` yang mengkategorikan gambar ke dalam kelas `offensive` atau `non-offensive`. Dataset ini bertujuan untuk melatih dan mengevaluasi model machine learning dalam mendeteksi berbagai bentuk ujaran kebencian pada unggahan media sosial. |  
| **Masalah** | Permasalahan yang diangkat dalam proyek ini adalah semakin maraknya ujaran kebencian yang tersebar melalui media sosial. Ujaran kebencian dapat berdampak buruk baik secara psikologis maupun sosial, termasuk menyebabkan trauma emosional, meningkatkan diskriminasi, dan memperburuk polarisasi masyarakat. Untuk mencegah dampak negatif ini, diperlukan sistem yang mampu mendeteksi ujaran kebencian secara otomatis dan akurat. |  
| **Solusi Machine Learning** | Solusi yang ditawarkan adalah membangun model deep learning berbasis Convolutional Neural Networks (CNN) yang mampu menganalisis gambar dan teks untuk mendeteksi ujaran kebencian. Model ini dirancang untuk mengidentifikasi dan mengklasifikasikan unggahan media sosial ke dalam kategori `offensive` atau `non-offensive`, sehingga dapat digunakan untuk membantu platform media sosial dalam mengelola konten mereka. |  
| **Metode Pengolahan** | Data diproses melalui beberapa langkah penting. Label pada data dikodekan, di mana `offensive` diberikan nilai 1 dan `non-offensive` diberikan nilai 0. Oversampling dilakukan pada data minoritas untuk menyeimbangkan distribusi kelas. Selain itu, teks pada metadata gambar diubah menjadi huruf kecil dan tanda baca dihapus untuk menyederhanakan analisis. |  
| **Arsitektur Model** | Model yang digunakan terdiri dari beberapa lapisan utama, yaitu lapisan input untuk menerima data, lapisan *TextVectorisation* untuk mengubah teks menjadi nilai numerik, lapisan *Embedding* untuk membuat urutan fitur, lapisan *GlobalAveragePooling* untuk mengurangi dimensi fitur, lapisan *Dense* untuk memproses fitur, dan lapisan output untuk menghasilkan klasifikasi akhir, yaitu `offensive` atau `non-offensive`. |  
| **Metrik Evaluasi** | Evaluasi model dilakukan dengan menggunakan metrik *Area Under Curve (AUC)* untuk mengukur luas area di bawah kurva ROC. Selain itu, digunakan metrik *Binary Accuracy* untuk menghitung proporsi prediksi yang benar, serta matriks kebingungan (confusion matrix) untuk mengevaluasi hasil klasifikasi, termasuk nilai True Positive, True Negative, False Positive, dan False Negative. |  
| **Performa Model** | Model yang telah dilatih menunjukkan hasil *binary accuracy* sebesar 99,81% pada data pelatihan (*training accuracy*), namun performa pada data validasi (*validation accuracy*) tidak sebaik data pelatihan, dengan nilai tertinggi sebesar 59,16%. Hal ini terlihat pula dari meningkatnya *validation loss*, yang mencapai 2,6621 pada akhir pelatihan. Perbedaan signifikan antara performa pelatihan dan validasi ini mengindikasikan terjadinya *overfitting*. Untuk meningkatkan performa pada data validasi, diperlukan penyesuaian pada parameter model atau strategi regularisasi seperti penambahan lapisan dropout, augmentasi data, atau pengurangan kompleksitas model. |  
| **Opsi Deployment** | Proses deployment dilakukan menggunakan platform Railway. Railway memudahkan pengembang untuk menyebarkan aplikasi atau model machine learning ke lingkungan produksi dengan pengaturan yang sederhana dan efisien. |  
| **Web App** | Model yang telah dilatih dapat diakses melalui tautan berikut: [Hate-Speech-Model](https://example.railway.app/v1/models/hate-speech-detection) (model saat ini tidak aktif karena keterbatasan sumber daya). |  
| **Monitoring** | Monitoring model dilakukan untuk memastikan performa dan stabilitasnya di lingkungan produksi. Dengan menggunakan alat seperti Prometheus, metrik seperti jumlah permintaan dan waktu respons model dapat diamati secara real-time, membantu dalam deteksi dini terhadap potensi masalah operasional. |  
