# CO~2~ Huff & Puff Predictive Model



## Pendahuluan

Injeksi CO~2~ *Huff & Puff* adalah salah satu metode *Enhanced Oil Recovery* (EOR) yang menggunakan gas CO~2~ sebagai fluida injeksinya. Injeksi dilakukan pada sebuah sumur produksi dengan sistem siklus, satu sistem siklus terdiri dari tahapan injeksi, tahapan perendaman (*soaking*), dan tahapan produksi. Meskipun aplikasi injeksi CO~2~ telah banyak menggunakan ssitem berkelanjutan tetapi tidak mengurangi minat terhadap injeksi CO2 Huff & Puff dikarenakan oleh hal-hal berikut:

a. Sebagai *pilot project* untuk injeksi CO~2~ secara kontinyu.
b. Investasi yang murah dengan pengembalian yang cepat.
c. Lebih mudah beradaptasi terhadap gejolak harga minyak.

Berikut akan dibahas mengenai penyusunan model prediktif injeksi CO~2~ *huff & puff* untuk memprediksi performa reservoir saat dilakukan metode EOR CO~2~ *huff & puff injection*. Model prediktif dibuat berdasarkan hasil simulasi reservoir dan aplikasi *Artificial Neural Network* (ANN). Profil produksi dibentuk berdasarkan model prediktif laju alir maksimum, waktu saat laju alir maksimum, periode produksi dan laju alir di akhir periode produksi.

## Pembutan _Predictive Model_

Model prediktif injeksi CO2 huff & puff dibentuk menggunakan fungsi *Multilayer Neural Network* pada *software C*MG-CMOST berdasarkan data hasil simulasi reservoir. Tahapannya adalah pembuatan model sintetis, analisa sensitivitas, pembuatan *proxy model* untuk tiap titik hasil, dan pembuatan profil produksi.

Model sintetis reservoir yang dibangun merupakan *single well model* dengan menggunakan jenis *grid* radial dan menggunakan skala logaritmik. Model reservoir diasumsikan tertutup (*bounded*), homogen dan perforasi pada sumur injeksi dan produksi dipasang pada seluruh zona *net sand*. Properti batuan reservoir telah disesuaikan dengan *screening criteria* pada berbagai studi dan aplikasi lapangan yang telah dilakukan sebelumnya.
<div class="figure" style="text-align: center">
<img src="images/co2huffnpuff/sintesis.png" alt="Model sintetis reservoir untuk pembuatan model prediktif CO~2~ huff &amp; puff" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-2)Model sintetis reservoir untuk pembuatan model prediktif CO~2~ huff & puff</p>
</div>
Fluida yang digunakan adalah *black oil* yang memiliki rentang API 15-45. Model fluida dibentuk menggunakan *software* CMG-WINPROP untuk melakukan lumping komponen dalam upaya mengelompokkan komponen dengan kategori: Komponen ringan, komponen sedang, komponen berat dan pengotor (*impurities*).
<div class="figure" style="text-align: center">
<img src="images/co2huffnpuff/phase.png" alt="_Phase envelope_ fluida reservoir yang digunakan untuk membangun model prediktif." width="50%" />
<p class="caption">(\#fig:unnamed-chunk-3)_Phase envelope_ fluida reservoir yang digunakan untuk membangun model prediktif.</p>
</div>
Kurva permeabilitas relatif dibangun menggunakan Persamaan Corey.

Untuk permeabilitas relatif minyak dan air ditentukan dengan persamaan berikut ini:
$$k_{ro} = (k_{rocw}) \left[ \frac{1-S_{w}-S_{orw}}{1-S_{wc}-S_{orw}} \right]^{n_o}...(1)$$
$$k_{rw} = (k_{rwiro}) \left[ \frac{S_{w}-S_{wc}}{1-S_{wc}-S_{orw}} \right]^{n_{ow}}...(2)$$
<div class="figure" style="text-align: center">
<img src="images/chemicalhnp/oilwater.png" alt="Kurva permeabilitas relatif minyak-air" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-4)Kurva permeabilitas relatif minyak-air</p>
</div>
Berikut asumsi yang digunakan dalam membuat tabel permeabilitas relatif minyak dan gas:
$$S_{wc}=S_{wcrit}...(3)$$
$$S_{orw}=S_{oirw}...(4)$$
Untuk permeabilitas relatif _liquid_ dan gas ditentukan dengan persamaan berikut ini:
$$k_{rog} = (k_{rogcg})\left[ \frac{1-S_{g}-S_{Lc}}{1-S_{gc}-S_{Lc}} \right]^{n_{og}}...(5)$$
$$k_{rg} = (k_{rgci}) \left[ \frac{S_{g}-S_{gc}}{1-S_{gc}-S_{Lc}} \right]^{n_g}...(6)$$
<div class="figure" style="text-align: center">
<img src="images/chemicalhnp/oilgas.png" alt="Kurva permeabilitas relatif liquid-gas" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-5)Kurva permeabilitas relatif liquid-gas</p>
</div>
Berikut asumsi yang digunakan dalam membuat tabel permeabilitas relatif _liquid_-gas:
$$S_{wcon} = S_{Lcon}$$
$$S_{Lrg} = S_{Lcon}+S_{org}$$
$$S_{gc} = S_{gcrit}$$
$$N_o = N_g$$
$$N_{ow} = N_{og}$$

Tekanan alir produksi bawah sumur di-*set* dua pertiga dari tekanan reservoir, hal ini dilakukan sebagai best practice pada aplikasi dilapangan yang menggunakan *inflow performance relationship* dalam menentukan tekanan dasar sumur (P~wf~). Parameter operasi adalah total gas CO~2~ yang diinjeksikan. Gas yang diinjeksikan adalah CO~2~ murni tanpa campuran. Injeksi dilakukan selama beberapa hari yang diikuti oleh waktu peremdaman (*soaking time*) dan selanjutnya sumur dibuka untuk diproduksikan (*Put on Production*). Sumur akan diproduksikan hingga mencapai limit ekomosisnya yaitu sekitar 2 STB/D.

Analisa sensitivitas dilakukan menggunakan fungsi CMOST pada software CMG, dengan menggunakan metode *Response Surface Methodology*. Metode ini digunakan untuk menentukan hubungan antara variabel *input* (parameter) dan respon (*objective function*). Seluruh parameter divariasikan dalam sejumlah eksperimen yang dibuat menggunakan *Latin Hypercube Method* dan respon dari seluruh eksperimen akan digunakan untuk membentuk sebuah *proxy model*.

Ada 21 parameter yang divariasikan, dengan *range* nilai masing-masing parameter yang berbeda. Tabel 1 menunjukkan parameter-parameter dan variasi nilainya:

|No|Parameter|Satuan|Min|Max|Keterangan|
|:---:|:---:|:---:|:---:|:---:|:---:|
|1 | _Luas area pattern_ (A)|acre|5|10||
|2 | Ketebalan _net pay_(h)|ft|10|100||
|3 |Porositas|%|0.1|0.25||
|4 |Permeabilitas Lateral|mD|10|300||
|5 |kv/kh _Ratio_|fraksi|0.1|0.3||
|6 |Densitas Fluida Reservoir|$^\circ$API|15|45|SG 0.7978 - 0.9599|
|7 |Temperatur Reservoir |$^\circ$F|100|200||
|8 | _Slug_ Injeksi CO~2~|SCF|500000|15000000||
|9 |Tekanan Reservoir|psia|500|2000||
|10|Saturasi Air|fraksi|0.4|0.74||
|11| Swcon||0.125|0.4||
|12 |Krocw ||0.4|0.95||
|13 |Krwcw ||0.15|0.7||
|14 |Sorg||0|0.2||
|15 |Nw||1|3||
|16 |Now||1|5||
|17 |BHP|Psia|263|1950||
|18 |Sgcon||0|0.1||
|19 |Krgcl||0.5|1||
|20 |Hari Injeksi|Hari|1|5||
|20 |Hari _Soaking_|Hari|5|40||

Table: <span style="color: grey;"> Tabel 12.1: _Range_ Nilai Parameter _Input_ Untuk Studi Sensitivitas dan Pembuatan _Proxy Model_ </span>

Respon yang diukur adalah volume produksi dan laju alir fluida. Dari respon tersebut akan direkam nilai produksi kumulatif, laju alir maksimum (Q~max~), dan periode produksi (t~stop~). Masing-masing respon ini akan dibentuk _proxy model_-nya untuk membangun profil produksi suatu fluida reservoir.
<div class="figure" style="text-align: center">
<img src="images/co2huffnpuff/proxy.png" alt="Pembangunan profil produksi fluida reservoir berdasarkan _proxy model_" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-6)Pembangunan profil produksi fluida reservoir berdasarkan _proxy model_</p>
</div>
_Proxy model_ dibuat berdasarkan hubungan parameter dan respon pada fungsi CMOST pada _software_ komersial CMG. Ada 2 jenis _proxy model_ yang dapat dibentuk: _Polynomial Regression_ dan _Neural Network_. Setelah membandingkan keakuratan kedua jenis model, jenis _proxy model_ yang dominan digunakan adalah _Neural Network_, tipe _Multilayer Neural Network_. 

Jumlah eksperimen simulasi yang digunakan untuk membangun _proxy model_ adalah 7000 eksperimen, dengan jumlah perbandingan data _training_ dan data testing sebesar 80%-20%.

Profil produksi akan dibentuk menggunakan _proxy model_ variabel-variabel respon di atas untuk fluida minyak, air, gas, dan _liquid_ seperti tertera pada Tabel 2. Di bawah ini akan dilampirkan seluruh _proxy model_ pembentuk profil produksi dalam bentuk weighting dari _neural network architecture_.

|Type|Proxy|R^2^ Training|R^2^ Testing|
|:---:|:---:|:---:|:---:|
|Oil|Cummulative Oil/ N~p~|0.99|0.97|
|Oil|Max Oil Production|0.98|0.89|
|Field|Water Saturation (EndSim)|0.99|0.99|
|Field|Pressure (EndSim)|0.99|0.99|

Table: <span style="color: grey;"> Tabel 12.2:Jumlah _Proxy Model_ yang Dibentuk untuk Profil Produksi Berbagai Fluida Reservoir </span>
