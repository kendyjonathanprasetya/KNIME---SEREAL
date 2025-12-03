📘 Laporan Analisis Dataset Nutrisi Sereal (via KNIME)
---
🥣 Pendahuluan
---
Dataset berisi berbagai jenis sereal beserta kandungan nutrisinya. Tujuan analisis ini adalah:

Membersihkan data (outlier & missing value)

Menampilkan visualisasi nutrisi

Menghitung rata-rata nilai nutrisi

Mengidentifikasi sereal aman untuk kondisi kesehatan tertentu

Workflow KNIME digunakan karena alurnya mudah divisualisasikan dan modular.

🧩 Step-by-Step Workflow & Fungsi Node
---
Berikut ringkasan setiap node dalam pipeline KNIME:

1️⃣ CSV Reader
---
📥 Fungsi: Membaca file DATA CSV SEREAL.csv.

📌 Apa yang dilakukan:

Mengimpor seluruh dataset nutrisi sereal ke dalam workflow.

2️⃣ Column Filter
---
🧹 Fungsi: Menghapus kolom yang tidak dibutuhkan.

📌 Apa yang dilakukan:

Menghilangkan kolom non-esensial (misalnya ID, catatan teks, dll)

Menyisakan hanya kolom nutrisi seperti calories, fat, sugar, fiber, sodium, dll.

3️⃣ Numeric Outliers
---
📊 Fungsi: Mendeteksi nilai outlier pada kolom numerik.

📌 Apa yang dilakukan:

Menandai data nutrisi yang terlalu ekstrem (misalnya sodium sangat tinggi).

Output diteruskan ke node berikut untuk diperbaiki.

4️⃣ Missing Value
---
🛠️ Fungsi: Mengatasi missing value dan mengganti outlier dengan mean.

📌 Apa yang dilakukan:

Mengisi nilai kosong dengan mean kolom masing-masing.

Mengganti nilai outlier (ditandai sebelumnya) menjadi mean juga.

Data jadi rapi, bersih, dan siap dianalisis.

5️⃣ Visualisasi Nutrisi (Banyak Node Chart/Plot)
---
📈 Fungsi: Memberikan gambaran distribusi tiap nutrisi.

📌 Visualisasi mencakup:

Histogram / Bar chart kalorinya

Grafik sugar, sodium, fiber, protein, dll

Tujuan: hanya untuk melihat penyebaran & pola dasar

⚠️ Karena ini hanya eksplorasi awal, bagian ini dipersingkat dalam laporan.

6️⃣ GroupBy (Mean Aggregation)
---
🔎 Fungsi: Menghitung rata-rata semua nutrisi.

📌 Insight yang didapat:
---
Mengetahui apakah secara umum:

Kandungan gula sereal cenderung tinggi?

Sodium rata-rata aman?

Kalorinya tinggi atau rendah?

Hasil ini membantu menilai apakah sereal secara keseluruhan sehat atau tidak.

📋 Hasil Rata-rata Setiap Nutrisi:


| Nutrisi  | Rata-rata      |
| -------- | -------------- |
| Calories | **106.6 kcal** |
| Sugar    | **7.02 g**     |
| Sodium   | **159.6 mg**   |
| Fiber    | **1.793 g**    |
| Protein  | **2.419 g**    |
| Carbo    | **14.8 g**     |
| Fat      | **1.013 g**    |
| Potass   | **87.4 mg**    |
---
🔍 1. Calories — 106.6 kcal

📌 Penilaian: Moderat–Rendah

Berdasarkan sumber ini:
Rekomendasi sarapan sehat menurut Academy of Nutrition and Dietetics berada di kisaran 100–300 kcal, dan sereal “rendah kalori” biasanya berada ≤ 120 kcal per porsi.

👉 Karena rata-rata dataset adalah 106.6 kcal, maka:

Masuk kategori rendah kalori

Aman untuk diet

Tidak berlebihan untuk penderita diabetes atau penyakit metabolik

⭐ Kesimpulan:
Kalori sereal secara keseluruhan cukup baik dan tidak berlebihan.

🔍 2. Sugar — 7.02 g

📌 Penilaian: Cenderung Tinggi

Berdasarkan sumber ini:
WHO dan American Heart Association (AHA) merekomendasikan:

Batas maksimum gula tambahan untuk makanan rendah gula adalah ≤ 5 g per sajian.

Di atas 6 g biasanya dianggap moderately high sugar.

👉 Karena rata-rata dataset adalah 7.02 g, maka:

Rata-rata sereal lebih tinggi dari batas “rendah gula”

Banyak sereal komersial memang memiliki tambahan gula

Tidak ideal untuk diabetes atau diet rendah gula

⭐ Kesimpulan:
Gula rata-rata agak tinggi, sehingga konsumsinya perlu diperhatikan terutama untuk penderita diabetes.

🔍 3. Sodium — 159.6 mg

📌 Penilaian: Menengah–Sedikit Tinggi

Berdasarkan sumber ini:
FDA menyatakan makanan dianggap low-sodium apabila memiliki:

≤ 140 mg sodium per porsi.

👉 Dengan rata-rata 159.6 mg, berarti:

Rata-rata sereal melewati batas low sodium

Cenderung tinggi bagi penderita tekanan darah tinggi

Tidak semua sereal cocok untuk hipertensi

⭐ Kesimpulan:
Sodium rata-rata sedikit tinggi dan belum masuk kategori aman untuk penderita hipertensi.

🔍 4. Fiber — 1.793 g

📌 Penilaian: Rendah

Berdasarkan sumber ini:
Kategori makanan:

High-fiber food → ≥ 5 g

Good source of fiber → ≥ 3 g

Poor source → < 3 g

👉 Dengan rata-rata hanya 1.8 g, maka:

Mayoritas sereal adalah poor source of fiber

Tidak optimal untuk pencernaan

Tidak membantu rasa kenyang lama (penting untuk diet)

⭐ Kesimpulan:
Serat rata-rata terlalu rendah dan tidak ideal untuk diet atau kesehatan usus.

🔍 5. Protein — 2.419 g

📌 Penilaian: Rendah

Berdasarkan sumber ini:
Ahli gizi menyarankan sarapan mengandung 4–8 g protein agar lebih mengenyangkan dan stabil untuk gula darah.

👉 Karena rata-rata hanya 2.4 g, berarti:

Sereal kurang mengenyangkan bila dimakan sendirian

Perlu tambahan protein (yogurt, susu, telur, almond)

Tidak cukup baik untuk kebutuhan sarapan seimbang

⭐ Kesimpulan:
Protein rata-rata kurang, sehingga sereal perlu dikombinasikan dengan sumber protein lain.

🔍 6. Carbohydrates — 14.8 g

📌 Penilaian: Moderat

Berdasarkan sumber ini:
Sereal breakfast umumnya mengandung 12–20 g karbohidrat per porsi.

👉 Nilai 14.8 g berarti:

Masuk kategori normal

Tidak berlebihan

Masih aman untuk diabetes asal gula dan serat ikut memenuhi syarat

⭐ Kesimpulan:
Karbohidrat rata-rata normal, tidak terlalu tinggi.

🔍 7. Fat — 1.013 g

📌 Penilaian: Sangat Rendah

Berdasarkan sumber ini:
Produk low-fat umumnya memiliki:

≤ 3 g fat per porsi

Sereal whole-grain biasanya memiliki 0–2 g fat

👉 Karena rata-rata 1 g, maka:

Sangat rendah lemak

Ideal untuk penderita kolesterol tinggi

Mudah dicerna

⭐ Kesimpulan:
Lemak rata-rata sangat baik dan aman untuk penderita kolesterol tinggi.

🔍 8. Potassium — 87.4 mg

📌 Penilaian: Rendah

Berdasarkan sumber ini:
FDA menyatakan makanan layak disebut “sumber potassium baik” apabila memiliki:

≥ 200 mg per porsi

👉 Nilai rata-rata 87 mg menunjukkan bahwa:

Sereal tidak menyumbang banyak mineral potassium

Tidak cukup untuk mendukung fungsi otot & keseimbangan elektrolit

⭐ Kesimpulan:
Potassium rata-rata rendah, sehingga sereal bukan sumber mineral yang signifikan.



📌 Ringkasan:
Kalium rata-rata rendah, kurang mendukung kesehatan otot & tekanan darah.

| Nutrisi         | Nilai Rata-rata | Penilaian               |
| --------------- | --------------- | ----------------------- |
| **Kalori**      | 106.6 kcal      | ✔️ Baik & cukup rendah  |
| **Gula**        | 7.02 g          | ⚠️ Cenderung tinggi     |
| **Sodium**      | 159.6 mg        | ⚠️ Sedikit tinggi       |
| **Serat**       | 1.793 g         | ❌ Rendah                |
| **Protein**     | 2.419 g         | ❌ Rendah                |
| **Karbohidrat** | 14.8 g          | ✔️ Normal               |
| **Lemak**       | 1.013 g         | ✔️ Sangat rendah (baik) |
| **Kalium**      | 87.4 mg         | ❌ Rendah                |

7️⃣ Row Filter (Kriteria Kesehatan) Berserta Visualisasi
---
🚦 Fungsi: Memfilter sereal berdasarkan kebutuhan kesehatan tertentu.
❤️ 1. Kolesterol Tinggi & Penyakit Jantung
🔍 Fokus utama: Lemak total & gula
📌 Kriteria:

Fat ≤ 1 g

Sugar ≤ 5 g

Orang dengan kolesterol tinggi memerlukan makanan rendah lemak dan rendah gula agar kadar LDL tetap terkendali. Karena itu, batasan lemak ≤ 1 g dan gula ≤ 5 g dipakai sebagai patokan untuk memilih sereal yang aman bagi kesehatan jantung.

❤️ Rekomendasi Sereal Aman untuk Kolesterol Tinggi - Visualisasi
<img width="1392" height="349" alt="image" src="https://github.com/user-attachments/assets/fbf90438-a111-433e-835d-b53efc1cfc5c" />


| No | Nama Sereal                   |
| -- | ----------------------------- |
| 1  | Wheaties                      |
| 2  | Wheat Chex                    |
| 3  | Triples                       |
| 4  | Total Whole Grain             |
| 5  | Total Corn Flakes             |
| 6  | Strawberry Fruit Wheats       |
| 7  | Special K                     |
| 8  | Shredded Wheat (semua varian) |
| 9  | Rice Krispies                 |
| 10 | Rice Chex                     |
| 11 | Puffed Wheat                  |
| 12 | Puffed Rice                   |
| 13 | Product 19                    |
| 14 | Nutri-Grain Wheat             |
| 15 | Maypo                         |
| 16 | Kix                           |
| 17 | Grape-Nuts Flakes             |
| 18 | Grape-Nuts                    |
| 19 | Double Chex                   |
| 20 | Crispix                       |
| 21 | Cream of Wheat (Quick)        |
| 22 | Corn Flakes                   |
| 23 | Corn Chex                     |
| 24 | Bran Flakes                   |
| 25 | All-Bran                      |


⭐ Insight Singkat:
Sereal-sereal ini umumnya sangat rendah lemak dan banyak yang berbasis whole grain. Kombinasi tersebut sangat efektif untuk menjaga kestabilan LDL dan mendukung kesehatan kardiovaskular secara keseluruhan.

🌾 2. Sembelit & Gangguan Pencernaan
🔍 Fokus utama: Serat
📌 Kriteria:

Fiber ≥ 5 g

Serat tinggi membantu meningkatkan pergerakan usus dan melancarkan pencernaan. Karena itu, batas minimal 5 g serat dipilih sebagai standar untuk menentukan sereal yang benar-benar efektif melawan sembelit.

🌾 Rekomendasi Sereal Tinggi Serat untuk Pencernaan - Visualisasi
<img width="1395" height="349" alt="image" src="https://github.com/user-attachments/assets/04e706b0-4388-48fa-8e58-794a10e5601a" />


| No | Nama Sereal                           |
| -- | ------------------------------------- |
| 1  | Bran Flakes                           |
| 2  | Fruit & Fibre (Dates, Walnuts & Oats) |
| 3  | Fruitful Bran                         |
| 4  | Post Nat. Raisin Bran                 |
| 5  | Raisin Bran                           |


⭐ Insight Singkat:
Sereal-sereal ini berada dalam kategori “very high fiber cereals” yang secara klinis dikenal membantu meningkatkan kesehatan usus dan mengatasi sembelit secara konsisten.

🫀 3. Hipertensi / Darah Tinggi
🔍 Fokus utama: Sodium
📌 Kriteria:

Sodium ≤ 140 mg
<img width="433" height="407" alt="image" src="https://github.com/user-attachments/assets/7024d3ed-5f43-4d5d-9670-4a78117e5029" />

Menurut pedoman nutrisi, makanan dikategorikan “low sodium” apabila mengandung ≤ 140 mg natrium per porsi. Karena itu, angka ini dipakai sebagai batas untuk memilih sereal yang aman bagi penderita hipertensi.

🫀 Rekomendasi Sereal Low-Sodium untuk Hipertensi - Visualisasi
<img width="1391" height="349" alt="image" src="https://github.com/user-attachments/assets/b09ea343-8195-40ca-a294-72794a4b2d85" />


| No | Nama Sereal                       |
| -- | --------------------------------- |
| 1  | 100% Bran                         |
| 2  | 100% Natural Bran                 |
| 3  | All-Bran with Extra Fiber         |
| 4  | Apple Jacks                       |
| 5  | Clusters                          |
| 6  | Corn Pops                         |
| 7  | Cracklin' Oat Bran                |
| 8  | Cream of Wheat (Quick)            |
| 9  | Crispy Wheat & Raisins            |
| 10 | Froot Loops                       |
| 11 | Frosted Mini-Wheats               |
| 12 | Fruity Pebbles                    |
| 13 | Golden Crisp                      |
| 14 | Grape-Nuts Flakes                 |
| 15 | Great Grains Pecan                |
| 16 | Maypo                             |
| 17 | Muesli (Raisins, Dates & Almonds) |
| 18 | Puffed Rice                       |
| 19 | Puffed Wheat                      |
| 20 | Quaker Oat Squares                |
| 21 | Quaker Oatmeal                    |
| 22 | Raisin Nut Bran                   |
| 23 | Raisin Squares                    |
| 24 | Shredded Wheat (semua varian)     |
| 25 | Smacks                            |
| 26 | Strawberry Fruit Wheats           |
| 27 | Trix                              |


⭐ Insight Singkat:
Menariknya, banyak sereal manis tetap rendah sodium. Namun meskipun aman untuk tekanan darah, tidak semuanya cocok untuk kondisi lain seperti diabetes, jadi pemilihan tetap perlu disesuaikan.

⚖️ 4. Kelebihan Berat Badan / Obesitas
🔍 Fokus utama: Kalori, gula, serat
📌 Kriteria:

Kalori ≤ 110

Gula ≤ 5 g

Serat ≥ 3 g

Untuk menurunkan berat badan, makanan rendah kalori dan rendah gula tetapi tetap tinggi serat sangat penting. Standar ini memastikan sereal mengenyangkan tanpa memberikan beban kalori berlebih.

⚖️ Rekomendasi Sereal Aman untuk Diet / Obesitas - Visualisasi
<img width="1391" height="346" alt="image" src="https://github.com/user-attachments/assets/1710153e-dbc3-45c2-be56-269e6f833d97" />


| No | Nama Sereal                 |
| -- | --------------------------- |
| 1  | Bran Flakes                 |
| 2  | Grape-Nuts Flakes           |
| 3  | Grape-Nuts                  |
| 4  | Nutri-Grain Wheat           |
| 5  | Shredded Wheat              |
| 6  | Shredded Wheat ’n’ Bran     |
| 7  | Shredded Wheat (spoon size) |
| 8  | Strawberry Fruit Wheats     |
| 9  | Total Whole Grain           |
| 10 | Wheat Chex                  |
| 11 | Wheaties                    |



⭐ Insight Singkat:
Ini adalah kombinasi ideal: rendah kalori, rendah gula, dan cukup serat untuk kenyang lebih lama. Banyak sereal di kategori ini juga cocok untuk jantung dan metabolisme.

🍬 5. Diabetes
🔍 Fokus utama: Gula, karbo cepat, serat
📌 Kriteria:

Sugar ≤ 5 g

Carbo ≤ 30 g

Fiber ≥ 5 g

Kriteria ini dibuat untuk memastikan sereal tidak menyebabkan lonjakan gula darah. Serat yang tinggi membantu memperlambat penyerapan glukosa, sedangkan batas gula & karbo mencegah kenaikan gula darah yang cepat.

🍬 Rekomendasi Sereal Aman untuk Diabetes - Visualisasi
<img width="1388" height="346" alt="image" src="https://github.com/user-attachments/assets/133691d6-b84a-4be6-a5b0-83c0978f9058" />


| No | Nama Sereal |
| -- | ----------- |
| 1  | Bran Flakes |


⭐ Insight Singkat:
Hanya satu sereal yang memenuhi semua batas ketat untuk diabetes. Namun, setelah data nutrisi lengkap tersedia, mungkin ada kandidat lain yang hampir lolos dan cocok untuk dikonsumsi secara moderat.

Dengan filter ini, kita bisa membuat klasifikasi sederhana sereal mana yang aman & disarankan.

💡 Insight Penting yang Diperoleh
---
✨ 1. Profil sereal cenderung “ringan”
Secara keseluruhan, sereal dalam dataset memiliki kalori, lemak, dan protein yang relatif rendah. Ini membuatnya cocok sebagai sarapan cepat, tapi kurang memberikan rasa kenyang jangka panjang.

✨ 2. Cenderung tinggi gula
Rata-rata gula cukup tinggi untuk standar sehat, sehingga banyak sereal komersial berpotensi tidak ideal bagi penderita diabetes atau orang yang mengurangi gula.

✨ 3. Serat tidak terlalu tinggi
Sebagian besar sereal bukan sumber serat yang baik — artinya untuk kesehatan pencernaan atau diet, hanya sedikit sereal yang benar-benar unggul.

✨ 4. Sodium berada di level menengah
Tidak terlalu tinggi, tapi juga tidak rendah. Untuk penderita hipertensi, seleksi sereal tetap perlu dilakukan.

✨ 5. Secara keseluruhan: “cukup baik, tapi perlu seleksi”
Jika dilihat sebagai satu kelompok, sereal-sereal ini cenderung aman untuk dikonsumsi sehari-hari, asalkan dipilih berdasarkan kebutuhan kesehatan masing-masing.
Row Filter membantu mengidentifikasi sereal mana yang aman untuk kolesterol, hipertensi, diabetes, obesitas, dan pencernaan, karena tidak semua sereal memenuhi standar gizi yang diperlukan.

✨ 6. Rekomendasi sereal berdasarkan penyakit lebih mudah dilakukan
Karena dataset sudah bersih dan stabil, Row Filter mampu mengidentifikasi dengan jelas sereal mana yang aman untuk diabetes, hipertensi, atau kolesterol, sehingga pengambilan keputusan lebih akurat.

🏁 Kesimpulan
---
🎯 Workflow KNIME berhasil melakukan:

Import & pembersihan data

Perbaikan outlier & missing value

Visualisasi nutrisi

Analisis rata-rata setiap nutrisi

Klasifikasi sereal berdasarkan kebutuhan kesehatan

Dengan workflow ini, kamu bisa:

Menilai apakah sereal tertentu sehat

Memberikan rekomendasi berdasarkan kondisi penyakit

Mengetahui pola umum nutrisi dalam semua sereal
