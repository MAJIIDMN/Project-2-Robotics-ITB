# Deteksi & Pelacakan Objek dengan YOLOv8

Proyek ini mendemonstrasikan cara mendeteksi serta melacak objek pada video menggunakan model YOLOv8 dari pustaka **ultralytics**. Skrip utama (`TUGAS_2.py`) memuat video `object_video_manual.mp4`, menjalankan pelacakan objek, dan menampilkan hasilnya dengan kotak dan label kepercayaan.

## Prasyarat
- Python 3.10 atau lebih baru.
- Paket Python: `ultralytics`, `opencv-python`, dan `math` (termasuk di pustaka standar).
- Berkas model YOLOv8 ringan di jalur `yolo-Weights/yolov8n.pt`. Unduh dari repositori resmi Ultralytics jika belum tersedia.
- Video uji: `object_video_manual.mp4` (sudah disertakan di repo).

## Cara Menjalankan
1. Buat dan aktifkan lingkungan virtual (opsional tetapi disarankan):
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```
2. Pasang dependensi yang diperlukan:
   ```bash
   pip install ultralytics opencv-python
   ```
3. Pastikan berkas bobot model berada di `yolo-Weights/yolov8n.pt`. Jika belum ada, unduh model YOLOv8n dari Ultralytics dan simpan pada jalur tersebut.
4. Jalankan skrip pelacakan:
   ```bash
   python TUGAS_2.py
   ```
5. Tekan `q` di jendela tampilan untuk menghentikan proses lebih cepat; jika tidak, pemutaran akan berhenti ketika video selesai.

## Penjelasan Singkat Skrip
- **Memuat video:** `cv2.VideoCapture('object_video_manual.mp4')`.
- **Memuat model:** `YOLO("yolo-Weights/yolov8n.pt")`.
- **Pelacakan streaming:** `model.track(imS, stream=True)` membaca setiap frame, memberi bounding box, nama kelas, dan skor kepercayaan di atas ambang 0,4.
- **Visualisasi:** Kotak dan label ditampilkan pada jendela OpenCV bertajuk `Object_Track`.

## Output Video Contoh
Rekaman layar hasil deteksi dapat diakses pada tautan berikut:
- https://drive.google.com/file/d/1aiWzxclsFEdwdbRNfbvnIqNYzID9TVhp/view?usp=sharing

## Lisensi
Proyek ini bersifat akademik/tugas. Silakan sesuaikan atau perluas sesuai kebutuhan Anda.
