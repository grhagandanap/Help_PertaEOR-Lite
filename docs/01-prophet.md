# CO~2~ Prophet Predictive Model



## Pendahuluan

__CO~2~ Prophet__ merupakan perangkat lunak yang dibangun oleh __U.S. Department of Energy (DOE)__ yang dapat digunakan untuk memprediksi performa CO2 _flooding_. Perangkat lunak ini memiliki keunggulan dibandingkan dengan CO2 Miscible Predictive Model (CO2PM), yang juga dibangun oleh U.S. DOE.

Berbeda dengan CO~2~ _predictive model_ yang hanya memberikan satu pilihan pola injeksi (yaitu 5-spot), CO~2~ Prophet memberikan opsi kepada _user_ untuk memilih antara enam pola injeksi. Pilihan pola injeksi yang tersedia diantaranya adalah 5-_spot_, West Texas 7-_spot_, _Inverted_ 9-_spot_, _Line Drive_, 4-_spot_, dan _Isolated_ 2-_spot_. Gambar berikut memperlihatkan pilihan pola injeksi yang tersedia bagi _user_.

<div class="figure" style="text-align: center">
<img src="images/co2prophet/patternCO2.png" alt="Beberapa pilihan pola injeksi dalam CO~2~ Prophet" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-2)Beberapa pilihan pola injeksi dalam CO~2~ Prophet</p>
</div>

Selain untuk memprediksi performa _miscible_ CO~2~ _flooding_, CO~2~ Prophet juga dapat digunakan untuk memprediksi performa _waterflood_, _miscible_ CO~2~, _WAG_, dan _immiscible_ CO~2~ _flood._
<p> &nbsp; </p>

## Asumsi yang Digunakan Dalam Model

Beberapa asumsi yang digunakan dalam CO~2~ Prophet diantaranya adalah: 

1. Terdapat tiga fasa fluida yang disertakan dalam model, yaitu fasa minyak, fasa air, dan fasa _solvent._
2. User dapat memilih hingga 10 _layer_ untuk digunakan dalam perhitungan. Nilai _default_ untuk jumlah _layer_ adalah 5 _layer._
3. Efek gravitasi diabaikan.
4. Beberapa parameter reservoir dan fluida yang berperan penting dalam model diantaranya adalah koefisien permeabilitas Dykstra-Parsons, viskositas minyak, viskositas air, temperatur reservoir, tekanan rata-rata reservoir, dan _minimum miscibility pressure_ (MMP).
<p> &nbsp; </p>

## Parameter-Parameter Penting yang Digunakan Dalam Model

### Koefisien Permeabilitas Dykstra-Parsons

Koefisien permeabilitas Dykstra-Parsons (V~*dp*~) menyatakan besarnya keheterogenan permeabilitas reservoir secara vertikal. Nilai V~*dp*~ menentukan besarnya _injectivity_ fluida di setiap lapisan reservoir. Nilai _default_ yang digunakan adalah 0.7.

### Temperatur Reservoir

Dalam model, temperatur reservoir digunakan untuk menghitung viskositas CO~2~ di dalam reservoir. Nilai _default_ yang digunakan adalah 100$^\circ$F. 

### Tekanan Rata-Rata Reservoir (_Average Reservoir Pressure_)

Nilai tekanan rata-rata reservoir menentukan kondisi aliran di reservoir. Kondisi aliran dapat berupa _completely miscible flood_, _partially miscible flood_, atau _totally miscible flood_. Nilai _default_ yang digunakan dalam model adalah 2000 psia.

### _Minimum Miscibility Pressure (MMP)_

Sama seperti nilai tekanan rata-rata reservoir, nilai MMP menentukan kondisi aliran yang akan terjadi di reservoir. Jika _user_ menginginkan kondisi _completely miscible_ CO~2~, maka nilai MMP harus berada di bawah nilai tekanan rata-rata reservoir. Nilai default MMP yang digunakan dalam model adalah 1200 psia.

### Viskositas Minyak ($\mu_o$)

Dalam model, viskositas minyak digunakan untuk melakukan perhitungan mobilitas fluida. Nilai _default_ $\mu_o$ yang digunakan dalam model adalah 2 cp.

### Viskositas Air ($\mu_w$)

Dalam model, viskositas minyak digunakan untuk melakukan perhitungan mobilitas fluida. Nilai _default_ $\mu_w$ yang digunakan dalam model adalah 0.8 cp.

### Faktor Volume Formasi Minyak (B~*o*~)

Faktor volume formasi minyak menyatakan perbandingan antara volume fluida di reservoir dengan volume fluida di permukaan. Nilai default yang digunakan dalam model adalah 1.4 bbl/STB.

### _Solution Gas-Oil Ratio_ (R~*s*~)

Nilai kelarutan gas digunakan untuk menghitung jumlah gas hidrokarbon yang terproduksikan. Nilai _defaut_ yang digunakan dalam model adalah 500 scf/STB.

### Permeabilitas Relatif (k~*r*~)

Dalam model, nilai permeabilitas relatif air (k~*rw*~), permeabilitas relatif minyak (k~*ro*~), permeabilitas relatif gas (k~*rg*~), dan permeabilitas relatif solvent (k~*rs*~) dihitung menggunakan persamaan-persamaan berikut:
$$k_{rw}\ = k_{rw}@S_{or} \left( \frac{S_w-S_{wirr}}{1-S_{wirr}-S_{orw}} \right)^{expw} $$
$$k_{ro}\ (oil\ -\ water) = k_{ro}@S_{wc} \left( \frac{1-S_w-S_{orw}}{1-S_{wc}-S_{orw}} \right)^{expow} $$
$$k_{ro}\ (gas\ -\ oil) = k_{ro}@S_{wc} \left( \frac{1-S_{wc}-S_{org}-S_g}{1-S_{wc}-S_{org}} \right)^{expog} $$
$$k_{rg}\ = k_{rg}@S_{wc} \left( \frac{S_g-S_{gr}}{1-S_{wc}-S_{gr}} \right)^{expg} $$
$$k_{rs}\ = k_{rs}@S_{wc} \left( \frac{S_g-S_{gr}}{1-S_{wirr}-S_{sr}-S_{orm}} \right)^{exps} $$
Dimana: <br/>
_S~wirr~_ = _irreducible water saturation (default = 0.2)_ <br/>
_S~orw~_ = _residual oil to waterflood (default = 0.37)_ <br/>
_S~wc~_ = _connate water saturation (default = 0.2)_ <br/>
_S~gr~_ = _residual gas saturation (default = 0.37)_ <br/>
_S~sr~_ = _residual solvent saturation (default = 0.37)_ <br/>
_S~orm~_ = _residual oil saturation to solvent (default = 0.001)_ <br/>
expw = _water equation exponent (default = 2)_ <br/>
expo = _oil equation exponent (default = 2)_ <br/>
expg = _gas equation exponent (default = 2)_ <br/>
exps = _solvent equation exponent (default = 2)_ 

### _Water/CO~2~ Injection Ratio_

___Water/CO~2~ Injection Ratio___ merupakan parameter yang menyatakan periode injeksi air dan CO~2~ dalam injeksi WAG. Parameter ini terkait dengan ___WAG ratio___, seperti diperlihatkan pada tabel di bawah berikut ini.

|WAG Ratio    |Water/CO~2~ Injection Ratio    |
|:---:        |:---:                          |
|2 to 1       |2    |
|1 to 1       |1    |
|1 to 2       |0.5  |
|1 to 3       |0.33 ||

Table: <span style="color: grey;"> Tabel 2.1: Hubungan antara WAG _ratio_ dan _water/CO~2~ injection ratio_ </span>

<br/>
_Water/CO~2~ injection ratio_ daoat ditentukan berdasarkan _time basis_ atau _volume basis_. Jika _user_ memilih _time basis_ dan nilai _water/CO~2~ injection ratio_ adalah 2, maka 67% dari total periode injeksi adalah injeksi air, dan 33% dari total periode injeksi adalah injeksi CO~2~. Jika _user_ memilih _volume basis_ dan nilai _water/injection ratio_ adalah 2, maka 67% dari total volume injeksi fluida adalah air, dan 33% dari total volume injeksi fluida adalah CO~2~.

### _Mixing Parameter ($\omega$)_

_Mixing parameter_ merupakan parameter yang digunakan untuk menggambarkan keadaan _miscibility_ di dalam model. Parameter ini berperan dalam mengatur viskositas efektif untuk fasa _solvent_ dan minyak. Jika , bernilai 0, maka tidak terjadi pencampuran dan fasa _solvent_ dan minyak memiliki nilai viskositas yang berbeda, masing-masing sesuai dengan nilai _immiscible_-nya. Jika $\omega$, bernilai 1, maka terjadi complete mixing dimana fasa minyak dan _solvent_ akan memiliki viskositas yang sama. Nilai default yang digunakan untuk, adalah 0.666.

Viskositas efektif untuk fasa minyak dan _solvent_ masing-masing dinyatakan oleh persamaan berikut:
$$Viskositas\ efektif\ solvent\ = \mu_{se} = (1-\alpha)\mu_s\ + \alpha\mu_{sm} $$
$$Viskositas\ efektif\ minyak\ = \mu_{oe} = (1-\alpha)\mu_o\ + \alpha\mu_{pm} $$
<p> &nbsp; </p>
Untuk kondisi _partially miscible_, yaitu P~*res*~ < _MMP_ dan P~*res*~ > _0.75MMP_, maka $\alpha$ dinyatakan oleh:
$$\alpha = \frac{P_{res}-0.75MMP}{0.25MMP}$$
<p> &nbsp; </p>
Untuk kondisi _completely miscible_, yaitu P~*res*~ > _MMP_, maka $\alpha$ dinyatakan oleh:
$$\alpha = 1$$
$$\mu_{sm} = \mu_s^{1-\omega}\mu_m^\omega$$
$$\mu_{om} = \mu_o^{1-\omega}\mu_m^\omega$$
$$\frac{1}{\mu_m^{0.25}} = \frac{1}{1-S_w} \left(\frac{S_o}{\mu_o^{0.25}} + \frac{S_g}{\mu_s^{0.25}} \right)$$

Dimana: <br/>
_$\mu_s$ = solvent viscosity_ <br/>
_$\mu_o$ = oil viscosity_ <br/>
_$\mu_m$ = mixed viscosity_ <br/>
*$\mu_{sm}$ = mixed solvent viscosity* <br/>
*$\mu_{om}$ = mixed oil viscosity* 

## Tiga Kondisi Aliran Fluida

Proses _flooding_ dapat terjadi dalam tiga kondisi, yaitu kondisi _immiscible flow_, _miscible flow_, dan _partially miscible flow_.

### _Immiscible Flow_

Pada kondisi aliran _immiscible_, permeabilitas relatif solvent merupakan fungsi dari saturasi _solvent_ saja. Pada kondisi ini, permeabilitas relatif minyak (_k_~*ro*~) dinyatakan oleh:

$$k_{ro} = \frac{1}{k_{row}}(A-k_{rg}-k_{rw})$$
$$A = \left( \frac{k_{row}}{k_{ro}@S_{wc}}+k_{rw}\right)\left( \frac{k_{rog}}{k_{ro}@S_{wc}}+k_{rg}\right) $$

### _Miscible Flow_

Pada kondisi aliran _miscible_, permeabilitas relatif fasa _miscible_ (_k_~*rm*~) dihitung dengan persamaan berikut.
$$k_{rm} = \frac{S_o-S_{orm}}{1-S_w-S_{orm}}(k_{row})\ +\ \frac{S_g}{1-S_w-S_{orm}}(k_{rs}) $$

### _Partially Miscible Flow_

Kondisi _partially miscible_ terjadi saat P~*res*~ < _MMP_ dan P~*res*~ > 0.75*MMP*. Pada kondisi ini, permeabilitas efektif minyak dan _solvent_ dinyatakan oleh persamaan berikut.
$$k_{roeff} = (1-\alpha)k_{ro}\ +\ \alpha \left( \frac{S_o-S_{orm}}{1-S_w-S_{orm}} \right)$$
$$k_{rseff} = (1-\alpha)k_{rg}\ +\ \alpha \left( \frac{S_g}{1-S_w-S_{orm}}(k_{rs} \right)$$

dimana:
$$\alpha = \frac{P_{res}-0.75MMP}{0.25MMP}$$

## Hasil Perhitungan dan Tampilan Perangkat Lunak

Hasil perhitungan CO~2~ Prophet memberikan informasi mengenai estimasi dari beberapa parameter performa produksi, diantaranya laju produksi minyak, laju produksi air, laju produksi CO~2~, dan lain sebagainya.

Berikut merupakan tampilan _screenshot_ dari _output_ yang dihasilkan oleh CO~2~ Prophet.

<div class="figure" style="text-align: center">
<img src="images/co2prophet/prediksiprophet.png" alt="Hasil prediksi performa dari CO~2~ Prophet" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-3)Hasil prediksi performa dari CO~2~ Prophet</p>
</div>
<p> &nbsp; </p>

<div class="figure" style="text-align: center">
<img src="images/co2prophet/produksiminyakprophet.png" alt="Grafik laju produksi minyak hasil perhitungan CO~2~ Prophet" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-4)Grafik laju produksi minyak hasil perhitungan CO~2~ Prophet</p>
</div>
<p> &nbsp; </p>

<div class="figure" style="text-align: center">
<img src="images/co2prophet/produksiairprophet.png" alt="Grafik laju produksi air hasil perhitungan CO~2~ Prophet" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-5)Grafik laju produksi air hasil perhitungan CO~2~ Prophet</p>
</div>
<p> &nbsp; </p>

<div class="figure" style="text-align: center">
<img src="images/co2prophet/produksisolventprophet.png" alt="Grafik laju produksi _solvent_ hasil perhitungan CO~2~ Prophet" width="50%" />
<p class="caption">(\#fig:unnamed-chunk-6)Grafik laju produksi _solvent_ hasil perhitungan CO~2~ Prophet</p>
</div>
<p> &nbsp; </p>
