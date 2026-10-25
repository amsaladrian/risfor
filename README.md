# risfor
# Edge AI-Based Industrial Sorting System 🍎🍊

Sistem automasi penyortiran industri berasaskan Edge AI yang direka untuk mengklasifikasikan buah (epal dan oren) secara *real-time* di atas laluan konveyor. Sistem ini memanfaatkan kuasa YOLOv8 yang dijalankan pada Raspberry Pi 5, dipercepatkan oleh NPU Hailo-8L, dan diintegrasikan dengan PLC Omron melalui pin GPIO.

## 🚀 Ciri-Ciri Utama
- **Pemecutan NPU Hailo-8L:** Menggunakan model YOLOv8 yang dikuantisasi (format INT8) untuk mengalihkan beban komputasi daripada CPU.
- **Asynchronous Dual-Queue:** Algoritma *multi-threading* khusus untuk memastikan penyegerakan persepsi visual dan tindakan mekanikal tanpa kehilangan data (low latency).
- **Prestasi Tinggi:** Kelajuan inferens mencapai 30-45 FPS dengan latensi purata ~22 ms.
- **Ketepatan Penyortiran:** Kadar kejayaan fizikal 96.0% untuk epal dan 98.0% untuk oren.

## 🛠️ Keperluan Perkakasan & Perisian
- **Perkakasan:** Raspberry Pi 5 (8GB RAM), Modul Pecutan AI Hailo-8L M.2, Modul Relay Opto-isolated, Penderia Proximity IR, PLC Omron, Aktuator Penyortir.
- **Perisian:** OS Linux (Raspbian), Python 3, OpenCV, Ultralytics YOLOv8, HailoRT API.

## 📂 Struktur Repositori
- `/dataset` - Sampel imej latihan (epal dan oren).
- `/models` - Fail model YOLOv8 terkuantisasi (`.hef` / Hailo Executable Format).
- `/src` - Skrip utama Python untuk inferens *multi-threading* dan kawalan GPIO.

## 📊 Keputusan Ujian
Sistem berjaya mengurangkan beban CPU daripada 95% (CPU Only) kepada 15%-25%, mengelakkan amaran kelambatan terma (*thermal throttling*), dan mengekalkan peruntukan memori yang selamat tanpa *memory leak* sepanjang proses penyortiran berterusan.
