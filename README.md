# CapstoneProject3 - ML - CLV Prediction

**Problem Statement**

Dalam berbisnis, untuk mendapatkan customer baru bisa [sampai 25 kali](https://hbr.org/2014/10/the-value-of-keeping-the-right-customers) lebih mahal daripada mempertahankan customer lama (customer retention). Customer retention menjadi kunci dari sumber pendapatan yang stabil bagi perusahaan karena pembelian berulang dari existing customer membuat bisnis perusahaan tetap berjalan. Oleh karena itu, perusahaan perlu melihat seberapa valuable customer terhadap bisnis perusahaan. Untuk mengukur hal tersebut, terdapat sebuah metrik yang dapat digunakan yaitu metrik **Customer Lifetime Value (CLV)**.

Customer Lifetime Value (CLV) adalah jumlah uang yang dikeluarkan customer untuk perusahaan sepanjang hubungan bisnis antara customer dengan perusahaan tersebut. CLV penting bagi bisnis karena dapat meningkatkan revenue perusahaan, meningkatkan customer acquisition dan customer retention, membantu perusahaan merencanakan anggaran marketingnya, dan lain-lain. Pada implementasinya, metrik CLV banyak digunakan oleh perusahaan yang melakukan repeat sales kepada customer (misal. makanan, produk rumah tangga) maupun perusahaan yang menggunakan sistem berlangganan dalam bisnisnya (misal. asuransi, perusahaan telekomunikasi).  

Dalam project ini, terdapat sebuah perusahaan asuransi mobil di Amerika Serikat mengalami issue dalam meningkatkan revenue perusahaan. Salah satu penyebab issuenya adalah karena pendekatan strategi marketing yang tidak tepat dimana perusahaan mengeluarkan budget yang sama untuk seluruh customer (baik new maupun existing customer), sehingga perusahaan akhirnya membayar lebih untuk low-value customer dan kehilangan high-value customer. Maka dari itu, perusahaan menggunakan metrik CLV untuk menentukan seberapa valuable customer yang dimiliki. Namun perusahaan asuransi mobil tersebut belum memiliki sistem untuk memprediksi CLV dengan cepat dan akurat sehingga penentuan strategi marketing saat ini memakan waktu lebih lama karena pengolahan data yang masih secara manual. Oleh karena itu, prediksi CLV yang lebih cepat dan akurat sangatlah penting untuk dapat mengambil strategi marketing yang lebih tepat pula.

Dari permasalahan diatas, maka kita dapat mengajukan pertanyaan berupa:
1. Bagaimana memprediksi CLV sehingga dapat meningkatkan revenue perusahaan?
2. Fitur apa yang paling berpengaruh dalam menentukan CLV?

**Goals**

Berdasarkan permasalahan diatas, maka tentunya akan sangat mudah apabila terdapat 'tools' bagi perusahaan asuransi mobil (khususnya divisi marketing) memprediksi CLV dengan melihat dari data demografis dan data asuransi mobil customer (tipe asuransi, jumlah polis, biaya premi, total klaim, dan lainnya) sehingga pengolahan data CLV tidak lagi secara manual dan dapat mempercepat proses pengambilan keputusan strategi marketing.

**Analytic Approach**

Membangun suatu model regresi yang akan membantu perusahaan untuk dapat menyediakan 'tools' prediksi CLV dengan menganalisis data yang dapat menemukan pola dari feature-feature yang ada, untuk membedakan CLV masing-masing customer.

**Metric Evaluation**

Evaluasi metrik yang akan digunakan adalah RMSE, MAE, dan MAPE, di mana RMSE adalah nilai akar kuadrat dari error, MAE adalah rataan nilai absolut dari error, sedangkan MAPE adalah rataan persentase error yang dihasilkan oleh model regresi. Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi CLV sesuai dengan limitasi feature yang digunakan. 

# Data Source

- Dataset merupakan data customer asuransi mobil di Amerika Serikat tahun 2019
- Sumber dataset: [Link](https://www.kaggle.com/datasets/pankajjsh06/ibm-watson-marketing-customer-value-data)
- Informasi atribut menggunakan informasi dari Kaggle user lain karena tidak ditemukannya pada sumber dataset awal: [Link](https://www.kaggle.com/code/juancarlosventosa/models-to-improve-customer-retention/notebook)

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Vehicle Class | Object | Vehicle type classification |
| Coverage | Object | Types of vehicle insurance coverage |
| Renew Type Offer | Object | Offer to renew policies that have been/will expire |
| EmploymentStatus | Object | Customer's employment status |
| Marital Status | Object | Customer's marital status |
| Education | Object | Customer's educational level |
| Number of Policies | Float | Number of policies owned by the customer |
| Monthly Premium Auto | Float | Monthly premium paid by the insured |
| Total Claim Amount | Float | Cumulative number of claims since the beginning of the policy |
| Income | Float | Customer's income (in dollar) |
| Customer Lifetime Value | Float | Customer Lifetime Value (Target) |
