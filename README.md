# Otel Konaklama Sistemi Projesi

Bir otel için otomasyon sistemi geliştirerek, rezervasyon, oda, müşteri ve ödeme yönetimini daha verimli hale getirmek.

### Proje Ekibindeki Kişiler
- Yusuf Enes Demir (225260001)
- Mert Arslan (225260051)
- Yusuf Talha Yıldırım (225260085)

## Proje Özeti

Otel Otomasyon Sistemi, aşağıdaki kullanıcı türlerini ve işlevleri destekler:
- **Müşteriler**: Müşterilerin adı, telefon numarası ve e-posta adresi gibi temel iletişim bilgileri saklanacaktır.
- **Oda Yönetimi**: Otel odalarının durumu, rezervasyonları ve oda tipleri gibi çeşitli faktörleri içerir.
- **Otel Yöneticileri**: Oda bilgileri, fiyatlandırmalar, müşteri bilgileri, rezervasyonlar ve hizmetler hakkında bilgi ekleyebilir ve düzenleyebilir.
- **Fatura**: Otel hizmetlerinden yararlanan müşteriler için faturalama işlemlerini düzenler, takip eder ve yönetir.
  
Bu veri tabanı modeli; otel, odalar, müşteriler, rezervasyonlar, hizmetler, personel ve faturalama gibi birçok varlığı kapsar.

## DataBase Structure

### Entitys (Tables) and Attributes

#### 1. Customer
- **Customer_id** (Primary Key): Müşterinin kimlik numarası.
- **Age**: Müşterinin yaşı.
- **Gender**: Müşterinin cinsiyeti.
- **Name**: Müşterinin adı.
- **Phone**: Müşterinin telefon numarası.
- **Email**: Müşterinin e-posta adresi.

#### 2. Room
- **Room_id** (Primary Key): Oda numarası kimlik numarası.
- **Hotel_id** (Foreign Key): Odanın ait olduğu otelin kimlik numarası.
- **Room_Type**: Odanın tipi.
- **Price**: Oda ücreti.
- **Available**: Oda müsaitliği.

#### 3. Hotel
- **Hotel_id** (Primary Key): Otelin kimlik numarası.
- **Hotel_Name**: Otelin ismi.
- **Location**: Otelin konumu.
  
#### 4. Bill 
- **Bill_id** (Primary Key): Fatura kimlik numarası.
- **Customer_id** (Foreign Key): Faturayı ödeyen kişinin müşteri kimliği.
- **Date**: Faturanın oluşturulma tarihi.
- **Amount**: Faturanin bedel miktarı.
  
#### 5. Reservation
- **Reservation_id** (Primary Key): Reservasyon kimlik numarası.
- **Customer_id** (Foreign Key): Rezervasyonu yapan müşteri kimliği.
- **Room_Number** (Foreign Key): Rezervasyon yapılan oda numarası.
- **Start_Date**: Rezervasyon başlangıç tarihi.
- **End_Date**: Rezervasyon bitiş tarihi.

#### 6. Admin
- **Admin_id** = Yönetici kimlik numarası.
- **Admin_name** = Yönetici ismi.
- **Username** = Yönetici kullanıcı adı.
- **Password** = Yönetici şifresi.

### Relations
1. **Customer - Reservation** : Her rezervasyon tek bir müşteriye aittir (**N-1**).
2. **Customer - Bill**: Her fatura tek bir müşteriye aittir (**N:1**).
3. **Customer - Review**: Her değerlendirme tek bir müşteriye aittir (**N-1**).
4. **Room - Hotel**: Bir otelde birden fazla oda olabilir (**1:N**).
5. **Room - Reservation** : Her rezervasyon belirli bir odaya aittir. (**N-1**)
6. **Hotel - Review** : Bir otel, birden fazla müşteri tarafından değerlendirilebilir (**1-N**).

![image](https://github.com/user-attachments/assets/08371886-2167-4461-9d84-badd7104a589)

