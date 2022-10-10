# AlphaTeam_JC_DS_LS_02_FinalProject

![a](https://play-lh.googleusercontent.com/eqLTXWdyygKUf85JsCXmcLSr1GnoYNLJfFVCmY-N8xGFr2T3PWwNcFdJ2Sx7MwcO6ac)

### **Alpha Team :**
- Kevin Pratama
- Muhammad Mukhlis
- Sari Amalia

## **Contents**

1. Business Problem Understanding
2. Data Understanding
3. EDA (Explanatory Data Analysis) & Data Preprocessing
4. Data Analysis & Modeling
5. Conclusion & Recommendation

------------

## **1. Business Problem Understanding**

**Context**

Di Brazil, *online shopping* menjadi salah satu kebiasaan yang berkembang dengan cepat. Menurut [Valor Capital Group](https://valorcapitalgroup.com/case-studies/olist-redesigned-the-marketplace-business-model-to-fit-the-realities-of-ecommerce-in-brazil/#:~:text=Through%20a%20single%2C%20seamless%20integration%2C%20Olist%20would%20provide,customer%20service%2C%20and%20payments%20in%20a%20single%20place), *online seller* di Brazil menghadapi beban operasional yang harus diintegrasikan secara manual pada berbagai *marketplace* sehingga Olist hadir untuk memecahkan masalah tersebut.
Olist merupakan sebuah *startup* yang berdiri pada tahun 2015 dan berhasil menjadi *unicorn* pada tahun 2021 setelah mendapat investasi sebesar USD 186 juta ([Valor Capital Group](https://valorinternational.globo.com/business/news/2021/12/15/olist-is-brazils-newest-unicorn.ghtml)). Bila dilihat dari website [Olist](https://olist.com/pt-br/) perusahaan ini memiliki 4 produk yang ditawarkan, salah satunya adalah Olist Store yang bergerak di bidang *e-commerce* dan menjadi subjek yang akan dibahas. Dilansir dari website [PitchBook](https://pitchbook.com/profiles/company/102473-65#overview), *platform* Olist menghubungkan pengusaha dengan *online seller* dan memberi akses kepada penjual untuk mengiklankan dan menjual di *marketplaces* tanpa masalah, serta memungkinkan perusahaan retail untuk menjangkau *marketplaces* internasional.

Olist menyediakan layanan operasional menyeluruh kepada *merchants* dengan mengelola katalog produk, inventaris, harga, *fulfillment*, layanan *customer*, dan pembayaran dalam satu tempat. Penjual hanya perlu menginput produk-produk yang akan dijual sekali saja pada Olist Store yang kemudian akan diintegrasikan oleh Olist ke berbagai *e-commerce* lain.

Berdasarkan website [Similarweb](https://www.similarweb.com/website/olist.com/#ranking) Olist Store (salah satu produk Olist) berada pada peringkat 43 untuk kategori *e-commerce* di Brazil. Pada dasarnya masyarakat akan lebih mengenal nama-nama perusahaan yang masuk kategori kelas atas. Mengingat Olist Store ada di peringkat 43, Olist Store perlu "merangkak" naik supaya masyarakat bisa mengenal Olist Store lebih dalam. Peringkat tersebut juga tergolong rendah untuk perusahaan sekelas Olist yang sudah mendapat status sebagai *unicorn*. Menurut [Think With Google](https://www.thinkwithgoogle.com/feature/online-shopping-trends/landing?lang=pt_BR), masyarakat di Brazil menjadikan *free shipping*, *discounts and promotions*, dan *lower prices* sebagai tiga elemen utama yang memengaruhi keputusan berbelanja mereka. Namun, juga terdapat masyarakat yang tidak terlalu memedulikan ketiga elemen tersebut sebagai pertimbangan ketika berbelanja. Oleh karena itu, Olist Store membutuhkan segmentasi pasar berdasarkan ketiga elemen tersebut sehingga marketing akan lebih tepat sasaran dan akan lebih banyak *customer* yang melakukan transaksi di Olist Store. Hal ini diharapkan dapat membantu Olist Store mendapatkan peringkat yang lebih baik dan lebih banyak masyakarat yang berbelanja di Olist store. Semakin banyak pembeli, maka profit yang akan didapat Olist Store akan semakin tinggi.

**Problem Statement**

*RFM* merupakan teknik segmentasi *customer* yang menggunakan pengamatan terhadap perilaku berbelanja *customer*. RFM merupakan singkatan dari *Recency*. *Frequency*, dan *Monetary Value*.

*RFM* dapat dilakukan secara manual dan otomatis. Segmentasi yang dilakukan secara manual akan memakan sangat banyak waktu dan tenaga. Oleh karena itu, segmentasi dapat dilakukan dengan cara mengotomatisasi proses bisnis. Salah satu cara tersebut adalah dengan menggunakan *tool* khusus untuk proses segmentasi *customer*. CDP (*Customer Data Platform*) dimanfaatkan sebagai sumber untuk mendapatkan data terkait perilaku *customer* sehingga segmentasi menjadi lebih akurat. RFM cocok digunakan untuk segmentasi *customer* karena mempertimbangkan *customer behavior* yang dilihat dari ketiga aspek berikut.

RECENCY (R): Waktu berbelanja terakhir<br>
FREQUENCY (F): Jumlah pembelian<br>
MONETARY VALUE (M): Total uang pembelanjaan<br>

**Analisis yang akurat mengenai segmentasi *customer* akan membantu perusahaan dalam menerapkan strategi marketing yang efektif**.

**Goals**

Dalam analisis ini, data diperoleh langsung dari Olist Store dan akan digunakan untuk menentukan segmentasi konsumen. Hal ini diperlukan dengan tujuan perusahaan **dapat meningkatkan peringkatnya agar masyarakat lebih mengenal Olist Store dengan cara menerapkan strategi marketing yang efektif** untuk masing-masing segmen.

**Analytic Approach**

Hal pertama yang harus dilakukan adalah dengan menganalisis seluruh transaksi yang pernah terjadi untuk menemukan pola dari fitur-fitur yang diberikan dan yang membedakan setiap *customer*. Langkah berikutnya akan dilakukan segmentasi RFM yang akan membantu perusahaan menentukan segmentasi konsumen.

**Metric Evaluation**

Evaluasi metrik yang akan digunakan adalah metode *silhouette* dan *elbow* untuk seluruh model.
1. *Elbow Method*
2. *Silhouette Method*

## **2. Data Understanding**

**Dataset source :** https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce?select=olist_products_dataset.csv

**Data Info**

Data ini dibuat oleh *Olist* dan berisikan informasi *customer, seller, product, order, review, dan geolocation* dari Olist Store di Brazil mulai tahun 2016 hingga 2018

### **2.1 Customers Dataset**

Dataset ini memiliki informasi mengenai *customers* dan lokasinya. Dataset ini digunakan untuk mengidentifikasi *unique customers* pada dataset *orders* dan untuk mendapatkan *orders delivery location*-nya.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Customer_ID             | object    | key to the orders dataset. Each order has a unique customer_id |
| Customer_Unique_ID      | object    | unique identifier of a customer |
| Customer_Zip_Code_Prefix | int64     | first five digits of customer zip code |
| Customer_City           | object    | customer city name |
| Customer_State          | object    | customer state |

### **2.2 Geolocation Dataset**

Dataset ini memiliki informasi mengenai kodepos di Brazil beserta koordinat *latitude* dan *longitude*-nya. Dataset ini digunakan untuk mem-*plot* peta dan menemukan jarak antara penjual dan pembeli.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Geolocation_Zip_Code_Prefix   | int64 | first 5 digits of zip code |
| Geolocation_Latitude   | float64   | latitude |
| Geolocation_Longitude   | float64   | longitude |
| Geolocation_City  | object    | city name |
| Geolocation_State | object    | state |


### **2.3 Order Items Dataset**

Dataset ini memiliki informasi mengenai *items* yang dibeli dalam setiap pesanan.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Order_ID  | object    | order unique identifier |
| Order_Item_ID | int64 | sequential number identifying number of items included in the same order |
| Product_ID    | object    | product unique identifier |
| Seller_ID | object  | seller unique identifier |
| Shipping_Limit_Date   | object    | Shows the seller shipping limit date for handling the order over to the logistic partner |
| Price | float64   | item price |
| Freight_Value | float64   | item freight value item (if an order has more than one item the freight value is splitted between items) |

### **2.4 Order Payment Dataset**

Dataset ini memiliki informasi mengenai metode pembayaran.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Order_ID  | object    | unique identifier of an order |
| Payment_Sequential    | int64 | a customer may pay an order with more than one payment method. If he does so, a sequence will be created to |
| Payment_Type  | object    | method of payment chosen by the customer |
| Payment_Installments  | int64 | number of installments chosen by the customer |
| Payment_Value | float64   | transaction value |

### **2.5 Order Reviews Dataset**

Dataset ini memiliki informasi mengenai *review* yang dibuat oleh *customer*. 

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Review_ID | object    | unique review identifier |
| Order_ID  | object | unique order identifier |
| Review_Score  | int64    | Note ranging from 1 to 5 given by the customer on a satisfaction survey |
| Review_Comment_Title  | object | Comment title from the review left by the customer, in Portuguese |
| Review_Comment_Message    | object   | Comment message from the review left by the customer, in Portuguese |
| Review_Creation_Date  | object   | Shows the date in which the satisfaction survey was sent to the customer |
| Review_Answer_Timestamp   | object   | Shows satisfaction survey answer timestamp |

### **2.6 Orders Dataset**

Dataset ini merupakan dataset utama. Dataset ini memiliki informasi mengenai masing-masing order.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Order_ID  | object    | unique identifier of the order |
| Customer_ID   | object | key to the customer dataset. Each order has a unique customer_id |
| Order_Status  | object    | Reference to the order status (delivered, shipped, etc) |
| Order_Purchase_Timestamp  | object | Shows the purchase timestamp |
| Order_Approved_Timestamp | object   | Shows the payment approval timestamp |
| Order_Delivered_Carrier_Date     | object   | Shows the order posting timestamp. When it was handled to the logistic partner |
| Order_Delivered_Customer_Date | object   | Shows the actual order delivery date to the customer |
| Order_Estimated_Delivery_Date | object   | Shows the estimated delivery date that was informed to customer at the purchase moment |

### **2.7 Products Dataset**

Dataset ini memiliki informasi mengenai data produk yang dijual di Olist Store.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Product_ID    | object    | unique product identifier |
| Product_Category_Name | object | root category of product, in Portuguese |
| Product_Name_Length   | float64    | number of characters extracted from the product name |
| Product_Description_Length    | float64 | number of characters extracted from the product description |
| Product_Photos_Qty    | float64   | number of product published photos |
| Product_Weight_gr  | float64   | product weight measured in grams |
| Product_Length_cm | float64   | product length measured in centimeters |
| Product_Height_cm | float64   | product height measured in centimeters |
| Product_Width_cm  | float64   | product width measured in centimeters |

### **2.8 Sellers Dataset**

Dataset ini memiliki informasi mengenai penjual yang menyelesaikan order yang dibuat di Olist Store. Dengan dataset ini kita dapat menemukan lokasi penjual dan mengidentifikasi penjual mana yang memenuhi pembelian.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Seller_ID | object    | seller unique identifier |
| Seller_Zip_Code_Prefix   | int64  | first 5 digits of seller zip code |
| Seller_City   | object    | seller city name |
| Seller_State  | object | seller state |

### **2.10 Data Schema**

Data ini terbagi menjadi 9 dataset. hubungan antar dataset dapat dilihat pada gambar schema berikut.
![a](https://i.ibb.co/xS6Q78b/schema.png)
