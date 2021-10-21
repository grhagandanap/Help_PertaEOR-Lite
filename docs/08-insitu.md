# In-Situ Combustion Predictive Model



## Pendahuluan

___In-Situ Combustion___ merupakan salah satu metode peningkatan perolehan minyak yang tergabung dalam kelompok peningkatan perolehan termal (*Thermal Enhanced Oil Recovery* (EOR)). Dalam *in-situ combustion*, udara yang kaya akan oksigen diinjeksi ke dalam reservoir. Oksigen kemudian bereaksi dengan minyak di reservoir dalam bentuk reaksi pembakaran (*combustion*). Reaksi pembakaran ini menyebabkan kenaikan temperatur reservoir dari temperatur awal formasi menjadi temperatur *combustion*. Kenaikan temperatur reservoir menyebabkan penurunan viskositas minyak dan selanjutnya akan menyebabkan penambahan mobilitas minyak, sehingga dapat menambah tingkat perolehan minyak. Dalam *in-situ combustion*, terdapat volume minyak *in-place* yang terpakai dalam proses pembakaran. Minyak *in-place* yang terpakai dalam proses pembakaran disebut sebagai bahan bakar (*fuel*).

Prediksi performa reservoir di bawah proses *in-situ combustion* sangat diperlukan dalam studi awal reservoir (*preliminary study*) sebelum dilakukan penerapan di lapangan. Oleh karena itu, diperlukan suatu model sederhana yang dapat memprediksi performa reservoir di bawah proses *in-situ combustion* secara akurat. Sehubungan dengan ini, penelitian ini dilakukan untuk membangun suatu model sederhana yang dapat memprediksi performa reservoir di bawah pengaruh proses *in-situ combustion*.

## _In-Situ Combustion Predictive Model_

### Model Brigham, et al Untuk _Dry In-Situ Combustion_

_Predictive model_ yang dibangun mencakup dua mekanisme _in-situ combustion_, yaitu _dry in-situ combustion_ dan _wet in-situ combustion_. Untuk _dry in-situ combustion_, _predictive model_ mengacu pada metode yang dikembangkan oleh Brigham, et al (1980). Brigham, et al membangun dua korelasi untuk memprediksi performa reservoir di bawah penerapan _dry in-situ combustion_. Dua korelasi ini dibangun berdasarkan data lapangan dari reservoir yang berproduksi di bawah pengaruh proses _dry in-situ combustion_.

Korelasi dibangun berdasarkan konsep teknik dan statistik. Parameter-parameter yang biasa muncul dalam persamaan kesetimbangan panas maupun kesetimbangan massa akan disertakan sebagai variabel-variabel dalam korelasi. Selanjutnya, parameter-parameter lain yang pengaruhnya dianggap signifikan terhadap performa reservoir akan dijadikan variabel tambahan dalam korelasi. Korelasi yang dibangun menghubungkan variabel perolehan minyak dengan variabel volume fluida injeksi (*recovery* vs. *volume injected fluid*).

Beberapa asumsi beserta batasan dari korelasi Brigham, et al adalah sebagai berikut:

a. Korelasi hanya menghubungkan variabel perolehan minyak dengan variabel volume fluida injeksi.
b. Korelasi disusun berdasarkan data dari 12 lapangan (skala *field*) dan 5 lapangan (skala *pilot*).
c. Pengaruh kedalaman reservoir (*depth*) terhadap performa reservoir dianggap tidak signifikan.
d. Terdapat 10 parameter yang dijadikan variabel dalam korelasi, yaitu __(1) porositas, (2) volume injeksi udara, (3) *oxygen utilization*, (4) viskositas minyak, (5) volume minyak *in-place* yang terpakai dalam proses pembakaran, (6) saturasi minyak saat awal *combustion*, (7) ketebalan formasi, (8) *Original Oil in Place* (OOIP), (9) OIP saat *combustion* dimulai, dan (10) peningkatan produksi minyak kumulatif__.

Korelasi menghubungkan perolehan minyak dengan volume injeksi udara. Kadar oksigen dalam udara (yang diinjeksikan) merupakan parameter penting dalam proses *in-situ combustion*. Istilah injeksi udara efektif (*effective air injected*) didefinisikan sebagai banyaknya oksigen yang terkandung di dalam udara yang diinjeksikan ke dalam reservoir.
$$effective\ air\ injected = a_ie_{O_2}...(1)$$
Jumlah injeksi udara efektif per volume batuan reservoir (sebagai sumbu x atau absis dalam korelasi) dinyatakan oleh persamaan berikut.
$$absis = \frac{injeksi\ udara\ efektif}{volume\ batuan\ reservoir} = a_i \frac{\phi S_o}{N}\frac{e_{O_2}}{1-\phi}...(2)$$
dimana: </br>
$a_i$ = injeksi udara kumulatif </br>
$e_{O_2}$ = _oxygen utilization_ </br>
$\phi$ = porositas (fraksi) </br>
$S_o$ = saturasi minyak saat _combustion_ dimulai (fraksi) </br>
$N$ = OIP saat _combustion_ dimulai (bbl).

Dalam _in-situ combustion_, sebagian volume minyak di reservoir akan terpakai dalam proses pembakaran (disebut _volume of fuel burned_ = $\Delta N_b$). Perbandingan antara jumlah peningkatan volume produksi minyak dan peningkatan volume _fuel burned_ terhadap OOIP (sebagai sumbu y atau ordinat dalam korelasi) dinyatakan oleh persamaan berikut.
$$ordinat = \frac{peningkatan\ volume\ produksi\ minyak\ +\ peningkatan\ volume\ fuel\ burned}{OOIP}$$
$$ordinat = \frac{\Delta N_p + \Delta N_b}{OOIP}...(3)$$

Persamaan (2) dan (3) secara berurutan menyatakan absis (sumbu x) dan ordinat (sumbu y) dari korelasi yang akan dibangun. Parameter-parameter yang dinyatakan dalam kedua persamaan ini adalah parameter-parameter berdasarkan tinjauan teknik. Untuk melengkapi tinjauan teknik, dilakukan penambahan parameter melalui tinjauan statistik dengan analisis _multiple linear regression_. Melalui _multiple linear regression_, parameter-parameter yang dianggap signifikan dan belum disertakan dalam persamaan (2) dan (3) akan disertakan ke dalam korelasi.

Brigham, et al membangun dua korelasi berikut.

__Korelasi I__
$$\frac{y}{36.53}=(0.02S_o - 0.001h - 0.00082\mu_o)x...(4)$$
dimana:
$$y = \left( \frac{\Delta N_p + \Delta N_b}{OOIP} \right)100...(5)$$
$$x = \frac{a_ie_{O_2}}{\left(\frac{N}{\phi S_o}\right)(1-\phi)}...(6)$$
Interval nilai dimana persamaan (4) berlaku baik adalah:
$$0.36 < S_o < 0.79$$
$$4.4 < h < 150$$
$$10 < \mu_o < 700$$

__Korelasi II__
$$\frac{y}{47}=\left[0.427S_o - 0.00135h - 2.196\left(\frac{1}{\mu_o}\right)^{0.25}\right]x...(7)$$
dimana:
$$y = \left( \frac{\Delta N_p + \Delta N_b}{OOIP} \right)100...(8)$$
$$x = \frac{a_ie_{O_2}}{\left(\frac{N}{\phi S_o}\right)(1-\phi)}...(9)$$
Interval nilai dimana persamaan (7) berlaku baik adalah:
$$0.36 < S_o < 0.79$$
$$4.4 < h < 150$$
$$10 < \mu_o < 700$$

Pada kedua korelasi ini, parameter viskositas minyak (3) mendapat perhatian khusus. Jika _input_ viskositas minyak di atas 700 cp, maka Brigham menyarankan untuk menggunakan korelasi II. Namun, jika _input_ viskositas minyak di bawah 10 cp, Brigham menyarankan untuk menggunakan korelasi I.

Korelasi I memiliki standard deviasi 17% dengan _error_ maksimum 21%, sedangkan korelasi II memiliki standard deviasi 9% dengan _error_ maksimum 14%. Sehingga, secara umum dapat dikatakan bahwa korelasi II memberikan hasil yang lebih baik daripada korelasi I.

### Perhitungan Parameter-Parameter Penting ynag Dgunakan Dalam Model

### Viskositas Minyak

Viskositas minyak dihitung dengan terlebih dahulu menghitung nilai viskositas minyak pada temperatur 100°F dan 210°F.

Untuk _API_ ≤ 10:
$$\mu_{o,100} = 10^{(8.35928-0.37539API)}...(10)$$
$$\mu_{o,210} = 10^{(3.15424-0.11862API)}...(11)$$
Untuk _API_ > 10:
$$\mu_{o,100} = exp \left[BB(1)API + BB(2) +\frac{\alpha_3}{API} \right]...(12)$$
$$\alpha_3 = \frac{\alpha_2}{API}+ BB(3)...(12.a)$$
$$\alpha_2 = \frac{\alpha_1}{API}+ BB(4)...(12.b)$$
$$\alpha_1 = \frac{BB(6)}{API}+ BB(5)...(12.c)$$
$$\mu_{o,210} = exp \left[BB(7)API + BB(8) +\frac{\alpha_6}{API} \right]...(13)$$
$$\alpha_6 = \frac{\alpha_2}{API}+ BB(9)...(13.a)$$
$$\alpha_5 = \frac{\alpha_1}{API}+ BB(10)...(13.b)$$
$$\alpha_4 = \frac{BB(6)}{API}+ BB(11)...(13.c)$$
dimana: </br>
$\mu_{o,100}$ = viskositas minyak pada temperatur 100°F, cp </br>
$\mu_{o,210}$ = viskositas minyak pada temperatur 210°F, cp </br>
$API$ = _gravity oil_, °API </br>
$BB(i)$ = konstanta korelasi viskositas.

Selanjutnya, viskositas minyak dihitung menggunakan persamaan berikut.
$$\mu_o = Y(VIS)^X...(14)$$
$$Y = BB(19)R_s + BB(20) + \frac{BB(21)}{R_s}+\frac{BB(22)}{R_s^2}+\frac{BB(23)}{R_s^3}+\frac{BB(24)}{R_s^4}...(14.a)$$
$$X = BB(31)R_s + BB(32) + \frac{BB(33)}{R_s}+\frac{BB(34)}{R_s^2}+\frac{BB(35)}{R_s^3}+\frac{BB(36)}{R_s^4}...(14.b)$$
$$VIS = \mu_{o,100} \left(\frac{T_{form}}{100}\right)^{1.345 \log \left( \frac{\mu_{o,210}}{\mu_{o,100}} \right)}...(14.c)$$
dimana: </br>
$R_s$ = _solution gas oil ratio_ </br>
$T_{form}$ = temperatur formasi

Nilai konstanta korelasi viskositas, BB(*i*), untuk setiap i diberikan di tabel berikut.

|i |BB(*i*)|i |BB(*i*)|i |BB(*i*)|i |BB(*i*)|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|1| -0.000676825 |11| -190.395376 |21| 281.437484 |31| -7.34671E-05|
|2| -3.89570682 |12| 4161.01142 |22| -53791.9095 |32| 0.541912201|
|3| 272.18035 |13| -0.001495773 |23| 4985256.03 |33| 133.649237|
|4| -3470.80586 |14| 0.944396001 |24| -173099129 |34| -26771.3439|
|5| 36881.4527 |15| 3.98464375 |25| -0.000475188 |35| 2799780.44|
|6| -148843.074 |16| -186.338863 |26| 0.884019819 |36| -110373996|
|7| -0.025195294 |17| 3325.20064 |27| 7.38565439 |37| 0.000547457|
|8| -0.964528667 |18| -18147.1583 |28| -237.472458 |38| -0.375792641|
|9| 95.0590107 |19| -4.55391E-05 |29| 3301.29337 |39| 135.019571|
|10| -398.368883 |20| 0.134211338 |30| -15644.0226 |40| -857.863129|
|||||||41|-68814.674|
|||||||42|1178800.05|

Table: <span style="color: grey;"> Tabel 9.1: Konstanta korelasi viskositas, BB(*i*) </span>

#### Faktor Volume Formasi Minyak

Faktor volume formasi minyak, _B~o~_, dihitung menggunakan korelasi Vasquez-Beggs.
$$B_o = 1 + C_1R_s+(C_2+C_3R_s)(T-60) \left( \frac{API}{\gamma_{g.100}} \right) ...(15)$$
dimana: </br>
Untuk _API_ $\leq$ 30:
$$C_1 =4.677(10^{-4})$$
$$C_2 =1.751(10^{-5})$$
$$C_3 =-1.811(10^{-8})$$
Untuk _API_ > 30:
$$C_1 = 4.67 (10^{-4})$$
$$C_2 = 1.1 (10^{-5})$$
$$C_3 = 1.337 (10^{-9})$$

#### Faktor Volume Fomasi Air

Dengan asumsi air formasi berupa pure water, faktor volume formasi air dihitung menggunakan
persamaan berikut.
$$B_w = 1 + [1.2(10)^{-4}(T_{form}-60)] + [1(10)^{-6}(T_{form}-60)^2] - [3.33(10)^{-6}P_{form}]...(16)$$
dimana: </br>
$T_{form}$ = temperatur formasi = $70 + \left[(depth)(0.011 \frac{^\circ F}{ft})\right]$ </br> 
$P_{form}$ = tekanan formasi = $14.7 + \left[(depth)(0.011 \frac{0.433}{2} \frac{psi}{ft})\right]$.

#### Laju Injeksi Udara

Nilai laju injeksi udara ditentukan berdasarkan asumsi bahwa lama injeksi udara dibatasi maksimum 10 tahun. Selanjutnya, nilai _default_ laju injeksi untuk tahun pertama adalah sebesar 50% dari nilai laju yang diperoleh dari persamaan (17), dan konstan sesuai dengan nilai laju yang diperoleh dari persamaan (17) untuk tahun-tahun selanjutnya.
$$Q_{air,inj} = \frac{43560A_{patt}h_{net}V_{sweep}AR}{\left( \frac{365}{t_{life}} \right)} ...(17)$$
dengan:
$$A_{patt} = \frac{A}{N_{well,inj}}...(18)$$
$$N_{well,inj} = \frac{N_{well,prod}}{2}...(19)$$
$$AR = [0.073 \log \mu_o]+0.2 -0.1f_{wa}...(20)$$
$$
f_{wa} =
\begin{cases}
  0,\ dry\ combustion \\
  1,\ wet\ combustion \\
\end{cases}
...(21)
$$
dimana: </br>
$Q_{air,inj}$ = laju injeksi udara, MSCF/D </br>
$A_{patt}$ = _pattern area_ </br>
$h_{net}$ = _net thickness_, ft </br>
$V_{sweep}$ = _volumetric sweep_ = $\begin {cases} 0.4,\ jika\ A \geq 20\ acres\\ 0.5,\ jika\ 5 \leq A \leq 20\ acres \\ 0.6,\ jika\ A < 5\ acres\end{cases}$ </br>
$A$ = luas daerah reservoir(*area*) </br>
$N_{well,inj}$ = jumlah sumur injeksi per _area_ </br>
$N_{well,prod}$ = jumlah sumur produksi per _area_ </br>
$f_{wa}$ = perbandingan air dengan udara, STB/MSCF = $\begin{cases} 0,\ untuk\ dry\ combustion \\ 1,\ untuk\ wet\ combustion \end{cases}$

### Parameter-Parameter Performa _In-Situ Combustion_

Algoritma yang digunakan dalam menghitung parameter-parameter _recovery_ adalah berdasarkan metode Brigham, et al (1980) untuk _dry in-situ combustion_ dan metode Ganon-Wygal (1974) dan Prats (1982) untuk _wet in-situ combustion_.

Beberapa asumsi dan batasan dari _predictive model_ yang dibangun adalah sebagai berikut.

1. Tidak terdapat saturasi _free gas_.
2. _Volumetric sweep efficiency_ ditentukan berdasarkan total luas daerah lapangan.
3. Rasio injeksi udara terhadap bahan bakar ditentukan bernilai konstan, yaitu 70 Mcf udara terbakar per barel minyak terbakar.
4. Banyaknya air yang terproduksi dihitung menggunakan hubungan berikut.
$$produksi\ air= air\ injeksi\ + air\ yang\ terpindahkan\ selama\ proses\ pembakaran\\ - air\ yang\ tertinggal\ di\ zona\ pembakaran$$
5. Nilai saturasi air di zona pembakaran (*burned zone*) ditentukan sebesar 20% untuk *wet combustion* dan 0% untuk *dry combustion*.
6. Banyaknya gas yang terproduksi dihitung menggunakan hubungan berikut.
$$produksi\ gas = injeksi\ nitrogen\ + gas\ hasil\ reaksi\ pembakaran\\ - gas\ yang\ tertinggal\ di\ zona\ pembakaran$$
7. Nilai saturasi gas di zona pembakaran ditentukan sebesar 80% untuk *wet combustion* dan 0% untuk *dry combustion*.
8. Lama injeksi udara dibatasi maksimum 10 tahun.
9. Perbandingan jumlah sumur produksi terhadap jumlah sumur injeksi adalah 2 : 1.

#### Tekanan Injeksi

Besarnya tekanan injeksi dihitung menggunakan persamaan berikut.
$$P_{inj} = \left[ \frac{Q_{air,inj} \log (626A_{patt}^{0.5})}{[2.2(10)^{-5-f_{wa}}]kh_{net}+P_{form}^2} \right]^{0.5}...(22)$$
Nilai tekanan injeksi harus lebih kecil dari tekanan formasi. Nilai _default_ yang digunakan adalah
$$P_{inj} = P_{form} + 200$$

#### Kebutuhan Daya Kompressor

Kebutuhan daya kompressor per pola injeksi (*horsepower compressor*) dapat diprediksi melalui persamaan berikut.
$$HP_{compressor} = \frac{Q_{air,inj}}{48.13(10)^3(PDP^{0.25})}...(23)$$
$$PDP = 1.2 [[1.81(10)^{-6}(depth+1500)Q_{air,inj}^2]+[P_{inj}^2]]^{0.5}...(23)$$
dimana: </br>
$HP_{compressor}$ = kebutuhan daya kompressor </br>
$Q_{air,inj}$ = laju injeksi udara </br>
$P_{inj}$ = tekanan injeksi

#### Injeksi Udara dan Injeksi Air Kumulatif

Jumlah injeksi udara kumulatif, $V_{air,cum}$ dan jumlah injeksi air kumulatif, $V_{water,cum}$ dihitung untuk setiap _time step i_ menggunakan persamaan berikut.
$$V_{air,cum}(i)=V_{air,cum}(i-1) + \left[Q_{air,inj}t_D \left( \frac{365.25}{1000} \right)\right]...(24)$$
$$V_{water,cum}(i)=V_{water,cum}(i-1) + \left[0.5f_{wa}Q_{air,inj}t_D \left( \frac{365.25}{1000} \right)\right]...(24)$$
dimana: </br>
$V_{air,cum}$ = kumulatif injeksi udara, MMSCF </br>
$V_{water,cum}$ = kumulatif injeksi air, MSTB </br>
$t_D$ = _dimensionless time_ = $\begin{cases} 0.25,\ untuk\ t < 1\ tahun \\ 0.5,\ untuk\ t > 1\ tahun \end{cases}$ </br>
$t$ = lama injeksi, tahun </br>
$f_{wa}$ = perbandingan air dengan udara

#### Volume Minyak Kumulatif yang Terpakai dalam Proses Pembakaran

Seperti yang telah dijelaskan sebelumnya bahwa pada _in-situ combustion_ terdapat sejumlah minyak _in-place_ yang terpakai dalam proses pembakaran. Volume minyak yang terpakai dalam proses pembakaran ini dihitung untuk setiap _time step i_ menggunakan persamaan berikut: 
$$N_{fuel}(i) = \frac{V_{air,cum}(i)}{AFR}...(26)$$
dimana: </br>
$N_{fuel}(i)$ = volume minyak yang terpakai dalam proses pembakaran </br>
$AFR$ = perbandingan volume udara terhadap volume bahan bakar (*air-fuel ratio*), nilai *default* = 70 MSCF/STB.

Volume zona pembakaran dinyatakan oleh persamaan berikut.
$$V_{burn} = \frac{1000[V_{air,cum}(i)-V_{air,cum}(i-1)]}{\left( \frac{AR}{43560} \right)}...(27)$$
dimana: </br>
$V_{burn}$ = volume zona pembakaran (*burned zone volume*) </br>
$AR$ = kebutuhan udara, MSCF/cuft.

#### Produksi Minyak Kumulatif

Produksi minyak kumulatif dihitung di setiap _time step i_ menggunakan persamaan berikut.
$$N_p(i) = [0.64(OIP) \tan Y] - N_{fuel}(i)...(28)$$
$$OIP = \frac{7758 \phi S_{oi} A_{patt}h_{net}}{\left( \frac{B_{oi}}{1000} \right)}...(29)$$
dengan:
$$Y = 0.581X^{0.82}...(30)$$
$$X = 1000C_1C_2[V_{air,cum}(i)+V_{water,cum}(i)]...(31)$$
$$C_1 = (0.427S_{oi} - 0.00135h_{net}) + \frac{2.196}{\mu_o^{0.25}}...(32)$$
$$C_2 = \frac{oxygen\ utilization}{\left( \frac{7758A_{patt}h_{net}}{B_{oi}} \right)(1-\phi)} ...(33)$$
dimana: </br>
$N_p$ = produksi minyak kumulatif, MSTB </br>
$OIP$ = jumlah _oil in place_ saat _in-situ combustion_ dimulai </br>
$\phi$ = porositas </br>
$S_{oi}$ = saturasi minyak saat _in-situ combustion_ dimulai </br>
$B_{oi}$ = faktor volume formasi minyak saat _in-situ combustion_ dimulai </br>
$oxygen\ utilization$ = kadar oksigen dalam udara yang diinjeksikan ke reservoir (nilai _default_ = 0.95).

#### Produksi Gas Kumulatif

Dengan asumsi temperatur zona pembakaran adalah 1260°F pada kondisi tekanan injeksi $P_{inj}$, maka produksi gas kumulatif dihitung di setiap _time step i_ menggunakan persamaan berikut.
$$G_p(i) = G_p(i-1) + \frac{[(339.6825t_DQ_{air,inj})+(1-(1.93\phi P_{inj}V_{burn}(S_{wr}f_{wa})))]}{1000}...(34)$$
dimana: </br>
$G_p$ = produksi gas kumulatif, MMSCF </br>
$S_{wr}$ = saturasi air residu (setelah pembakaran) </br>
$V_{burn}$ = volume zona pembakaran.

#### Produksi Air Kumulatif

Produksi air kumulatif dihitung di setiap _time step i_ menggunakan persamaan berikut.
$$W_p(i) = W_p(i-1) + \frac{365.25f_{wa}Q_{air,inj}t_D+ \left( \frac{7758 \phi V_{burn}(1-(S_{wr}f_{wa})-S_{oi})}{B_{wi}} \right)}{1000} ...(35)$$
dimana: </br>
$W_p$ = produksi air kumulatif </br>
$B_{wi}$ = faktor volume formasi air, bbl/STB.
