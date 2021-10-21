# Polymer Predictive Model



## Pendahuluan  

__Injeksi polimer (*polymer flood*)__ merupakan bagian dari metode _Enhanced Oil Recovery_ (EOR)yang menggunakan mekanisme injeksi zat kimia ke dalam reservoir dengan tujuan untuk menambah tingkat perolehan minyak. Zat kimia yang diinjeksikan ke dalam reservoir adalah
polimer.

Adanya konsentrasi polimer dalam air injeksi akan menambah viskositas air. Akibatnya mobilitas air akan berkurang, sehingga nilai _mobility ratio M_ akan menjadi lebih kecil. Berkurangnya nilai _M_ menyebabkan bertambahnya nilai dari ketiga parameter efisiensi, yaitu _displacement efficiency_ (*E~D~*), _areal sweep efficiency_ (*E~A~*), dan _vertical sweep efficiency_ (*E~V~*), sehingga efisiensi dari proses _displacement_ akan bertambah, yang menyebabkan bertambahnya tingkat perolehan minyak.

_Polymer Flood Predictive Model_ merupakan model yang dibangun untuk memprediksi performa reservoir di bawah pengaruh injeksi polimer. _Predictive model_ yang dibangun merupakan model tiga dimensi dan dua fasa (minyak dan air) dimana _displacement efficiency_ dihitung menggunakan teori _fractional flow_, sedangkan _areal_ dan _vertical sweep_ dihitung menggunakan pendekatan _streamtube_. Efek dari _slug size_ polimer dimodelkan dengan menggunakan korelasi. Selain itu, model juga menyertakan sifat-sifat fisis dari larutan polimer ke dalam perhitungan, seperti adsorpsi polimer, efek _permeability reduction_, dan efek non-Newtonian.

Beberapa asumsi yang digunakan dalam penyusunan _predictive model_ adalah sebagai berikut:

a. Fluida dan batuan dianggap _incompressible_.
b. Aliran fluida terjadi secara isotermal.
c. Tidak terjadi perubahan volume selama proses pencampuran polimer dengan air.
d. Efek salinitas terhadap viskositas polimer diabaikan.
e. Gaya gravitasi dan gaya kapiler diabaikan.
f. Tidak terjadi _fingering_.
g. Dispersi pada larutan polimer diabaikan.
h. Tidak terjadi _crossflow_ antar lapisan reservoir.
i. Nilai permeabilitas, porositas, _thickness_, dan _initial water saturation_ adalah homogen untuk setiap lapisan reservoir.
j. Adsorpsi polimer terjadi secara seketika.
k. Beda tekanan antara sumur injeksi dan sumur produksi dinyatakan konstan, sehingga nilai _injectivity_ berubah-ubah untuk setiap _time step_ bergantung pada mobilitas fluida di setiap _streamtube_.
l. Faktor keheterogenan reservoir dapat dinyatakan dalam bentuk input data untuk setiap lapisan reservoir maupun dalam bentuk koefisien variasi permeabilitas Dykstra-Parsons (*V~DP~*).
m. Injeksi polimer diasumsikan membentuk empat zona (atau *bank*) di reservoir, yaitu *initial water bank* (*bank* ke-1), *oil ba*nk atau *connate water bank* (*bank* ke-2), *polymer bank* (*bank* ke-3), dan *chase water bank* (*bank* ke-4).

## Teori _Fractional Flow_

Sama seperti proses _waterflooding,_ prediksi performa _polymer flood_ membutuhkan dua informasi penting, yaitu informasi mengenai profil saturasi air di reservoir selama periode _flooding_ dan informasi mengenai nilai saturasi air rata-rata di reservoir pada waktu tertentu selama periode _flooding_. Kedua informasi penting ini dapat diperoleh dengan memahami teori _fractional flow_ untuk _polymer flood_. Dalam model, teori _fractional flow_ digunakan untuk menghitung _displacement efficiency_ dari injeksi polimer, dimana injeksi polimer terlebih dahulu diasumsikan dilakukan secara kontinu (tidak menggunakan _slug_). Koreksi terhadap efek injeksi non-kontinu dengan menggunakan ukuran _slug_ akan dilakukan kemudian.

Terdapat dua perbedaan utama antara teori _fractional flow_ untuk _waterflooding_ dengan _polymer flood_. Pertama, terlarutnya polimer (dengan konsentrasi tertentu) dalam air injeksi pada _polymer flood_ akan menyebabkan perbedaan profil saturasi air di reservoir dengan proses _waterflooding_, sehingga secara otomatis mempengaruhi kurva _fractional flow of water_ (*f~w~*). Kedua, adanya penyerapan (adsorpsi) polimer oleh batuan reservoir menyebabkan fenomena _displacement_ di reservoir menjadi lebih rumit dibandingkan dengan proses _waterflooding_.

<div class="figure" style="text-align: center">
<img src="images/polymer/elemen.png" alt="Elemen volume dengan panjang \Delta x" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-2)Elemen volume dengan panjang \Delta x</p>
</div>
<p> &nbsp; </p>

Total akumulasi zat kimia *i* dalam elemen volume di atas dinyatakan oleh:

$$
  \left( \begin{array}{c}
      total\ akumulasi\ zat\ kimia\ i\\ 
      dalam\ elemen\ volume\\ 
      selama\ selang\ waktu\ \Delta x
  \end{array}\right)
  =
  \left( \begin{array}{c}
      akumulasi\ zat\ kimia\ i\ dalam\\ 
      elemen\ volume\ akibat\\ 
      perubahan\ konsentrasi\ zat\ i\\
      atau\ perubahan\ saturasi\ air\\
      dimana\ zat\ i\ tersebut\ terlarut\\
      selama\ selang\ waktu\ \Delta t
  \end{array}\right)
  +
  \left( \begin{array}{c}
      akumulasi\ zat\ kimia\ i\\ 
      dalam\ permukaan\ batuan\\
      reservoir\ akibat\ adsorpsi\\
      selama\ selang\ waktu\ \Delta t
  \end{array}\right)
$$

$${(q_tf_wC_i)_x \Delta t - (q_tf_wC_i)_{x+\Delta x} \Delta t} \\ = {[(C_iS_w)_{t+\Delta t}\Delta xA-(C_iS_w)_{t}\Delta xA}]\phi\\ + {[(A_i\rho_{gr}(1-\phi)\Delta x)_{t+\Delta t}-(A_i\rho_{gr}(1-\phi)\Delta x)_{t}]A}...(1)$$
Pada persamaan (1) di atas, *C~i~* menyatakan konsentrasi dari polimer, *A~i~* menyatakan jumlah polimer yang terakumulasi dalam batuan, dan $\rho_{gr}$ menyatakan densitas dari butiran batuan reservoir. Bagi persamaan (1) dengan faktor ($A\Delta x\Delta t$), diperoleh persamaan berikut.
$$-\frac{[(q_tf_wC_i)_x \Delta t - (q_tf_wC_i)_{x+\Delta x} \Delta t]A}{\Delta x} \\ = \frac{{[(C_iS_w)_{t+\Delta t}-(C_iS_w)_{t}}]\phi}{\Delta t} \\ + \frac{[(A_i\rho_{gr}(1-\phi)\Delta x)_{t+\Delta t}-(A_i\rho_{gr}(1-\phi)\Delta x)_{t}]}{\Delta t}...(2)$$
Dari definisi turunan dalam kalkulus, persamaan (2) dapat dituliskan sebagai berikut.
$$-\frac{q_t}{A\phi}\frac{\partial(f_wC_i)}{\partial x}= \frac{\partial(S_wC_i)}{\partial t}+\frac{1}{\phi}\frac{\partial[A_i\rho_{gr}(1-\phi)]}{\partial t}...(3)$$
Selanjutnya akumulasi polimer pada permukaan batuan reservoir per volume pori batuan reservoir dnyatakan dalam variabel $\hat C_i$ dimana
$$\hat C_i = \frac{A_i\rho_{gr}(1-\phi)}{\phi}...(4)$$
Substitusi persamaan (4) ke persamaan (3), diperoleh
$$-\frac{q_t}{A\phi}\frac{\partial(f_wC_i)}{\partial x}= \frac{\partial(S_wC_i)}{\partial t}+\frac{\partial \hat C_i}{\partial t}$$
$$\frac{\partial (S_wC_i)}{\partial t}+\frac{\partial \hat C_i}{\partial t}+\frac{q_t}{A\phi}\frac{\partial(f_wC_i)}{\partial x}=0...(5)$$
Lakukan ekspansi terhadap persamaan (5),
$$S_w \frac{\partial C_i}{\partial t}+C_i \frac{\partial S_w}{\partial t}+\frac{\partial \hat C_i}{\partial t}+\frac{q_t}{A\phi}f_w\frac{\partial C_i}{\partial x}+\frac{q_t}{A\phi} C_i\frac{\partial f_w}{\partial x}=0$$
$$S_w \frac{\partial C_i}{\partial t}+C_i \left( \frac{\partial S_w}{\partial t}+\frac{q_t}{A\phi} \frac{\partial f_w}{\partial x} \right)+\frac{\partial \hat C_i}{\partial t}+\frac{q_t}{A\phi}f_w\frac{\partial C_i}{\partial x}=0...(6)$$
Karena *S~w~* hanya merupakan fungsi dari posisi (*x*) dan *f~w~* hanya merupakan fungsi dari *S~w~*, maka:
$$C_i \left( \frac{\partial S_w}{\partial t}+\frac{q_t}{A\phi} \frac{\partial f_w}{\partial x} \right)=0$$
Sehingga persamaan (6) menjadi:
$$S_w \frac{\partial C_i}{\partial t}+\frac{\partial \hat C_i}{\partial t}+\frac{q_t}{A\phi}f_w\frac{\partial C_i}{\partial x}=0...(7)$$
Konsentrasi polimer yang terserap di batuan ($\hat C_i$) merupakan fungsi dari konsentrasi polimer dalam larutan ($\hat C_i$), sehingga
$$\hat C_i = f(C_i)$$
$$\frac{\partial \hat C_i}{\partial t} = \left( \frac{\partial \hat C_i}{\partial C_i} \right)\left( \frac{\partial C_i}{\partial t} \right)...(8)$$
Didefinisikan parameter adsorpsi polimer pada permukaan batuan (*D~i~*) sebagai:
$$D_i = \frac{\partial \hat C_i}{\partial C_i}$$
Maka, persamaan (8) menjadi:
$$\frac{\partial \hat C_i}{\partial t} = D_i\left( \frac{\partial C_i}{\partial t} \right)...(9)$$
Subtitusi persamaan (9) ke pesamaan (7),
$$S_w \frac{\partial C_i}{\partial t}+D_i \frac{\partial C_i}{\partial t}+\frac{q_tf_w}{A\phi}\frac{\partial C_i}{\partial x}=0$$
$$(S_w +D_i) \frac{\partial C_i}{\partial t}+\frac{q_tf_w}{A\phi}\frac{\partial C_i}{\partial x}=0$$
$$(S_w +D_i) \frac{\partial C_i}{\partial t}= -\frac{q_tf_w}{A\phi}\frac{\partial C_i}{\partial x}$$
$$\frac{\partial C_i}{\partial t}= -\left( \frac{q_t}{A\phi} \right)\frac{f_w}{(S_w +D_i)}\frac{\partial C_i}{\partial x} $$ 
Konsentrasi polimer dalam larutan merupakan fungsi dari posisi dan waktu sehingga
$$C_i = C_i(x,t)$$
$$dC_i= \left( \frac{\partial C_i}{\partial x}_t \right)dx + \left( \frac{\partial C_i}{\partial t}_x \right)dt$$
Tinjau suatu nilai konsentrasi polimer konstan dalam larutan
$$dC_i=0$$
$$\left( \frac{\partial C_i}{\partial x}_t \right)dx + \left( \frac{\partial C_i}{\partial t}_x \right)dt=0$$
$$\left( \frac{\partial C_i}{\partial x}_t \right)\frac{dx}{dt} + \left( \frac{\partial C_i}{\partial t}_x \right)=0$$
$$\frac{dx}{dt} = \frac{-\frac{\partial C_i}{\partial t}_x}{\frac{\partial C_i}{\partial x}_t}...(11)$$ 
Substitusi persamaan (10) ke persamaan (11),
$$\frac{dx}{dt} = \frac{-\frac{\partial C_i}{\partial t}_x}{\frac{\partial C_i}{\partial x}_t}=\frac{\left( \frac{q_t}{A\phi} \right)\frac{f_w}{(S_w +D_i)}\frac{\partial C_i}{\partial x}}{\frac{\partial C_i}{\partial x}_t}=\left( \frac{q_t}{A\phi} \right)\frac{f_w}{(S_w +D_i)}$$ 
$$\left( \frac{dx}{dt} \right)_{C_i} = \left( \frac{q_t}{A\phi} \right)\frac{f_w}{(S_w +D_i)}...(12)$$
Persamaan (12) merupakan persamaan _fractional flow_ yang memberikan kecepatan gerak _polymer bank front_ di reservoir. Persamaan (12) memiliki bentuk umum yang mirip dengan persamaan _fractional flow_ pada _waterflood_. Maka, kecepatan gerak _polymer bank front_ dapat pula dinyatakan sebagai berikut.
$$\left( \frac{dx}{dt} \right)_{C_i} = \left( \frac{q_t}{A\phi} \right)\frac{f_w}{(S_w +D_i)}=\left( \frac{q_t}{A\phi} \right) \left( \frac{\partial f_w^*}{\partial S_w^*} \right)_{S_w^*}...(13)$$
dimana
$$\left( \frac{\partial f_w^*}{\partial S_w^*} \right)_{S_w^*}=\frac{f_w}{(S_w +D_i)}=\frac{f_w^*}{(S_w^* +D_i)}...(14)$$
Parameter $\left( \frac{\partial f_w^*}{\partial S_w^*} \right)_{S_w^*}$ merupakan kemiringan kurva _fractional flow_ polimer, yaitu $f_w^*$ versus $S_w^*$ di titik $S_w^*$. Di sini sudah terlihat pengaruh adanya polimer dalam air injeksi, yaitu menyebabkan pergeseran kurva _fractional flow of water_ dari kurva $f_w$ versus $S_w$ menjadi kurva $f_w^*$ versus $S_w^*$.

Berdasarkan persamaan (13), profil saturasi air di reservoir pada kondisi _polymer flood_ memiliki bentuk yang berbeda dengan kondisi _waterflood_. Gambar berikut memperlihatkan profil saturasi air di reservoir selama periode _polymer flood_.

<div class="figure" style="text-align: center">
<img src="images/polymer/saturasipoly.png" alt="Profil saturasi air di reservoir di bawah kondisi _polymer flood_" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-3)Profil saturasi air di reservoir di bawah kondisi _polymer flood_</p>
</div>
<p> &nbsp; </p>

Seperti dapat dilihat pada gambar (2), terdapat dua _shock front_ dalam _polymer flood_. _Shock front_ pertama adalah _front_ dari _resident water_ (atau _connate water_) dengan nilai saturasi $S_{w2}$. Adapun _shock front_ kedua adalah _front_ dari _polymer_ _bank_ dengan nilai saturasi $S_{w3}^*$.

Secara grafik, nilai dari parameter ($\left( \frac{\partial f_w^*}{\partial S_w^*} \right)_{S_w^*}$) pada persamaan (13) dapat diketahui dengan menarik
garis lurus yang berpusat di (-*D~i~*, 0) yang menyinggung (*tangent*) dengan kurva _fractional flow_ untuk polimer, $f_{w}^* - S_{w}^*$. Titik potong garis ini dengan kurva _fractional flow water_, $f_{w} - S_{w}$ memberikan nilai saturasi dan fraksi aliran untuk _shock front_ pertama, (*S~w2~*, *f~w2~*). Gambar berikut memperlihatkan hal ini.

<div class="figure" style="text-align: center">
<img src="images/polymer/ffpoly.png" alt="Kurva _fractional flow_ untuk _polyer flood_" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-4)Kurva _fractional flow_ untuk _polyer flood_</p>
</div>
<p> &nbsp; </p>

Kecepatan *shock front* pertama (*resident water*, dilambangkan $v_2$) dan kecepatan *shock front kedua* (*polymer bank*, dilambangkan $v_3^*$) dinyatakan masing-masing oleh:
$$v_2 = \frac{q_t}{A\phi} \left( \frac{\partial f_w}{\partial S_w}\right)_{S_{w2}}=\frac{q_t}{A\phi} \left( \frac{f_{w2}-f_{wi}}{S_{w2}-S_{wi}}\right) = \left( \frac{f_{w2}}{S_{w2}-S_{wi}}\right)...(15)$$
$$v_3^* = \frac{q_t}{A\phi} \left( \frac{\partial f_w^*}{\partial S_w^*}\right)_{S_{w2}}=\frac{q_t}{A\phi} \left( \frac{f_{w3}^*-f_{w2}}{S_{w3}^*-S_{w2}}\right)...(16)$$
Di daerah *saturation discontinuity*, yaitu di daerah batas antara larutan polimer dengan *resident water* (daerah di sekitar titik *x~3~* pada gambar (2)), kecepatan dari larutan polimer akan sama dengan kecepatan dari *resident water* karena pada daerah ini, keduanya bercampur (*miscible*). Maka, dari persamaan (15) dan (16),
$$v_2=v_3^*$$
$$\frac{q_t}{A\phi}\left( \frac{f_{w2}}{S_{w2}-S_{wi}}\right) = \frac{q_t}{A\phi} \left( \frac{f_{w3}^*-f_{w2}}{S_{w3}^*-S_{w2}}\right)$$
$$\left( \frac{f_{w2}}{S_{w2}-S_{wi}}\right) = \left( \frac{f_{w3}^*-f_{w2}}{S_{w3}^*-S_{w2}}\right)$$
$$f_{w2}(S_{w3}^*-S_{w2}) = (S_{w2}-S_{wi})(f_{w3}^*-f_{w2})$$
$$f_{w2}=f_{w3}^* \left( \frac{S_{w2}-S_{wi}}{S_{w3}^*-S_{w2}} \right)...(17)$$
Lakukan substitusi persamaan (17) ke persamaan (14) dan (16), akan diperoleh:
$$\left( \frac{\partial f_w^*}{\partial S_w^*} \right)_{S_{w3}^*} = \frac{f_{w3}^*-f_{w2}}{S_{w3}^*-S_{w2}} = \frac{f_{w3}^*}{(S_{w3}^*+D_i)}=\frac{f_{w2}}{(S_{w2}+D_i)}...(18)$$
Sehingga, kecepatan dari _polymer bank front_, persamaan (16), dapat pula dinyatakan sebagai:
$$v_3^* = \frac{q_t}{A\phi} \left( \frac{\partial f_w^*}{\partial S_w^*}\right)_{S_{w3}^*}=\frac{q_t}{A\phi} \left( \frac{f_{w3}^*-f_{w2}}{S_{w3}^*-S_{w2}}\right) = \frac{q_t}{A\phi}\frac{f_{w3}^*}{(S_{w3}^*+D_i)}...(19)$$

### Penentuan Nilai Saturasi Air Rata-Rata di Reservoir Selama Periode Injeksi Polimer

Langkah selanjutnya adalah mencari informasi mengenai nilai saturasi air rata-rata di reservoir selama periode injeksi polimer. Penurunan persamaan umum yang digunakan untuk mengetahui nilai saturasi air rata-rata di reservoir selama periode _polymer flood_ adalah sebagai berikut. Berdasarkan gambar (2),
$$\bar S_w = \frac{\int_0^{x_3}S_w^*dx + \int_{x_3}^{x_2}S_{w2}^*dx + \int_{x_2}^{L}S_{wi}^*dx}{L}...(20)$$
$$\bar S_w = \bar S_w^* \frac{x_3}{L} + \frac{(x_{2}-x_3)}{L}S_{w2} + \frac{(L-x_{2})}{L}S_{wi}...(21)$$
Dari persamaan nilai saturasi air rata-rata yang dibahas di bagian _waterflood predictive model_,
$$\bar S_w = \frac{x_{II}S_{II}-x_{I}S_{I}}{x_{II}-x_{I}}- \left( \frac{q_tt}{A\phi}\right)\left( \frac{f_{wII}-f_{I}}{x_{II}-x_{I}} \right)$$
$$\bar S_w^* = \frac{LS_{w3}^*}{L} - \left( \frac{q_tt}{A\phi}\right)\left( \frac{f_{w3}^*-1}{L} \right)$$
$$\bar S_w^* = \bar S_{w3}^* - \left( \frac{q_tt}{A\phi}\right)\left( {f_{wII}-f_{I}} \right)...(22)$$
Maka, nilai saturasi air rata-rata selama periode _polymer flood_ ditentukan dengan persamaan (21) dengan nilai $\bar S_{w3}^*$ ditentukan oleh persamaan (22). Penentuan nilai-nilai $f_{w2}, S_{w2}, f_{w3}^*,$ dan $S_{w3}^*$ secara numerik dilakukan dengan cara yang sama seperti yang dijelaskan pada _technical report waterflood_.

### Rangkuman Persamaan-Persamaan yang Digunakan Dalam Teori _Fractional Flow_

Persamaan-persamaan yang digunakan dalam _polymer flood predictive model_ yang berkaitan dengan teori _fractional flow_ dirangkum pada tabel berikut. Simbol yang digunakan pada tabel mengacu pada gambar (2) dan (3).

|Parameter    |*Shock Front I* </br> (*Resident Water Bank*)       |*Shock Front II* </br> (*Polymer Bank*)       |
|:---:        |:---:                                               |:---:                                         |
|Kecepatan    |$$v_2 = \left( \frac{dx}{dt} \right)_{S_{w2}} = \frac{q_t}{A\phi} \left( \frac{\partial f_w}{\partial S_w} \right)_{S_{w2}}$$ $$\left( \frac{dx}{dt} \right)_{S_{w2}} = \frac{q_t}{A\phi} \left( \frac{f_{w2}-f_{wi}}{S_{w2}-S_{wi}} \right)$$ $$\left( \frac{dx}{dt} \right)_{S_{w2}} = \frac{q_t}{A\phi} \left( \frac{f_{w2}}{S_{w2}-S_{wi}} \right)$$ |$$v_3^* = \left( \frac{dx}{dt} \right)_{S_{w3}^*} = \frac{q_t}{A\phi} \left( \frac{\partial f_w}{\partial S_w} \right)_{S_{w3}^*}$$ $$\left( \frac{dx}{dt} \right)_{S_{w3}^*} = \frac{q_t}{A\phi} \left( \frac{f_{w3}^*}{S_{w2}+D_{i}} \right)$$ $$\left( \frac{dx}{dt} \right)_{S_{w3}^*} = \frac{q_t}{A\phi} \left( \frac{f_{w2}}{S_{w2}+D_i} \right)$$|
|Posisi|$$x_2 = \frac{q_tt}{A\phi}\left( \frac{\partial f_w}{\partial S_w} \right)_{S_{w2}}$$ $$x_2 = \frac{q_tt}{A\phi} \left( \frac{f_{w2}}{S_{w2}-S_{wi}} \right)$$|$$x_3 = \frac{q_tt}{A\phi} \left( \frac{\partial f_w}{\partial S_w} \right)_{S_{w3}^*}$$ $$x_3 = \frac{q_tt}{A\phi} \left( \frac{f_{w3}^*}{S_{w2}+D_{i}} \right)$$ atau $$x_3 = \frac{q_tt}{A\phi} \left( \frac{f_{w2}}{S_{w2}+D_{i}} \right) $$|

Table: <span style="color: grey;"> Tabel 5.1: Persamaan-persamaan _fractional flow_ yang digunakan dalam _polymer flood predictive model_ </span>

|Parameter                    |Nilai        |
|:---:                        |:---:        |
|*Pore volume* (PV) injeksi air, $Q_i$|$$Q_{i2}=\frac{1}{\left( \frac{\partial f_w}{\partial S_w} \right)_{S_{w2}}}= \bar S_w - S_{wi}$$ $$Q_{i3}=\frac{1}{\left( \frac{\partial f_w^*}{\partial S_w^*} \right)_{S_{w3}^*}}=\frac{(S_{w3}^*+D_i)}{f_{w3}^*}$$ $$\bar S_w =x_3\bar S_{w3}^*+(1-x_3)_{S_{w2}}$$|
|*Displacement efficiency*, $E_D$|$$E_{D2}= \frac{\bar S_w-S_{wi}}{1-S_{wi}}$$ $$E_{D3}= \frac{\bar S_w^*-S_{wi}}{1-S_{wi}}$$ $$\bar S_w =x_3\bar S_{w3}^*+(1-x_3){S_{w2}}$$ $$\bar S_w^* =\bar S_{w2}^*+\left( \frac{q_tt}{A\phi L} \right)(1-f_{w2}^*)$$|

Table: <span style="color: grey;"> Tabel 5.2: Persamaan untuk menghitung _pore volume_ injeksi air dan _displacement efficiency_ </span>

## Metode Perhitungan _Areal_ dan _Vertical Sweep Efficiency_ Menggunakan Pendekatan _Streamtube_

_Predictive model_ menggunakan pendekatan _streamtube_ untuk menghitung _areal_ dan _vertical sweep efficiency_. Setiap lapisan reservoir dibagi ke dalam beberapa _streamtube_ (satu, empat, sampai maksimum delapan _streamtube_) yang menghubungkan sumur injeksi dengan sumur produksi. Model perpindahan 1D dihitung di setiap _streamtube_ menggunakan teori _fractional flow_ seperti yang telah dibahas sebelumnya. _Areal_ dan _vertical sweep efficiency_ diperoleh dengan menggabungkan hasil perhitungan setiap _streamtube_ di setiap lapisan reservoir. Asumsi yang digunakan diantaranya adalah ukuran _streamtube_ ditentukan konstan, dan tidak terjadi _crossflow_ antar _streamtube_ di setiap lapisan reservoir.

<div class="figure" style="text-align: center">
<img src="images/polymer/streamtube.png" alt="Model _streamtube_" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-5)Model _streamtube_</p>
</div>
<p> &nbsp; </p>

Perhitungan _areal sweep efficiency_ (*E~A~*) di setiap *streamtube* dibagi ke dalam empat periode, yaitu:

1. Periode sebelum _resident water breakthrough_:
$$(E_A)_1= \frac{W_I}{(PV)(\bar S_{BT}-S_{wi})}...(23)$$
2. Periode saat _resident water breakthrough_:
$$(E_{ABT})_2 = 0.54602036=\frac{0.03170817}{M_2}+\frac{0.30222997}{e^{M_2}}-0.0050969M_2...(24)$$
3. Periode saat _polymer bank breakthrough_:
$$(E_{ABT})_3 = (E_{ABT})_2+0.54602036=\frac{0.03170817}{M_2}+\frac{0.30222997}{e^{M_2}}-0.0050969M_2...(25)$$
4. Periode setelah _polymer bank breakthrough_:
$$(E_{ABT})_4 = (E_{ABT})_3 + 0.633\log \left( \frac{W_i}{(W_{iBT})_3} \right)...(26)$$

Perhitungan _vertical sweep efficiency_ (*E~V~*) di setiap _streamtube_ dinyatakan dalam korelasi yang merupakan fungsi dari koefisien variasi permeabilitas Dykstra-Parsons (*V~DP~*), _mobility ratio M_, dan _water-oil ratio_ (WOR). Korelasi ini dinyatakan dalam bentuk parameter korelasi _Y_ yang dinyatakan sebagai:
$$Y = \frac{(WOR+0.4)(18.948-2.499V_{DP})}{(M - 0.8094V_{DP}+1.137)10^x}...(27)$$
dimana:
$$x=1.6453V_{DP}^2+0.935V_{DP}-0.6891...(28)$$
Nilai *E~V~* dihitung menggunakan metode iterasi melalui persamaan berikut:
$$a_1E_V^{a_2}(1-E_V)^{a_3}-Y = 0...(29)$$
Pada persamaan (29), nilai Y diperoleh dari persamaan (27), sedangkan nilai dari parameter – parameter *a~1~*, *a~2~*, dan *a~3~* berturut-turut adalah 3.334088568, 0.7737348199, dan 1.225859406.

Tabel berikut merangkum persamaan-persamaan yang digunakan dalam perhitungan di setiap _streamtube_.

|Parameter                    |Nilai        |
|:---:                        |:---:        |
|*Pore volume* (PV) injeksi air, $Q_i$|$$Q_{i2}=\frac{1}{\left( \frac{\partial f_w}{\partial S_w} \right)_{S_{w2}}}= \bar S_w - S_{wi}$$ $$Q_{i3}=\frac{1}{\left( \frac{\partial f_w^*}{\partial S_w^*} \right)_{S_{w3}^*}}=\frac{(S_{w3}^*+D_i)}{f_{w3}^*}$$ $$\bar S_w =x_3\bar S_{w3}^*+(1-x_3)_{S_{w2}}$$|
|*Displacement efficiency*, $E_D$|$$E_{D2}= \frac{\bar S_w-S_{wi}}{1-S_{wi}}$$ $$E_{D3}= \frac{\bar S_w^*-S_{wi}}{1-S_{wi}}$$ $$\bar S_w =x_3\bar S_{w3}^*+(1-x_3){S_{w2}}$$ $$\bar S_w^* =\bar S_{w2}^*+\left( \frac{q_tt}{A\phi L} \right)(1-f_{w2}^*)$$|
|Volume injeksi kumulaif, $W_i$|$$W_{i2}=(PV)Q_{i2}E_AE_V$$ $$W_{i3}=(PV)Q_{i3}E_AE_V$$|
|Waktu _breakthrough_ untuk _bank_ ke-*j*, $t_j$|$$t_2 = \frac{S_{w2}-S_{wi}}{f_{w2}}$$ $$t_2 = \frac{S_{w3}^*+D_i}{f_{w3}^*}$$|
|Koefisien variasi permeabilitas Dykstra-Parsons, $V_{DP}$|$$V_{DP} = \frac{k_{50}-k_{84.1}}{k_{50}}$$|
|Kumuatif produksi minyak, $N_p$|$$N_p = N_sE_DE_AE_V$$|

Table: <span style="color: grey;"> Tabel 5.3: Rangkuman persamaan yang digunakan dalam erhitungan di setiap _streamtube_ </span>

## Perhitungan _Injectivity_

*Predictive model* menggunakan nilai konstan untuk beda tekanan ($\Delta P$) antara sumur injeksi dengan sumur produksi (*constant pressure drop*), sehingga nilai *injectivity* akan berubah-ubah setiap waktu. Dengan asumsi saturasi awal terdistribusi merata di setiap lapisan reservoir, nilai laju injeksi awal (*initial injection rate*, bbl/day) untuk setiap lapisan reservoir (J) dapat dihitung menggunakan persamaan Muskat sebagai berikut.
$$Q_i = \frac{0.003541.CP.depth.k(J).h_{pay}(J).M(1,J)}{-0.619+log \left( \frac{DIPS}{r_w} \right)}...(30)$$
dengan: </br>
$$CP = \frac{\Delta P}{depth}...(31)$$ 
$$M(1,J) = \frac{X_{k_{ro}}(1)}{\mu_o}+\frac{X_{k_{rw}}(1)}{\mu_w}...(32)$$
$$DIPS = [(2)(43560)(A_{pat})]^{\frac{0.5}{2}}...(33)$$
dimana: </br>
$M(1,J)$ = total mobilitas relatif awal untuk _bank_ ke-1 </br>
$CP$ = koefisien _injectivity_, psi/ft</br>
$A_{pat}$ = _pattern area_</br>
$k(J)$ = permeabilitas dari lapisan J</br>
$h_{pay}(J)$ = _net pay_ dari lapisan J

Laju injeksi awal akan bernilai sama di setiap _streamtube_ yang berada pada lapisan reservoir yang sama. Nilai laju injeksi awal di setiap _streamtube_ dinyatakan oleh persamaan berikut.
$$Q_{i,st}(I,J)= \frac{Q_i}{N_{stub}}...(34)$$
dimana: </br>
$N_{stub}$ = jumlah _streamtube_ di setiap lapisan reservoir.

Ketika injeksi polimer dilakukan, nilai laju injeksi di setiap _streamtube_ akan berubah-ubah karena setiap _streamtube_ memiliki konduktivitas fluida yang berbeda-beda. Konduktivitas fluida dinyatakan oleh parameter mobilitas fluida di setiap _streamtube_. Perbedaan mobilitas fluida di setiap streamtube menyebabkan perbedaan laju injeksi di setiap _streamtube_. Maka, laju injeksi untuk setiap _streamtube_ dinyatakan oleh:
$$Q_{st}(I,J) = \frac{N_{block}Q_{st}^{old}(I,J)}{M(I,J).C_{st}(I,J)}...(35)$$
dimana: </br>
$Q_{st}^{old}(I,J)$ = nilai laju injeksi pada _timestep_ sebelumnya </br>
$C_{st}(I,J)$ = nilai konduktansi di _streamtube_ untuk _bank_ ke-*I* dan lapisan ke-*J*.

Laju injeksi total (*Newtonian*) diperoleh dengan menjumlahkan nilai laju injeksi di setiap *streamtube*, kemudian menjumlahkannya kembali untuk seluruh lapisan reservoir. Aliran *non-Newtonian* akan terjadi di daerah sekitar sumur karena tingginya kecepatan alir di daerah ini. Hal ini menyebabkan terjadinya *polymer shear degradation*. Efek aliran *non-Newtonian* di daerah sekitar sumur injeksi terhadap laju injeksi akan disertakan dalam model dalam bentuk parameter *skin factor negatif*.

## Penentuan Nilai Permeabilitas di Setiap Lapisan Reservoir

Nilai permeabilitas di setiap lapisan reservoir ditentukan dengan menggunakan konsep koefisien Lorenz dan plot antara parameter _flow capacity_ (kh) dan _storage capacity_ ($\phi h$).

## Koreksi Terhadap Pengaruh _Slug_ Polimer

Pada analisis _fractional flow_, perhitungan dilakukan dengan asumsi injeksi polimer dilakukan secara kontinu. Bagaimanapun, penerapan injeksi polimer di lapangan tidak dilakukan secara kontinu, melainkan menggunakan ukuran _slug_ tertentu. Ukuran polimer _slug_ yang digunakan sangat mempengaruhi performa dari _polymer flood_ dan keekonomian proyek.

Dalam _predictive model_, efek ukuran _slug_ polimer dinyatakan sebagai faktor koreksi _slug_ polimer, C~PB~. Faktor koreksi _slug_ polimer ini diperoleh dari hasil studi simulasi.
$$C_{PB} = \frac{(4.5+ \sqrt {M_{CP}})V_{i,pol,eff}}{1+5.V_{i,pol,eff}} ...(36)$$
dengan:
$$M_{CP} = \frac{\mu_p}{\mu_w}...(37)$$
$$V_{i,pol,eff} = V_{i,pol}-0.5D_i...(38)$$
dimana: </br>
$V_{i,pol,eff}$ = _pore volume_ injeksi _slug_ polimer efektif </br>
$V_{i,pol}$ = _pore volume_ injeksi _slug_ polimer </br>
$\mu_p$ = viskositas larutan polimer </br>
$D_i$ = adsorpsi polimer pada lapisan batuan reservoir 

Perolehan minyak (*oil recovery*) akan menurun dengan menurunnya nilai C~PB~. Semakin kecil *pore volume* injeksi _slug_ polimer, semakin kecil pula perolehan minyak.

## Pengaruh Sifat Fisis Larutan Polimer Terhadap Performa Injeksi Polimer

Secara umum, beberapa sifat fisis larutan polimer yang mempengaruhi performa injeksi polimer adalah salinitas air formasi, *inaccessible pore volume*, sifat *non-Newtonian*, adsorpsi polimer ke dalam lapisan batuan reservoir, dan pengurangan permeabilitas terhadap fasa *aqueous*. Namun, tidak semua faktor ini disertakan dalam *predictive model*. Beberapa asumsi terkait sifat fisis polimer yang digunakan dalam *predictive model* diantaranya adalah:

a. Faktor _inaccessible pore volume_ diabaikan karena efeknya terhadap _injectivity_ dan perolehan minyak dianggap tidak signifikan.
b. _Shear rate_ dan salinitas air formasi diasumsikan konstan selama periode _polymer flood_.
c. Perhitungan _oil recovery_ menggunakan nilai tunggal untuk parameter viskositas polimer dan adsorpsi polimer.
d. Adsorpsi polimer tidak dipengaruhi oleh konsentrasi polimer.

Dua sifat fisis polimer yang dianggap paling penting dalam *predictive model* adalah efek pengurangan permeabilitas terhadap fasa *aqueous* (*permeability reduction to aqueous phase*) dan sifat aliran *non-Newtonian* di daerah sekitar sumur injeksi. Berikut akan dilakukan pembahasan mengenai masing-masing sifat polimer ini.

### Efek Pengurangan Permeabilitas Untuk Fasa _Aqueous_

Larutan polimer mengurangi mobilitas dari fasa *aqueous* melalui dua mekanisme, yaitu dengan meningkatkan viskositas fasa *aqueous* dan dengan mengurangi permeabilitas terhadap fasa *aqueous*. Faktor berkurangnya permeabilitas terhadap fasa *aqueous* dinyatakan dalam bentuk parameter residual *resistance factor* (RRF).
$$RRF = \frac{M_{w,bc}}{M_{w,ac}}...(39)$$
dimana: </br>
$M_{w,bc}$ = mobilitas air sebelum kontak dengan formasi batuan yang mengandung polimer. </br>
$M_{w,ac}$ = mobilitas air setelah kontak dengan formasi batuan yang mengandung polimer

Faktor berkurangnya permeabilitas terhadap fasa aqueous dapat dinyatakan ekivalen dengan peningkatan viskositas larutan polimer.
$$\mu_{p,app} = (\mu_p)(RRF)...(40)$$
dimana: </br>
$\mu_{p,app}$ = viskositas _apparent_ polimer

Selanjutnya, karena faktor berkurangnya permeabilitas terhadap fasa _aqueous_ dianggap bersifat _irreversible_, maka _chase water bank_ yang berada di belakang _polymer bank_ juga akan mengalami peningkatan viskositas yang dinyatakan oleh persamaan berikut.
$$\mu_{w,app} = (\mu_w)(RRF)...(41)$$
Peningkatan viskositas _chase water_ akan mengurangi mobilitas _chase water_. Mobilitas chase water dinyatakan oleh:
$$M(4,J) = \frac{X_{k_{ro}}}{\mu_o} + \frac{X_{k_{rw}}}{\mu_{w,app}}...(42)$$
Nilai mobilitas _chase water_ yang dinyatakan oleh persamaan (42) selanjutnya akan dikalikan dengan faktor pengali 0.8.

Viskositas polimer _apparent_, yang dinyatakan oleh persamaan (40), dapat pula dinyatakan dalam bentuk _resistance factor_, RF, sebagai berikut.
$$\mu_{p,app} = (\mu_w)(RF)...(43)$$
$$RF = \frac{M_{w,bc}}{M_{pol}}...(44)$$
dimana: </br>
$M_{pol}$ = mobilitas larutan polimer 

Adapun nilai _default_ untuk viskositas polimer, $\mu_p$, dinyatakan oleh persamaan berikut.
$$\mu_p = \mu_w \left( \frac{RF}{RRF} \right)...(45)$$

### Efek Aliran _Non-Newtonian_ Larutan Polimer di Daerah Sekitar Sumur Injeksi

Pada _predictive model_ yang dibangun, aliran non-Newtonian dari larutan polimer dianggap hanya terjadi di daerah sekitar sumur injeksi dan hanya mempengaruhi nilai _injectivity._ Akibat terjadinya aliran _non-Newtonian_ di daerah sekitar sumur injeksi, nilai viskositas polimer di daerah ini menjadi lebih kecil dibandingkan dengan viskositas polimer yang diprediksi oleh persamaan (45), yang mengasumsikan kondisi aliran _Newtonian_. Hal ini akan menyebabkan peningkatan nilai _injectivity_. Efek peningkatan _injectivity_ dinyatakan dalam bentuk parameter _skin factor_ negatif.

Sifat _pseudo-plastic_ dari larutan polimer dimodelkan oleh modifikasi persamaan Blake-Kozeny dimana viskositas polimer _apparent_ dinyatakan sebagai fungsi dari kecepatan Darcy, $u$.
$$\mu_{p,app} = H(J).u.(XNPL-1)...(46)$$
dengan:
$$H(J) = \frac{XKPL}{12Y_1Y_2}...(47)$$
$$Y_1 = [9.86.10^{-12}.150.k(J).X_{k_[rwe]}.\phi (J).(1-S_{orw})]^{0.5(1-XNPL)}...(48)$$
$$Y_2 = \left( 9.XNPL = \frac{3}{XNPL} \right)^{XNPL}...(49)$$
dimana: </br>
$H(J)$ = koefisien Blake-Kozeny untuk lapisan reservoir _J_ </br>
$XNPL$ = eksponen _power law_ </br>
$XKPL$ = koefisien _power law_ 

Dengan mendefinisikan _dimensionless viscosity_ sebagai:
$$\mu_D = \frac{H(J)}{\mu_{p,app} \left[ 3170.r_w\frac{h_{pay}(J)}{Q_{st,NN}} \right]^{1-XNPL}}...(50)$$
dimana: </brs>
$Q_{st,NN}$ = laju injeksi _non-Newtonian_

Maka, parameter yang menyatakan sifat _non-Newtonian_, yaitu _pseudo skin factor_ dapat dinyatakan sebagai berikut. </br>
Untuk $\mu_D \leq XV$,
$$S_p = \frac{1}{(1-XNPL)(\log (XV^{XV}\mu_D^{1-XV})-XV+1)}...(51) $$
Untuk $\mu_D > XV$,
$$S_p = \frac{1}{(1-XNPL)(\log (\mu_D)-\mu_D+1)}...(52) $$
dengan
$$XV = \frac{\mu_w}{\mu_{p,app}}...(53)$$

Hubungan antara laju injeksi _Newtonian_ dengan laju injeksi _non-Newtonian_ dinyatakan oleh persamaan berikut.
$$\frac{Q_{st,NN}}{Q_{st}(I,J)} = \frac{\log \left( \frac{DIPS}{r_w} \right) - 0.619}{\log \left( \frac{DIPS}{r_w} \right) - 0.619+0.5S_p}...(54)$$

## Persamaan-Persamaan Dasar yang Digunakan Dalam _Predictive Model_

### Viskositas Minyak

Viskositas minyak, $\mu_o$, dihitung menggunakan korelasi Beggs-Robinson. Korelasi terlebih dahulu menghitung nilai viskositas _dead oil_, $\mu_{od}$.
$$\mu_{od} = 10^x -1...(55)$$
$$x = \frac{y}{T^{1.163}}$$
$$y = 10^z$$
$$z = 3.0324 - 0..02023(API)$$
dimana: </br>
_T_ = temperatur reservoir, $^\circ$F (*default*: *T* = 60 + 0.017*depth*)

Selanjutnya, viskositas _live oil_ dihitung menggunakan persamaan berikut.
$$\mu_o = A (\mu_{od})^B...(56)$$
dengan
$$A= \frac{10.715}{(R_s+100)^{0.515}}$$
$$B= \frac{5.44}{(R_s+150)^{0.338}}$$
dimana:
$R_s$ = _solution gas-oil ratio_

### _Solution Gas-Oil Ratio_

_Solution gas-oil ratio_ (*R~s~*) dihitung menggunakan korelasi Vasquez-Beggs. Dalam korelasi Vasquez-Beggs, nilai _specific gas gravity_, $\gamma_g$, terlebih dahulu dikoreksi ke dalam kondisi tekanan separator 100 psig dan temperatur separator (temperatur separator diasumsikan sama dengan temperatur reservoir).
$$\gamma_{g.100} = \gamma_g \left[ 1+\left(5.912(10^{-5})(API)(T)\log \left( \frac{64.7}{114.7} \right) \right) \right]...(57)$$
dimana:</br>
$\gamma_{g.100}$ = _specific gravity gas_ pada kondisi separator (interval nilai: 0.8 ≤ $\gamma_{g.100}$ ≤ 1.4). </br>
$\gamma_g$ = _specific gravity gas_ pada kondisi reservoir (*default*: $\gamma_g$ = 0.8).

Selanjutnya, _solution gas-oil ratio_ dihitung sebagai berikut: </br>
Untuk $API \leq$ 30:
$$R_s = 0.0362 \gamma_{g.100}P_{form}^{1.0937}exp \left[ 25.724 \left( \frac{API}{T+460} \right) \right]...(58)$$
Untuk $API$ > 30:
$$R_s = 0.0178 \gamma_{g.100}P_{form}^{1.187}exp \left[ 23.931 \left( \frac{API}{T+460} \right) \right]...(59)$$
dimana:
$P_{form} = 15+0.433(depth)$ = tekanan formasi, psia.

### Faktor Volume Formasi Minyak

Faktor volume formasi minyak, *B~o~*, dihitung menggunakan korelasi Vasquez-Beggs.
$$B_o = 1 + C_1R-s + (C_2 + C_3R_s)(T-60) \left( \frac{API}{\gamma_{g.100}} \right)...(61)$$
dimana: </br>
Untuk $API \leq$ 30:
$$C_1 = 4.677 (10^{-4})$$
$$C_2 = 1.751 (10^{-5})$$
$$C_3 = -1.811 (10^{-8})$$
Untuk $API$ > 30:
$$C_1 = 4.67 (10^{-4})$$
$$C_2 = 1.1 (10^{-5})$$
$$C_3 = 1.337 (10^{-9})$$

### Faktor Volume Formasi Air

Faktor volume formasi minyak, *B~w~*, dihitung menggunakan korelasi Keenan & Keyes.
$$B_w = 1 + 1.2(10^{-4})(T-60) + 1(10^{-6})(T-60)^{2}-3.33(10^{-6})P_{form}...(61)$$

### Permeabilitas Relatf dan Fraksi Aliran Air

Nilai permeabilitas relatif minyak (*k~ro~*) dan air (*k~rw~*), _fractional flow of water_ (*f~w~*), dan turunannya $\left( \frac{\partial f_w}{\partial S_w} \right)$ dihitung menggunakan korelasi Corey.
$$u_o = \frac{S_{w}-S_{orw}}{1-S_{wc}-S_{orw}}...(62)$$
$$k_{ro}=X_{k_{roe}}u_o^{X_{no}}...(63)$$
$$u_w = \frac{S_{w}-S_{wc}}{1-S_{wc}-S_{orw}}...(64)$$
$$k_{rw}=X_{k_{rwe}}u_w^{X_{nw}}...(65)$$
Nilai fraksi aliran air dan turunannya dihitung menggunakan persamaan berikut:
$$f_w = \frac{1}{M_{wo}}...(66)$$
$$\left( \frac{\partial f_w}{\partial S_w} \right) = f_w^2 \frac{\left( \frac{\mu_w}{\mu_o} \right)}{\left( \frac{k_{rw}}{k_{rw}UKR} \right)}...(67)$$
dengan:
$$M_{wo} = \frac{k_{ro}}{k_{rw}}\left( \frac{\mu_w}{\mu_o} \right)...(68)$$
$$UKR = (k_{ro}D_{k_{rw}})-(k_{rw}D_{k_{ro}})...(69)$$
$$D_{k_{rw}}= \frac{X_{nw}{k_{rw}}}{S_w - S_{wc}}...(70)$$
$$D_{k_{ro}}= \frac{-X_{no}{k_{ro}}}{1-S_w - S_{orw}}...(71)$$

### Persamaan-Persamaan Dasar dan Nilai _Default_ yang Digunakan

Tabel berikut merangkum persamaan dan nilai _default_ yang digunakan dari sejumlah parameter dalam _predictive model_.

|Parameter   |Nilai _Default_ yang Digunakan   |
|:---:    |:---:    |
|Konsentrasi polimeri, $C_{poly}$   |$C_{poly}$ berada pada interval 600-1000 ppm   |
|Adsorpsi polimer, $D_i$   |$D_i$ = 150 lbs/ac.ft   |
|Injeksi *slug* polimer, $V_{i,pol}$   |Nilai _default_ = nilai maksimum = 3 PV   |
|Koefisien variasi permeabilitas Dystra-Parsons, $V_{DP}$   |$V_{DP}=0.72$   |
|Jumlah lapisan reservoir   |Minimum = 1 </br> Maksimum = 10   |
|Koefisien _power law_, $XKPL$    |$XKPL = \mu_wRF$ |
|Eksponen _power law_, $XNPL$     |$$XNPL =0.6$$ 0.0001 < $XNPL$ < 0.999    |
|Viskositas air, $\mu_w$   |Korelasi Van Wingen: </br> $\mu_w = exp[1.003-1.479(10^{-2})T+1.982(10^{-5})T^2]$   |
|*Connate water saturation*, $S_{wc}$   |$S_{wc}=0.3$   |
|Saturasi minyak residu, $S_{orw}$  |Untuk tipe batuan _sandstone_, $S_{orw}=0.25$ </br> Untuk tipe batuan karbonat, $S_{orw}=0.38$   |
|Permeabilitas relatif minyak saat $S_{wc}$, $X_{k_{roe}}$   |Untuk tipe batuan _sandstone_, $X_{k_{roe}}=0.8$ </br> Untuk tipe batuan karbonat, $X_{k_{roe}}=0.4$   |
|Permeabilitas relatif air saat $S_{orw}$, $X_{k_{rwe}}$   |Untuk tipe batuan _sandstone_, $X_{k_{rwe}}=0.2$ </br> Untuk tipe batuan karbonat, $X_{k_{rwe}}=0.3$  |
|Eksponen kurva permeabilitas relatif minyak, $X_{no}$|$X_{no}=2$|
|Eksponen kurva permeabilitas relatif air, $X_{nw}$|$X_{nw}=2$|
|Radius sumur, $r_w$|$r_w=0.5ft$|
|Koefisien _injectivity_, $CP$|Untuk _depth_ $\leq$ 3000: </br> $CP=\frac{200+0.433(depth)}{depth}$ </br> Untuk _depth_ > 3000: </br> $CP = \frac{[200+(0.433)(3000)]+[0.003(depth-3000)]}{depth}$ </br> Interval nilai $CP$: 0.27 < $CP$ < 0.7|

Table: <span style="color: grey;"> Tabel 5.4: Nilai _default_ yang digunakan dari sejumlah parameter dalam _predictive model_ </span>




