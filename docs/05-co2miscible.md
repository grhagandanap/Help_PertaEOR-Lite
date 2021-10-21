# CO~2~ Miscible Predictive Model



## Pendahuluan

### Kondisi PVT 

Kondisi PVT dalam CO~2~ _flood_ lebih kompleks jika dibandingkan dengan hidrokarbon _flood_. Kelarutan yang relatif tinggi dalam air dan pengurangan pH akan mempengaruhi kondisi PVT dalam reservoir, fluida reservoir, dan komposisi batuan. Grigg dan Siagian telah menyelidiki fenomena tersebut dalam aliran 4 fasa CO~2~ _flood_ dalam temperatur rendah. Berikut adalah kesimpulan yang mereka hasilkan:

- Lima fasa, yaitu _aqueous_, _liquid_ HC, _liquid_ CO~2~, _gaseous_ CO~2~, dan endapan padat aspaltan bisa terdapat pada CO~2~ _flood_.
- Jumlah fasa tergantung pada tekanan, temperatur, dan komposisi.
- Gas yang terkondensasi menjadi fasa cair kedua dapat menjadi signifikan pada temperatur di atas tekanan kritis CO~2~ dan dekat dengan tekanan saturasi CO~2~.
- Efisiensi perpindahan CO~2~ akan meningkat karena berkurangnya tekanan sampai _minimum miscibility pressure_ tercapai.
- Hal-hal di atas diperlukan untuk mempertimbangkan perilaku kompleks dari reservoir ketika memprediksi CO~2~ _flood_. Oleh karena itu, penting untuk melakukan simulasi komposisi yang rinci sebagai bagian dari perencanaan CO~2~ flood.
- Bila terdapat air, hidrat setinggi 10$^\circ$C jika tekanan lebih besar dari 45 bar. Formasi hidrasi dapat menjadi masalah di choke dan katup di mana tekanan berkurang tiba-tiba dan CO~2~ mendingin karena ekspansi. Kemungkinan terbentuknya hidrat CO~2~ harus diperhitungkan ketika prediksi CO~2~ _flood_ dilakukan. CO~2~ dapat terbentuk pada suhu yang tepat dan tekanan hidrat CO~2~ dapat terjadi pada suhu.

### Wettability

_Wettability_ batuan reservoir menjadi salah satu faktor yang paling penting dalam strategi operasi untuk proses EOR. Tetapi, menurut McDougal, Dixit, dan Sorbie, analisa yang tepat terhadap _wettability_ batuan ini masih kurang. Ada juga indikasi bahwa _core flood_ dan _tes capillary tube visual cell_ dapat memberikan perubahan inkonsisten dalam _wettability_ batuan karena CO~2~ _miscible flooding_. CO~2~ mengurangi pH air formasi dan beberapa bukti eksperimental menunjukkan bahwa CO~2~ dapat mengurangi sifat _water-wet_ dalam sel kapiler. Pengalaman dari kedua tes laboratorium dan studi data lapangan mendukung bahwa karakteristik _wettability_ batuan sangat penting untuk CO~2~ _flood_.

Rogers dan Grigg menyimpulkan bahwa kondisi *water-wet* mengindikasikan untuk dilakukan injeksi gas terus menerus (*continous gas injection*). Sementara kondisi *oil-wet* mengindikasikan untuk dilakukannya proses *Water Alternating Gas* (WAG) dengan rasio kecepatan optimum sebesar 1:1. Selain itu, model *water-wet* menunjukkan bahwa faktor yang mendominasi dalam proses _displacement_ adalah gravitasi, sedangkan dalam *oil-wet*, faktor pengendalinya adalah *viscous fingering*.

### Keuntungan dan Kerugian Melakukan Injeksi CO~2~

#### Keuntungan

Perbedaan terbesar CO~2~ dibandingkan dengan gas lainnya adalah bahwa CO~2~ dapat meng-ekstrak komponen berat sampai dengan C-30. Kelarutan CO~2~ dalam minyak menyebabkan minyak mengembang. Pengembangan (*swelling*) ini tergantung pada jumlah kandungan metana di minyak. Karena CO~2~ tidak menggantikan semua metana ketika terjadi kontak dengan fluida reservoir, jika terdapat banyak kandungan metana dalam minyak, maka fenomena _swelling_ makin berkurang.

Beberapa keuntungan dalam menggunakan CO~2~ _flooding_ diantaranya adalah:

- Mendorong terjadinya _swelling_.
- Mengurangi viskositas minyak.
- Meningkatkan densitas minyak.
- Dapat terlarut dalam air.
- Dapat menguap dan mengekstrak bagian dari minyak.
- Mencapai _miscibility_ (terlarut) pada tekanan hanya 100 sampai 300 bar.
- Mengurangi densitas air.
- Mengurangi perbedaan densitas antara air dan minyak dan kemudian mengurangi perubahan untuk _gravity segregation_.
- Mengurangi tegangan permukaan antara minyak dan air, dan memberikan proses _displacement_ yang lebih efektif 

#### Kerugian

Salah satu masalah utama dalam CO~2~ _flooding_ adalah tingginya mobilitas dari CO~2~. Hal ini dapat menyebabkan _gravity tonguing_ dan _viscous fingering_. Beberapa cara untuk mengatasi hal tersebut diantaranya adalah:

- Pemasangan _well packers_ dan perforasi yang baik.
- Menutup sumur produksi untuk mengatur aliran.
- _Alternating_ CO~2~ dan injeksi air (WAG).
- Penambahan _foam solution_ dengan CO~2~.

## _Miscible CO~2~ Predictive Model_

### Sifat-Sifat Fisik Fluida

CO~2~ murni tidak berwarna, tidak berbau, gas inert, dan non-mudah terbakar. Berat molekul pada kondisi standar 44,010 g/mol, yang merupakan satu setengah kali lebih tinggi daripada udara. CO~2~ berbentuk padatan pada suhu dan tekanan rendah, tetapi sebagian besar tergantung pada temperatur seperti yang ditunjukkan pada gambar diagram fasa untuk CO~2~ di bawah. Fasa cair dan fasa uap CO~2~ berdampingan dari titik tripel dan sampai ke titik kritis pada kurva. Di bawah suhu kritis CO~2~ dapat berupa cairan atau gas melalui berbagai tekanan. Di atas suhu kritis CO~2~ akan ada sebagai gas terlepas dari tekanan. Namun, pada semakin tinggi tekanan superkritis, uap menjadi dan berperilaku lebih seperti cair.

Berikut ini adalah beberapa sifat fisik lainnya dari CO~2~:

- __Densitas__ </br>
Densitas fluida meningkat dengan tekanan pada temperatur di atas titik kritis, namun muncul diskontinuitas pada temperatur di bawah titik kritis.
- __Faktor kompresibilitas (*z-factor*)__ </br>
Kompresibilitas CO~2~, gas alam, dan campuran CO~2~-metana merupakan fungsi dari tekanan pada beberapa temperatur yang berbeda. Kompresibilitas CO~2~ jauh berbeda dibandingkan dengan gas alam dan campuran CO~2~-metana. Pada 100 bar dan 40 $\circ$C kompresibilitas bervariasi masing-masing dari 0.25 sampai 0.4 dan 0.85.
- __Viskositas__</br>
Viskositas CO~2~ sangat tergantung pada tekanan dan temperatur. Viskositas CO~2~ akan meningkat dengan meningkatnya tekanan pada temperatur reservoir tertentu. Viskositas gas alam dan air formasi berada di kisaran 0.02 sampai 0.03 dan 0.3 sampai 1.0 cp.
- __Kelarutan dalam air__</br>
Kelarutan CO~2~ dalam air meningkat dengan meningkatnya tekanan. Namun, kelarutan CO~2~ akan menurun dengan peningkatan suhu dan salinitas.
- __Viskositas Minyak__</br>
Viskositas minyak dihitung dengan menggunakan korelasi dari Beggs and Robinson,
$$\mu_o = A\mu_{oD}^B...(1)$$
dimana,
$$\mu_{oD}=10^X - 1...(2)$$
$$X = \frac{Y^{1.163}}{T}...(3)$$
$$Y = 10^Z...(4)$$
$$Z= 3.0324-0.02023(API)...(5)$$
dengan
$$A= \frac{10.715}{(R_s+100)^{0.515}}$$
$$B= \frac{5.44}{(R_s+150)^{0.338}}$$

#### _Solution Gas-Oil Ratio_

_Solution gas-oil ratio_ (*R~s~*) dihitung menggunakan korelasi Vasquez-Beggs. Dalam korelasi Vasquez-Beggs, nilai _specific gas gravity_, $\gamma_g$, terlebih dahulu dikoreksi ke dalam kondisi tekanan separator 100 psig dan temperatur separator (temperatur separator diasumsikan sama dengan temperatur reservoir).
$$\gamma_{g.100} = \gamma_g \left[ 1+\left(5.912(10^{-5})(API)(T)\log \left( \frac{64.7}{114.7} \right) \right) \right]...(6)$$
dimana:</br>
$\gamma_{g.100}$ = _specific gravity gas_ pada kondisi separator (interval nilai: 0.8 ≤ $\gamma_{g.100}$ ≤ 1.4). </br>
$\gamma_g$ = _specific gravity gas_ pada kondisi reservoir (*default*: $\gamma_g$ = 0.8).

Selanjutnya, _solution gas-oil ratio_ dihitung sebagai berikut: </br>
Untuk $API \leq$ 30:
$$R_s = 0.0362 \gamma_{g.100}P_{form}^{1.0937}exp \left[ 25.724 \left( \frac{API}{T+460} \right) \right]...(7)$$
Untuk $API$ > 30:
$$R_s = 0.0178 \gamma_{g.100}P_{form}^{1.187}exp \left[ 23.931 \left( \frac{API}{T+460} \right) \right]...(8)$$

#### Faktor Volume Formasi Minyak

Faktor volume formasi minyak, *B~o~*, dihitung menggunakan korelasi Vasquez-Beggs.
$$B_o = 1 + C_1R-s + (C_2 + C_3R_s)(T-60) \left( \frac{API}{\gamma_{g.100}} \right)...(9)$$
dimana: </br>
Untuk $API \leq$ 30:
$$C_1 = 4.677 (10^{-4})$$
$$C_2 = 1.751 (10^{-5})$$
$$C_3 = -1.811 (10^{-8})$$
Untuk $API$ > 30:
$$C_1 = 4.67 (10^{-4})$$
$$C_2 = 1.1 (10^{-5})$$
$$C_3 = 1.337 (10^{-9})$$

### _Fractional Flow_ Model

Tinjau aliran minyak beserta *miscible solvent* (CO2 *flooding*) di reservoir. Anggap bahwa perpindahan minyak (*i* = 2) oleh kontak pertama *miscible solvent* (*i* = 3) dan adanya air (*i* = 1). Jika komponen-komponen tersebut didistribusikan dalam fasa *aqueous* (*j* = 1) dan *oleic* (*j* = 2), hukum kekekalan massa dalam satu dimensi didefinisikan sebagai:
$$\frac{\partial C_i}{\partial t_D}+\frac{\partial F_i}{\partial x_D}=0,\ dimana\ i=1,2,3...(10)$$
dimana konsentrasi (C) dan _fractional flux_ (F) dinyatakan sebagai:
$$C_i = C_{i1}S_1 + C_{i2}S_2...(11)$$
$$F_i = C_{i1}f_1 + C_{i2}f_2...(12)$$
$$f_1 = 1 + \left( \frac{k_{r2\mu1}}{k_{r1\mu2}} \right)^{-1}...(13)$$
$$f_2 = 1-f_1...(14)$$

Persamaan (12) adalah berdasarkan asumsi _ideal mixing_, fluida dan batuan bersifat _incompressible_, serta diabaikannya dispersi, tekanan kapiler, dan pengaruh gaya gravitasi. Persamaan (12) dapat juga dituliskan sebagai:
$$\frac{\partial C_i}{\partial t_D}+\left(\frac{\partial F_i}{\partial x_D}\right)_{xD}=0,\ dimana\ i=1,2,3...(15)$$

Dengan mendefinisikan _concentration velocity_ (kecepatan dari konsentrasi tetap) dari persamaan (15) di bawah kondisi koherensi, dapat ditunjukkan bahwa kecepatan konsentrasi dari semua komponen adalah:
$$v_{C_i}=\frac{dF_i}{dC_i},\ dengan\ i = 1,2,3...(16)$$
di mana _total derivative_ dalam persamaan (16) mengikuti kondisi koherensi. Persamaan (16) dapat dinyatakan sebagai masalah nilai eigen dengan solusi dua kecepatan karakteristik dalam bentuk $\lambda$^±^.

Kecepatan $\lambda$^±^ mendefinisikan dua tipe dari jalur komposisi (arah). Jalur kecepatan ($\lambda$) harus melewati kondisi awal (di dalam reservoir), sedangkan jalur kecepatan ($\lambda$^±^) yang lebih lambat akan melalui kondisi injeksi. Urutan jalan yang melewati kondisi awal dan kondisi batas untuk permasalahan tertentu disebut rute komposisi. Rute komposisi tersebut yang mungkin bisa terjadi hanya _physical_ _composition route_, seperti kecepatan konsentrasi menurun secara monoton (tetapi tidak secara kontinu) dari kondisi awal ke kondisi injeksi. Jika penurunan secara monoton ini tidak terjadi, persamaan (16) menjadi:
$$v_{C_i} = \frac{\Delta F_i}{\Delta C_i}...(17)$$
Jika perhitungan jalur (*path*) dilakukan dengan kondisi diferential, persamaan (17), hasilnya akan sama dengan perhitungan jalur (*path*) yang dihitung dengan integral, persamaan (8). Maka, perkiraan *shock region* merupakan analogi yang tepat dengan teori Buckley-Leverett. Penjelasan ini diilustrasikan oleh gambar berikut:

<div class="figure" style="text-align: center">
<img src="images/co2miscible/skema.png" alt="Skematik dari jalur komposisi" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-2)Skematik dari jalur komposisi</p>
</div>
<p> &nbsp; </p>

Gambar (1) menjelaskan bahwa jalur cepat, digambarkan dengan garis tegas digambarkan melalui kondisi awal I (saturasi minyak-air di reservoir). Jalur lambat melalui kondisi injeksi J (campuran CO~2~ - air) dan A merupakan titik perpotongan I dan J. Sepanjang rute komposisi I-A-J, kurva F~3~-C~3~ (atau F~2~-C~2~) diperlihatkan melalui gambar berikut.

<div class="figure" style="text-align: center">
<img src="images/co2miscible/skema2.png" alt="Skema dari plot _flux_-konsentrasi" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-3)Skema dari plot _flux_-konsentrasi</p>
</div>
<p> &nbsp; </p>

Titik-titik A’ and A” secara bersamaan memenuhi kecepatan diferential dan kecepatan integral, kecepatan konsentrasi $c_{C_3}$ digantikan oleh $v_{\Delta C_3}$ untuk C~3I~ < C~3~ < C~3A’~, and C~3A~ < C~3~ < C~3A”~. Diluar segmen ini kecepatan dihitung dengan persamaan (6).

<div class="figure" style="text-align: center">
<img src="images/co2miscible/effluent.png" alt="_Effluent histories_" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-4)_Effluent histories_</p>
</div>
<p> &nbsp; </p>

Untuk memodifikasi teori _fractional flow_ agar menyertakan efek _viscous fingering_, ubah definisi dari F~i~, persamaan (12) menjadi:
$$F_i = C_{i1}f_1 + f_{i2}f_2,\ dengan\ i = 1,2,3...(18)$$
dimana f~i2~ adalah _fractional flow_ dari komponen saat fasa _oleic_,
$$f_{i2}=\frac{\frac{C_{i2}}{\mu_i^0}}{C_{12}\mu_1^0+C_{22}\mu_2^0+C_{32}\mu_3^0}...(19)$$
Dengan analogi Koval, persamaan (19) dapat dimodifikasi menjadi:
$$f_{32} = \frac{\frac {C_{22}}{K}}{C_{12}\left( \frac{\mu_3^0}{\mu_1^0} \right)+\frac{C_{22}}{K}+C_{32}}...(20)$$
$$f_{22} = \frac{C_{32}}{C_{12}\left( \frac{\mu_3^0}{\mu_1^0} \right)+\frac{C_{22}}{K}+C_{32}}...(21)$$
$$f_{12}=1-f_{22}-f_{32}...(22)$$
dimana:
$$K = H \left[0.78 + 0.22\left( \frac{\mu_2^0}{\mu_3^0} \right)^{\frac{1}{4}} \right]^4...(23)$$

K adalah __Koval Factor__, dan H adalah _faktor heterogenitas_.

_Koval factor_ adalah model analitik untuk mengetahui performa dari laju alir yang tidak stabil dalam media berpori. Koval model ini merupakan analogi dari metode Buckley-Leverett dan dikalikan dengan indeks heterogenitas dari sistem yang dipakai sebagai _input_ (H-*factor*), dengan faktor laju alir yang tidak stabil (dalam hal ini gravitasi), *E*, dimana _Koval Factor_ didefinisikan sebagai _K~G~ = HE_. _Koval Factor_ ini diimplementasikan dalam _modified fractional flow function_ yang didalamnya terdapat efek dilusi yang terjadi ketika CO2 menjauh dari _interface_ sebagai deskripsi _countercurrent gravitational flow_.

_Koval factor_ ini hanya berpengaruh dalam _fractional flow_ dari minyak dan CO~2~ dalam fasa _oleic_. Sedangkan _displacement_ dari air tidak terpengaruh _Koval Factor_. Dalam _secondary case_ ini, besarnya _breakthrough_ oleh pelarut diperkirakan sebesar 1/K. Sedangkan untuk kasus _tertiary_, _breakthrough_ merupakan fungsi dari viskositas.

### Parameter-Parameter Performa _Miscible_ CO~2~

Terdapat dua metode yang dapat digunakan untuk memprediksi performa injeksi CO~2~ _Miscible_, yaitu metode simulasi numerik dan analisis persamaan _material balance_. Persamaan _material balance_ adalah metode klasik untuk evaluasi reservoir, sedangkan simulasi numerik adalah teknik yang lebih modern untuk analisa reservoir. Limitasi dari metode simulasi numerik adalah dibutuhkannya data dalam jumlah besar dan geometri reservoir sangat diperhitungkan agar mendapatkan hasil yang seakurat mungkin. Sedangkan dalam persamaan _material balance_, data yang digunakan sedikit dan geometri reservoir tidak terlalu diperhitungkan.

Penelitian ini menggunakan metode simulasi numerik dalam memprediksi performa reservoir di bawah proses CO~2~ _miscible flooding_. Beberapa asumsi yang digunakan dalam metode ini diantaranya adalah:

- Perpindahan minyak karena CO~2~ _flooding_ seluruhnya _miscible_.
- Bisa menggunakan berbagai macam nilai _injection rate_ (konstan) di reservoir.
- _Viscous fingering_ dideskripsikan oleh _Koval Factor_.
- CO~2~ dan air diinjeksikan bersama sesuai proporsi yang ditentukan oleh WAG _ratio_ (konstan).
- Tidak ada saturasi _free gas_.
- Sifat-sifat fluida dianggap konstan.

Prediksi performa CO~2~ _miscible flooding_ menggunakan persamaan modified _fractional flow_ untuk 1D yang menyertakan efek _viscous fingering_, keheterogenan reservoir, dan _gravity segregation_.

#### Segregasi Gravitasi Dalam Teori 1-Dimensi

Simulasi numerik digunakan untuk mengembangkan korelasi dari _vertical sweep efficiency_ sebagai fungsi dari sejauh mana segregasi gravitasi terjadi. Gaya _viscous-to-gravity_ ditandai dengan rasio waktu yang dibutuhkan sebuah partikel fluida untuk menempuh perjalanan antara sumur (t~h~) dengan waktu yang dibutuhkan oleh fluida untuk bergerak dari bagian bawah reservoir ke bagian atas reservoir (t~v~).

Rata-rata kecepatan _front_ dalam pola _five-spot_ adalah:
$$\bar v_h = \frac{0.016q}{h\sqrt A}...(24)$$
dan jarak _injector-producer_ (dalam feet) adalah:
$$L = \frac{\sqrt{43560A}}{2\sin 45^\circ} = 147.58\sqrt A...(25)$$

Maka, t~h~ didefinisikan sebagai:
$$t_H = \frac{L}{\bar v_h} = \frac{9224hA}{q}...(26)$$

Dari hukum Darcy, kecepatan fluida dalam arah vertikal akibat gravitasi dinyatakan oleh persamaan berikut.
$$v_v = 2.7401(10)^{-3}\frac{k_v\Delta \rho}{\mu}...(27)$$
dimana $\Delta \rho$ adalah perbedaan densitas air dan densitas CO~2~ dan $\mu_{is}$ adalah viskositas CO~2~. Kemudian v~v~ didefinisikan sebagai h/v~v~, maka rasio waktunya adalah:
$$\frac{t_h}{t_v} = 2.5271\frac{k_v\Delta \rho}{\mu}...(28)$$

#### _Areal Sweep Efficiency_

Karena _viscous fingering_ termasuk dalam teori _fractional flow_, maka penting untuk tidak memasukkannya dalam korelasi _areal sweep_. Claridge mengantisipasi hal ini dan menanganinya dengan mendeskripsikan suatu wilayah yang disebut “_invaded area_” _sweep efficiency_ dan menurunkan persamaan untuk mendeskripsikan _invaded area sweep_ di dalam _confined five spot pattern_. Claridge juga membuat prosedur untuk mengkombinasikan _areal_ dan _displacement sweep_ untuk kasus _secondary_ dan _non_ WAG _displacement_. Generalisasi dari prosedur Claridge digunakan untuk _first-contact miscible flood_ dengan sembarang WAG _ratio_ dan sembarang kondisi awal. _Areal sweep_ saat _breakthrough_ dihitung dari rasio mobilitas berdasarkan pada konsentrasi rata-rata di belakang _front_ saat _breakthrough_. Setelah _breakthrough_, prosedur iterasi digunakan untuk mencari “_apparent_” _pore volume_ yang benar dari _areal sweep efficiency_ yang dihitung.

#### Koval Factor

Untuk menyertakan efek _viscous fingering_, _fractional flow_ dimodifikasi oleh koval factor untuk _secondary_ maupun _tertiary recovery_ yaitu,
$$Y = H\left( 0.78 - 0.22 \left( \frac{\mu_o}{\mu} \right)^{0.25} \right)^4...(29)$$
Dimana Y merupakan _Koval Factor_ dan H merupakan faktor heterogenitas masing-masing _layer_ dan diberikan oleh persamaan berikut,
$$H = 10^{0.2\frac{VDP}{1-VDP}}...(30)$$

#### Perhitungan Konsentrasi Rata-Rata di Belakang _Front_

Dalam menyertakan _areal sweep_ dalam perhitungan, diperlukan perhitungan konsentrasi rata-rata masing-masing komponen di belakang _front_. Untuk _timestep_ - *i*.
$$\bar C_o = C_o^i - \frac{(f_o^i-f_o^{ISP})}{_D^i}...(31)$$
$$\bar C_{co2} = C_{co2}^i - \frac{(f_o^i-f_o^{ISP})}{_D^i}...(32)$$
Dimana $f_j^{ISP}$ merupakan _fractional flux_ dari injeksi.

Setelah _breakthrough_, _areal sweep efficiency_ diberikan oleh persamaan berikut,
$$E_A=\frac{PV_i+0.4X}{1+X}...(33)$$
dimana,
$$X = \left[ \frac{\left(\lambda - \left( \frac{1-PV_i}{PV_i-0.4} \right) \right)(PV_i)+1}{25 \left( \left( \frac{\left( 1-PV_i\right)}{\left( PV_i - 0.4\right)} \right)^{0.833}+1.3+2.3PV_i \right)}\left( \frac{1-PV_i}{PV_i-0.4} \right) \right]^{(0.85-0.55PV_i)}...(34)$$
_Flood mobility ratio_ didefinisian sebagai:
$$\lambda = \frac{\lambda_j}{\lambda_i}...(35)$$
dimana $\lambda_j$ merupakan mobilitas di bealakang _front_ dan dapat diberikan oleh persamaan berikut,
$$\lambda_j = \frac{k_{ro}}{\mu_{mix}} + \frac{k_{rw}}{\mu_{w}}...(36)$$
dimana *k~ro~* dan *k~rw~* dievaluasi pada kondisi $\bar C_o$. Selain itu viskositas campuran setelah _breakthrough_ ditentukan dengan persamaan,
$$\mu_{mix} = frac{1}{\left[ \left( \frac{C_{CO_2}}{\mu_{CO_2}} \right)^{0.25} + \left( \frac{C_o}{\mu_o} \right)^{0.25} \right]^{0.4}}...(37)$$
Sedangkan mobilitas di depan _front_ diberikan oleh persamaan berikut,
$$\lambda_i = \frac{k_{ro}}{\mu_{o}} + \frac{k_{rw}}{\mu_{w}}...(38)$$
_Dimensionless time_ dari aliran diberikan oleh persamaan berikut,
$$t_{D1} = (1+WAG)\bar C_{CO_2}...(39)$$
Setelah _breakthrough_ fluida,
$$t_{D1} = \frac{t_D}{E_a}...(40)$$
dimana,
$$t_D = \frac{\frac{365\Delta t_{incrQres}}{PV_{pattern}}}{E_a}...(41)$$
Dengan _pore volume_ dari reservoir diberikan oleh:
$$PV_{pattern} = 7758.A.\phi.h...(42)$$
Untuk aliran dalam 2-Dimensi,
$$t_{D2} = \frac{t_D}{(1+WAG)}\bar C_{CO_2}...{43}$$
Sedangkan setelah _breakthrough_ terjadi,
$$t_{D2} = E_a...(44)$$
dimana _Water Alternating Gas_ (WAG) _Ratio_,
$$WAG = \frac{t_D}{CO_{2_i}}...(45)$$
Dimana, _W~i~_ merupakan volume air terinjeksi dan $CO_{2_i}$ adalah volume _CO~2~_ terinjeksi.

#### Perhitungan Laju Alir Produksi Masing-Masing Fluida

Laju alir produksi masing-masing komponen diberikan oleh persamaan berikut,

Untuk Minyak
$$q_o = \frac{q_i}{B_o} \left( \left( 1-\frac{dE_a}{dt_D} \right)f_o + \frac{dE_a}{dt_D}f_{oi} \right)...(46)$$

Untuk Gas/CO~2~
$$q_{CO_2} = \frac{q_i}{B_{CO_{2}}} \left( \left( 1-\frac{dE_a}{dt_D} \right)f_CO_{2} + \frac{dE_a}{dt_D}f_{CO_{2_i}} \right)...(47)$$

Untuk Air
$$q_w = \frac{q_i}{B_w} \left( \left( 1-\frac{dE_a}{dt_D} \right)f_o + \frac{dE_a}{dt_D}(1-f_{oi}-f_{CO_{2_i}}) \right)...(48)$$

Sebelum _breakthrough_ terjadi, laju alir masing-masing komponen diberikan sebagai berikut,

Untuk Minyak
$$q_o = f_{oi}\frac{q_i}{B_o}...(49)$$

Untuk Gas/CO~2~
$$q_{CO_2} = 0...(50)$$

Untuk Air
$$q_w = (1-f_{oi}-f_{CO_{2_i}}) \frac{q_i}{B_w}...(51)$$

#### Efek Segregasi Gravitasi

Akibat densitas CO~2~ yang jauh lebih rendah dibandingkan minyak dan air, maka CO~2~ memiliki kecenderungan untuk berada pada posisi _top pay zone_. Dalam pemodelan _miscible_ CO~2~, hal ini dilakukan dengan memberikan suatu faktor pengali terhadap _koval factor_ dengan persamaan berikut,
$$F = 0.565 \log2.5271 \frac{k_v}{k_h} A \frac{(\rho_w-\rho_{CO_2})}{q_i\mu}+0.87...(52)$$
