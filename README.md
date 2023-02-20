**Context**

Sistem *bike sharing* merupakan sarana persewaan sepeda dimana seluruh proses mulai dari keanggotaan, persewaan, dan pengembalian telah menjadi otomatis menggunakan sistem. Dengan menggunakan sistem ini, orang dapat menyewa sepeda dari satu lokasi dan mengembalikannya ke tempat lain sesuai kebutuhan. Saat ini, ada lebih dari 500 program *bike sharing* di seluruh dunia yang terdiri dari 500 ribu sepeda. Sistem *bike sharing* menghasilkan minat yang besar karena peran pentingnya dalam mengatasi masalah lalu lintas, lingkungan, dan kesehatan. Data yang dihasilkan oleh sistem *bike sharing* ini menjadi menarik untuk diteliti dan dimanfaatkan lebih lanjut. Sistem *bike sharing* ini dapat menjadi semacam jaringan sensor yang berfungsi dalam membaca mobilitas di sebuah kota. Oleh karena itu, diharapkan peristiwa terpenting di kota dapat dideteksi dengan memantau data ini.

**Problem Statement**

Salah satu tantangan yang dihadapi oleh pemilik sistem *bike sharing* yaitu **memprediksi jumlah unit sepeda** yang akan disewa oleh pengguna pada waktu dan kondisi tertentu. 


**Goals**

Berdasarkan permasalahan tersebut, diperlukan sebuah **tool yang dapat memprediksi kebutuhan jumlah unit sepeda** pada waktu dan kondisi tertentu.


**Analytic Approach**

Data historis dari sistem *bike sharing* dapat dianalisa polanya berdasarkan fitur-fitur yang tersedia. Selanjutnya, untuk dapat memprediksi kebutuhan unit sepeda dalam sistem layanan *bike sharing* ini, kita dapat membuat sebuah 'tool' prediksi yang memanfaatkan **model regresi** dari fitur-fitur yang tersedia dalam data. 

**Metric Evaluation**

- RMSE : nilai akar dari rata-rata kuadrat dari error. RMSE berdimensi sama dengan label (*dependent variable*) serta peka terhadap outlier.
- MAE : nilai error absolut. MAE berdimensi sama dengan label (*dependent variable*) serta tidak peka terhadap outlier.
- MAPE : rata-rata persentase error. MAPE menghasilkan nilai yang relatif berupa persentase terhadap label (*dependent variable*).

**Conclusion**

Dari hasil Benchmark Model dan Hyperparameter Tuning yang dilakukan, diperoleh model XGBoost dengan performa terbaik dengan parameter terbaik sebagai berikut :
- sub_sample : 0.7
- reg_alpha : 2.1544346900318834
- n_estimators : 175
- max_depth : 7
- learning_rate : 0.13
- gamma : 4
- colsample_bytree : 0.9

Metrik evaluasi yang digunakan pada model ini adalah nilai RMSE, MAE & MAPE. Jika ditinjau dari nilai RMSE sebesar 38.98 (atau dibulatkan ke 39), maka ini berarti bahwa nilai prediksi untuk jumlah kebutuhan bike sharing akan berkisar kurang lebih 39 sepeda dari nilai prediksi dari model (dengan nilai maksimum yang dilatih dalam model yaitu 645).

Berdasarkan pemodelan yang telah dilakukan, fitur 'hr', 'year', 'One Hot__x0_3' (weather-3), 'temp', dan 'Binary__day' menjadi top 5 fitur yang paling berpengaruh terhadap 'count'.
