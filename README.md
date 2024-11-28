# Exercise 5: Demonstrating Resource Contention in Multitasking Systems
Latihan ini bertujuan untuk memahami bagaimana sistem operasi real-time (RTOS) menangani multitasking dengan kebijakan penjadwalan preemptive priority. Pada bagian ini akan mengamati bagaimana tugas-tugas dengan prioritas berbeda memengaruhi urutan eksekusi dalam sistem berbasis STM32 dan FreeRTOS.
## Tujuan
1. Menunjukkan bagaimana kontensi akses terhadap sumber daya bersama dapat terjadi dalam sistem multitasking.
2. Mengidentifikasi dampak negatif dari tidak adanya mekanisme perlindungan sumber daya.
3. Memberikan pemahaman tentang pentingnya penggunaan mekanisme pengelolaan sumber daya, seperti semaphore atau mutex.

## Peralatan

1. STM32F103C8T
2. LED
3. Kabel Jummper
4. Mini debugger
## Langkah Implementasi

1. Buat proyek baru di STM32CubeIDE atau gunakan template yang disediakan.
2. Aktifkan fitur FreeRTOS melalui STM32CubeMX dengan konfigurasi yang sesuai.
2. Tambahkan dua tugas yang akan bersaing untuk menggunakan sumber daya bersama, seperti UART atau GPIO.
3. Tulis dua tugas (Task1 dan Task2) dalam file main.c.
4. Pastikan kedua tugas mencoba mengakses sumber daya bersama tanpa mekanisme pengelolaan seperti semaphore.
5. Gunakan fungsi osDelay() untuk membuat jeda eksekusi dan mempermudah observasi kontensi.
6. Flash kode ke STM32 Discovery Board.
7. Jalankan program dan perhatikan perilaku tugas melalui LED, UART output, atau alat debugging.


## Hasil yang Diharapkan
##### Tanpa Proteksi Sumber Daya

1. Tugas-tugas mungkin saling tumpang tindih dalam mengakses sumber daya bersama.
2. Muncul konflik akses, seperti data yang tumpang tindih pada UART atau LED yang menyala tidak sesuai.
##### Dengan Proteksi Sumber Daya (Semaphore)

1. Setelah menambahkan semaphore sebagai mekanisme pengelolaan, tugas-tugas dapat mengakses sumber daya secara bergantian.
2. Konflik dapat dihindari, dan sistem berfungsi dengan lebih stabil dan terprediksi. 

## Hasil Percobaan
https://github.com/user-attachments/assets/7df16fdc-1b41-4115-89fe-73f027f4890c
