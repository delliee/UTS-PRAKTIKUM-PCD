# UTS Praktikum PCD C

## Analisis Citra:
![Analisis Citra](https://github.com/delliee/UTS-Praktikum-PCD/assets/156888006/0b15d10a-bcfc-428f-9d27-19182fa50f10)

Pada citra "pcd.jpg" setiap saluran warna yang diekstraksi (r, g, b) ditampilkan dalam skala abu-abu (cmap="gray"). Ini membuat setiap saluran warna tampak sebagai citra grayscale yang menggambarkan tingkat kecerahan setiap saluran warna pada gambar asli.
Pada gambar asli (color_image), dapat dilihat bagaimana kombinasi saluran warna ini memberikan warna yang berbeda pada gambar.

- Setiap piksel pada citra warna mewakili warna yang merupakan kombinasi dari ketiga warna dasar RGB. 
- Setiap titik pada citra warna membutuhkan data sebesar 3 byte. 
- Setiap warna dasar memiliki intensitas tersendiri dengan nilai minimum nol (0) dan nilai maksimum 255 (8 bit). 
- RGB didasarkan pada teori bahwa mata manusia peka terhadap panjang gelombang 630nm (merah), 530 nm (hijau), dan 450 nm (biru).
- Analisis citra bertujuan menghitung besaran kuantitatif dari citra untuk menghasilkan deskripsinya. Proses segmentasi kadang kala diperlukan untuk melokalisasi objek yang diinginkan dari sekelilingnya. Seperti pendeteksian tepi (edge detection), ekstraksi batas (boundary) dan representasi daerah (region).

Proses analisis citra yang dilakukan:
- Membaca dan Menampilkan Citra
    - Citra yang disimpan dalam file "pcd.jpg" dibaca menggunakan fungsi "imread" dan ditampilkan menggunakan fungsi "imshow"
- Memisahkan Saluran Warna (Separating Color Channels)
    - Citra yang dibaca kemudian dikonversi ke bentuk Numpy dengan syntax "color_image[:. :, 2]" dan hasilnya adalah tiga variabel berisi warna merah, hijau, dan biru dari citra asli.
- Menampilkan Gambar dan Saluran Warna
    - Melakukkan plotting menggunakan "plt.subplots" untuk menampilkan gambar asli dan tiga saluran warna.

Konversi skala abu-abu membantu memvisualisasikan setiap saluran satu per satu, karena gambar berwarna menggabungkan saluran-saluran ini untuk menghasilkan visual akhir.

- Merah: Suatu pixel dapat dianggap merah jika nilai intensitas merahnya jauh lebih tinggi daripada nilai intensitas hijau dan birunya.  Dengan kata lain, angka pada kolom pertama harus jauh lebih besar daripada angka di kolom kedua dan ketiga.

- Hijau: Demikian pula, untuk pixel yang dianggap hijau, nilai intensitas hijaunya harus jauh lebih tinggi daripada nilai merah dan birunya. Ini berarti angka pada kolom kedua harus jauh lebih besar daripada angka di kolom pertama dan ketiga.

- Biru: Untuk pixel yang dianggap biru, nilai intensitas birunya harus jauh lebih tinggi daripada nilai merah dan hijaunya. Ini menunjukkan bahwa angka pada kolom ketiga harus jauh lebih besar daripada angka di kolom pertama dan kedua.

- [49]: (-0.5, 1279.5, 910.5, -0.5)

Pada gambar, nilai intensitas merah adalah 1279.5, sedangkan nilai intensitas hijau dan biru berturut-turut adalah 910.5 dan -0.5. Berdasarkan kriteria di atas, pixel ini bisa dianggap merah karena nilai intensitas merahnya jauh lebih tinggi daripada nilai intensitas hijau dan birunya.

Nilai ambang batas tertentu untuk menentukan apakah suatu pixel merah, hijau, atau biru tergantung pada keseluruhan rentang intensitas citra dan tingkat sensitivitas yang diinginkan. Namun, secara umum, pixel bisa dianggap merah jika nilai intensitas merahnya minimal dua kali lebih besar daripada nilai intensitas hijau dan birunya, begitupula untuk penjelasan hijau dan biru.

## Analisis Histogram:
![Analisis Histogram](https://github.com/delliee/UTS-Praktikum-PCD/assets/156888006/26596729-236c-4c82-93cf-dcae2e41ecd9)

- Grafik Batang Biru

    Grafik batang biru menunjukkan jumlah data yang dikelompokkan berdasarkan rentang nilai tertentu. Sumbu Y menunjukkan jumlah data, sedangkan sumbu X menunjukkan rentang nilai. Sumbu X dibagi menjadi enam segmen, masing-masing mewakili rentang nilai 50 unit.

    Nilai maksimum data pada grafik batang biru adalah 60.000, yang berarti terdapat 60.000 data yang nilainya berada di antara 200 dan 250. Nilai minimum data pada grafik batang biru adalah 0, yang berarti terdapat 0 data yang nilainya kurang dari 50.

- Grafik Batang Hijau

    Grafik batang hijau menunjukkan jumlah data yang dikelompokkan berdasarkan rentang nilai tertentu. Sumbu Y menunjukkan jumlah data, sedangkan sumbu X menunjukkan rentang nilai. Sumbu X dibagi menjadi enam segmen, masing-masing mewakili rentang nilai 50 unit.

    Nilai maksimum data pada grafik batang hijau adalah 70.000, yang berarti terdapat 70.000 data yang nilainya berada di antara 200 dan 250. Nilai minimum data pada grafik batang hijau adalah 0, yang berarti terdapat 0 data yang nilainya kurang dari 50.

- Grafik Batang Merah

    Grafik batang merah menunjukkan jumlah data yang dikelompokkan berdasarkan rentang nilai tertentu. Sumbu Y menunjukkan jumlah data, sedangkan sumbu X menunjukkan rentang nilai. Sumbu X dibagi menjadi enam segmen, masing-masing mewakili rentang nilai 50 unit.

    Nilai maksimum data pada grafik batang merah adalah 60.000, yang berarti terdapat 60.000 data yang nilainya berada di antara 200 dan 250. Nilai minimum data pada grafik batang merah adalah 0, yang berarti terdapat 0 data yang nilainya kurang dari 50.

- Grafik Batang Warna

    Grafik batang warna menunjukkan jumlah data yang dikelompokkan berdasarkan rentang nilai tertentu. Sumbu Y menunjukkan jumlah data, sedangkan sumbu X menunjukkan rentang nilai. Sumbu X dibagi menjadi enam segmen, masing-masing mewakili rentang nilai 50 unit.

    Nilai maksimum data pada grafik batang warna adalah 20.000, yang berarti terdapat 20.000 data yang nilainya berada di antara 150 dan 200. Nilai minimum data pada grafik batang warna adalah 0, yang berarti terdapat 0 data yang nilainya kurang dari 50.

-  Manfaat histogram citra :
    1. Berguna untuk mengamati penyebaran intensitas warna dan dapat dipakai untuk pengambilan keputusan, misalnya dalam peningkatan kecerahan atau peregangan kontras serta sebaran warna.
    2. Berguna untuk penentuan batas-batas dalam pemisahan objek dari latar belakangnya.
    3. Memberikan persentase komposisi warna dan tekstur intensitas untuk kepentingan identifikasi citra.


## Nilai Ambang Batas:
![Nilai Ambang Batas](https://github.com/delliee/UTS-Praktikum-PCD/assets/156888006/cd84cd3d-7166-4dda-9ac2-7ba9deda3644)
Untuk mengetahui nilai ambang batas, dapat emnggunakan fungsi 'cv2.inRange'. Fungsi ini bergantung pada niali ambang batas yang ditetapkan untuk Hue, Saturation dan Value atau HSV.

- Nilai ambang batas terdiri dari dua array, yaitu lower_bound (batas bawah) dan upper_bound (batas atas).
- Kedua array ini memiliki tiga nilai yang sesuai dengan ruang warna HSV (Hue, Saturation, Value).
    Hue (Rona Warna): Mewakili warna itu sendiri (misalnya merah, hijau, biru).
    Saturation (Saturasi): Menunjukkan kemurnian warna (semakin tinggi nilai, warna semakin jenuh).
    Value (Nilai): Menunjukkan kecerahan warna (semakin tinggi nilai, warna semakin terang).
- Pixel dalam gambar akan dianggap memiliki warna yang diinginkan jika nilai pada ketiga kanal (Hue, Saturation, Value) berada di antara lower_bound dan upper_bound.

    1. Bar Chart Biru:

- Pada bar chart biru, nilai ambang batas tidak terlihat secara eksplisit. Namun, kita dapat menduga nilainya berdasarkan warna biru yang ditampilkan. Warna biru umumnya memiliki Hue antara 100 dan 140, Saturation antara 50 dan 255, dan Value antara 50 dan 255.

    2. Bar Chart Hijau:

- Pada bar chart hijau, nilai ambang batas tidak terlihat secara eksplisit. Warna hijau umumnya memiliki Hue antara 40 dan 80, Saturation antara 50 dan 255, dan Value antara 50 dan 255.

    3. Bar Chart Merah:

- Pada bar chart merah, nilai ambang batas tidak terlihat secara eksplisit. Warna merah umumnya memiliki Hue antara 0 dan 10 atau antara 170 dan 180, Saturation antara 50 dan 255, dan Value antara 50 dan 255.

    4. Bar Chart Kombinasi:

- Pada bar chart kombinasi, nilai ambang batas tidak terlihat secara eksplisit. Warna yang ditampilkan merupakan hasil kombinasi dari deteksi warna biru, hijau, dan merah.

## Tahapan Project Citra Digital

### 1. Import Library

#### Sourcecode:

1.       import cv2
         import numpy as np
         from matplotlib import pyplot as plt
Penjelasan: 
- import cv2: OpenCV (Open Source Computer Vision Library), berfungsi untuk pengolahan gambar dan video
- import numpy as np: Library untuk bekerja dengan array
- from matplotlib import pyplot as plt: Library plotting yang menyediakan banyak fungsi untuk membuat plot, grafik, dan chart.

2.      import cv2
        import numpy as np
        import matplotlib.pyplot as plt
        import matplotlib.image as img

        %matplotlib inline
Penjelasan:
- import matplotlib.image as img: Library plotting untuk gambar
- %matplotlib inline: Untuk menampilkan plot Matplotlib langsung di dalam notebook Jupyter.

### 2. Membaca, Menampilkan Gambar Asli dan Membuat Plot 

#### Sourcecode:

3.      color_image = img.imread('pcd.jpg')
        plt.imshow(color_image)
Penjelasan:
- color_image = img.imread('pcd.jpg'): Membaca gambar dari file "pcd.jpg" dan array disimpan dalam variabel color_image.
- plt.imshow(color_image): Menampilkan gambar yang disimpan dalam variabel color_image

4.       r = color_image[:, :, 0] 
         g = color_image[:, :, 1] 
         b = color_image[:, :, 2]
        
         f, (c1, c2, c3, c4) = plt.subplots(1,4,figsize = (20,10))
        
         c1.set_title('Gambar Asli')
         c1.imshow(color_image) 
         c1.axis('off')
         
         c2.set_title('Merah') 
         c2.imshow(r, cmap="gray") 
         c2.axis('off')
         
         c3.set_title('Hijau') 
         c3.imshow(g, cmap="gray") 
         c3.axis('off')
         
         c4.set_title('Biru') 
         c4.imshow(b, cmap="gray")
         c4.axis('off')
Penjelasan:
- Tiga pernyataan awal yang memisahkan gambar berwarna menjadi komponen warna individual: merah (red - r), hijau (green - g), dan biru (blue - b).
- Membuat plot yang terdiri dari empat sub-plot.
- Subplot pertama menampilkan gambar asli, sedangkan tiga subplot lainnya menampilkan masing-masing komponen warna (merah, hijau, biru) dalam skala abu-abu

### 3. Membuat Histogram

#### Sourcecode:

5.        color_image = cv2.imread('pcd.jpg')
Penjelasan:
- Memuat gambar berwarna dari file "pcd.jpg" ke dalam program

6.        color_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB)
Penjelasan:
- Mengubah representasi warna citra dari format BGR (Biru, Hijau, Merah) ke RGB (Merah, Hijau, Biru) menggunakan fungsi "cv2.cvtColor"

7.        histogram_biru  = cv2.calcHist([b], [0], None, [256], [0, 256])
          histogram_hijau = cv2.calcHist([g],[0], None,[256],[0,256])
          histogram_merah = cv2.calcHist([r], [0], None,[256],[0,256])
          histogram_warna = cv2.calcHist([color_image], [0,1,2],None, [256, 256, 256], [0, 256, 0, 256, 0, 256])
Penjelasan:
- cv2.calcHist: Fungsi untuk menghitung histogram.
- [b]: Kanal biru yang dipisahkan sebelumnya.
- [g]: Kanal hijau yang dipisahkan sebelumnya.
- [r]: Kanal merah yang dipisahkan sebelumnya.
- [color_image]: Seluruh citra berwarna.
- [0]: Hitung histogram hanya untuk kanal biru/hijau/merah (indeks 0).
- [0, 1, 2]: Hitung histogram untuk ketiga kanal (biru, hijau, merah).
- None: Tidak ada mask yang digunakan.
- [256]: 256 bin (tempat penampungan) untuk histogram.
- [256, 256, 256]: 256 bin untuk tiap kanal.
- [0, 256]: Rentang intensitas 0-255.
- [0, 256, 0, 256, 0, 256]: Rentang intensitas 0-255 untuk tiap kanal.


8.        plt.figure(figsize=(20, 5))

          plt.subplot(141)
          plt.title('Histogram Asli')
          plt.hist(color_image.flatten(), bins=256, range=[0,256], color='gray')
          
          plt.subplot(142)
          plt.title('Histogram merah')
          plt.hist(r.flatten(), bins=256, range=[0,256,color='r')
          
          plt.subplot(143)
          plt.title('Histogram hijau')
          plt.hist(g.flatten(), bins=256, range=[0,256,color='g')
          
          plt.subplot(144)
          plt.title('Histogram hijau')
          plt.hist(b.flatten(), bins=256, range=[0,256,color='b')
          
          plt.show()
Penjelasan:
- plt.figure(figsize=(20, 5)): Membuat figure baru yang akan digunakan untuk menampilkan plot.
- Subplot pertama menampilkan histogram keseluruhan gambar (abu-abu), sedangkan tiga subplot lainnya menampilkan histogram untuk masing-masing komponen warna merah, hijau, dan biru.
- plt.show(): Menampilkan plot yang telah dibuat

### 4. Menampilkan Nilai Ambang Batas

#### Sourcecode:

9.         import cv2
           import numpy as np
           from matplotlib import pyplot as plt
           
           def make_image_invisible(image):
           height, width = image.shape[:2]
           return np.zeros((height, width, 3), dtype=np.uint8)
           
           def increase_brightness(image, value=30):
           hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
           h, s, v = cv2.split(hsv)
           v += value
           v = np.clip(v, 0, 255)
           final_hsv = cv2.merge((h, s, v))
           return cv2.cvtColor(final_hsv, cv2.COLOR_HSV2BGR)
           
           def detect_and_highlight_blue(image):
           hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
           lower_blue = np.array([100, 50, 50])
           upper_blue = np.array([130, 255, 255])
           blue_mask = cv2.inRange(hsv, lower_blue, upper_blue)
    
           result = cv2.bitwise_and(image, image, mask=blue_mask)
           return result
           
           def detect_and_highlight_red_blue(image):
           hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
           lower_red1 = np.array([0, 50, 50])
           upper_red1 = np.array([10, 255, 255])
           red_mask1 = cv2.inRange(hsv, lower_red1, upper_red1)
           lower_red2 = np.array([170, 50, 50])
           upper_red2 = np.array([180, 255, 255])
           red_mask2 = cv2.inRange(hsv, lower_red2, upper_red2)
           red_mask = cv2.bitwise_or(red_mask1, red_mask2)
           
           lower_blue = np.array([100, 50, 50])
           upper_blue = np.array([130, 255, 255])
           blue_mask = cv2.inRange(hsv, lower_blue, upper_blue)
           
           combined_mask = cv2.bitwise_or(red_mask, blue_mask)
           result = cv2.bitwise_and(image, image, mask=combined_mask)
           return result
           
           def detect_and_highlight_red_green_blue(image):
           hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
           lower_red1 = np.array([0, 50, 50])
           upper_red1 = np.array([10, 255, 255])
           red_mask1 = cv2.inRange(hsv, lower_red1, upper_red1)
           lower_red2 = np.array([170, 50, 50])
           upper_red2 = np.array([180, 255, 255])
           red_mask2 = cv2.inRange(hsv, lower_red2, upper_red2)
           red_mask = cv2.bitwise_or(red_mask1, red_mask2)
           
           lower_green = np.array([40, 50, 50])
           upper_green = np.array([200, 255, 255])
           green_mask = cv2.inRange(hsv, lower_green, upper_green)
           
           lower_blue = np.array([100, 50, 50])
           upper_blue = np.array([130, 255, 255])
           blue_mask = cv2.inRange(hsv, lower_blue, upper_blue)
           
           combined_mask = cv2.bitwise_or(red_mask, cv2.bitwise_or(green_mask, blue_mask))
           result = cv2.bitwise_and(image, image, mask=combined_mask)
           return result
           
           image = cv2.imread('pcd.jpg')
           invisible_image = make_image_invisible(image)
           brightened_image = increase_brightness(image)
           blue_detection = detect_and_highlight_blue(brightened_image)
           red_blue_detection = detect_and_highlight_red_blue(brightened_image)
           red_green_blue_detection = detect_and_highlight_red_green_blue(brightened_image)

           plt.figure(figsize=(10, 8))

           plt.subplot(221), plt.imshow(cv2.cvtColor(invisible_image, cv2.COLOR_BGR2RGB)), plt.title('Invisible Image')
           plt.subplot(222), plt.imshow(cv2.cvtColor(blue_detection, cv2.COLOR_BGR2RGB)), plt.title('Blue Color Detection')
           plt.subplot(223), plt.imshow(cv2.cvtColor(red_blue_detection, cv2.COLOR_BGR2RGB)), plt.title('Red-Blue Color Detection')
           plt.subplot(224), plt.imshow(cv2.cvtColor(red_green_blue_detection, cv2.COLOR_BGR2RGB)), plt.title('Red-Green-Blue Color Detection')

           plt.show()
Penjelasan:
- make_image_invisible(image): Untuk membuat gambar baru dengan ukuran yang sama seperti gambar asli (image), namun semua pikselnya diubah menjadi hitam (nilai 0) sehingga gambar tidak terlihat.
- increase_brightness(image, value=30): Untuk meningkatkan kecerahan gambar asli (image) dengan nilai tertentu (value). Peningkatan kecerahan dilakukan di ruang warna HSV (Hue, Saturation, Value).
- detect_and_highlight_blue(image): Untuk mendeteksi dan menyorot objek berwarna biru dalam gambar yang sudah dicerahkan (image). Deteksi dilakukan di ruang warna HSV dengan menentukan rentang nilai Hue (warna) untuk warna biru.
- detect_and_highlight_red_blue(image): Untuk mendeteksi dan menyorot objek berwarna merah dan biru dalam gambar yang sudah dicerahkan (image). Deteksi dilakukan di ruang warna HSV dengan menentukan dua rentang nilai Hue untuk warna merah dan satu rentang nilai Hue untuk warna biru.
- detect_and_highlight_red_green_blue(image): Untuk mendeteksi dan menyorot objek berwarna merah, hijau, dan biru dalam gambar yang sudah dicerahkan (image). Deteksi dilakukan di ruang warna HSV dengan menentukan rentang nilai Hue untuk masing-masing warna.
- image = cv2.imread('pcd.jpg'): Membaca gambar berwarna dari file "pcd.jpg" dan menyimpannya dalam variabel image.
- invisible_image = make_image_invisible(image): Membuat gambar tidak terlihat menggunakan fungsi make_image_invisible.
- brightened_image = increase_brightness(image): Meningkatkan kecerahan gambar asli menggunakan fungsi increase_brightness.
- blue_detection = detect_and_highlight_blue(brightened_image): Mendeteksi dan menyorot objek biru pada gambar yang sudah dicerahkan.
- red_blue_detection = detect_and_highlight_red_blue(brightened_image): Mendeteksi dan menyorot objek merah dan biru pada gambar yang sudah dicerahkan.
- red_green_blue_detection = detect_and_highlight_red_green_blue(brightened_image): Mendeteksi dan menyorot objek merah, hijau, dan biru pada gambar yang sudah dicerahkan.
- plt.figure(figsize=(10, 8)): Membuat canvas untuk menampilkan plot dengan ukuran 10 x 8 inci.
- Empat baris plt.subplot(...): membuat grid berisi 4 subplot (2 baris x 2 kolom) untuk menampilkan gambar hasil pemrosesan.
- plt.imshow(...): Untuk menampilkan gambar pada setiap subplot.
- Fungsi cv2.cvtColor(..., cv2.COLOR_BGR2RGB): Untuk mengubah format warna gambar dari BGR ke RGB sebelum ditampilkan dengan Matplotlib (karena Matplotlib biasanya menggunakan format RGB).
- plt.title(...): Judul untuk setiap subplot
- plt.show(): menampilkan plot yang telah dibuat.


## Teori Pendukung Project

### Teknik Segmentasi Citra

- Thresholding

Thresholding  adalah  proses  yang melibatkan  pemilihan  nilai ambang (threshold) tertentu. Semua piksel dalam citra dengan intensitas di atas nilai ambang ini dianggap sebagai bagian dari objek,  sedangkan  piksel  dengan  intensitas  di  bawah  nilai ambang dianggap sebagai latar belakang. Tujuan  utama  dari  thresholding  adalah  untuk  memisahkan objek dari latar belakang dan menciptakan citra biner di mana objek direpresentasikan sebagai piksel bernilai satu (putih) dan latar belakang sebagai piksel bernilai nol (hitam).

- Segmentasi Berdasarkan Warna

Segmentasi  berdasarkan  warna  melibatkan  pemisahan  objek dalam citra berdasarkan perbedaan warna piksel-pikselnya. Warna  adalah  atribut  visual  yang  penting  dalam  citra,  dan informasi warna dapat digunakan untuk memisahkan objek dari latar  belakang  atau  mengelompokkan  objek  berdasarkan karakteristik warna mereka. Pada citra berwarna, segmentasi  dapat  dilakukan  berdasarkan  komponen warna (misalnya, merah, hijau,  biru) atau dalam ruang warna tertentu seperti HSV (Hue, Saturation, Value).

### Representasi Citra Digital

- Visualisasi Hasil

Hasil dari pemrosesan citra seringkali divisualisasikan kembali dalam bentuk gambar, grafik, atau plot untuk memudahkan pemahaman dan interpretasi informasi yang terdapat dalam citra.


### Histogram

Histogram gambar adalah grafik yang menggambarkan penyebaran nilai- nilai intensitas piksel dari suatu gambar atau bagian tertentu didalam gambar
(Munir,2004). Berdasarkan sebuah histogram dapat diketahui frekuensi
kemunculan relatif dari intensitas pada citra. selain itu, informasi mengenai
tingkat kecerahan (brightness) dan kontras (contrast) dapat diketahui melalui
histogram.

Secara grafis histogram ditampilkan dengan diagram batang. Untuk citra
berwarna dengan model warna HSV, setiap komponen HSV (Hue, Saturation dan
Value) dinyatakan dengan histogram. Dengan demikian untuk setiap citra
berwarna dapat dibuat tiga buah histogram. Tingkat kemunculan dapat dilihat
berdasarkaan puncak dari histogram yang terbentuk (Kaswidjanti,2011).

### Operasi Pemrosesan Citra Digital

- Image Enhancement 
    - Bertujuan untuk memperbaiki kualitas citra dengan cara memanipulasi parameter-parameter citra. Dengan operasi ini, ciri-ciri khusus pada citra lebih ditonjolkan.

