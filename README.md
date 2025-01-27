🍜 Case Study #1: Danny's Diner

Case study  for the #Dannysdinner sql project.
![danny's_dinner_sql_projects](https://github.com/user-attachments/assets/66002c79-67cf-47d0-9606-f055a1a23100)

I came across this project after I started learning SQL and thought it would help me practice the concepts and gain proficiency in data analysis.

SQL öğrenmeye başladıktan sonra bu projeyle  karşılaştım ve bunun kavramları pratik etmeme ve data analizinde yetkinlik kazanmama yardımcı olacağını düşündüm.

**Case Study Introduction**

Danny seriously loves Japanese food so in the beginning of 2021, he decides to embark upon a risky venture and opens up a cute little restaurant that sells his 3 favourite foods: sushi, curry and ramen.

The restaurant has collected some basic data over the course of several months of operation, but they don’t know how to use that data to run the business.
—
**Türkçe**
**Vaka Çalışması Giriş**

Danny Japon yemeklerine gerçekten bayılıyor ve 2021'in başlarında riskli bir işe girişmeye karar veriyor ve en sevdiği 3 yemeği satan sevimli bir restoran açıyor: suşi, köri ve ramen.
Restoran, birkaç aylık faaliyetleri sırasında bazı temel verileri topladı ancak bu verileri işletmeyi yürütmek için nasıl kullanacaklarını bilmiyorlar.

**Business Task**

Danny wants to use the data to answer a few simple questions about his customers, especially about their visiting patterns, how much money they’ve spent and also which menu items are their favourite.
visiting patterns,
how much money they’ve spent, and
which menu items are their favourite.


The data set contains the following 3 tables which you may refer to the relationship diagram below to understand the connection.
*sales
*members
*menu



**Türkçe:**

Danny, verileri müşterileriyle ilgili birkaç basit soruyu cevaplamak için kullanmak istiyor. 

Ziyaret düzenleri(desenleri),
Ne kadar para harcadıkları ve
Hangi menü öğelerinin favorileri olduğu .
Danny, bu vaka çalışması için bizimle 3 temel veri seti paylaştı.
Veri seti, bağlantıyı anlamak için aşağıdaki ilişki diyagramına başvurabileceğiniz 3 tablodan oluşmaktadır.:
sales
menu
members


Aşağıdaki varlık ilişki diyagramını ve örnek verileri inceleyebilirsiniz.



**Entity Relationship Diagram**
(Tablo İlişkisi)


![Screen Shot 2025-01-27 at 16 34 17](https://github.com/user-attachments/assets/14d8e460-b816-4461-9463-fb57a7ec40f8)


You can find all the details for this challenge including datasets here.
(Bu meydan okuma için tüm detayları veri kümeleri dahil burada bulabilirsiniz .)







**Case Study Questions

After creating the database and tables, I started to answer the following questions.
I am using PostgreSQL in this project.

Ben bu projede **PostgreSQL** kullanıyorum .

**1. What is the total amount each customer spent at the restaurant?**


Use JOIN to merge dannys_diner.sales and dannys_diner.menu tables as sales.customer_id and menu.price are from both tables.
Use SUM to calculate the total sales contributed by each customer.
Group the aggregated results by sales.customer_id.


**Türkçe:**


**1-Restoranda her müşterinin harcadığı toplam miktar nedir?**




Fiyat ve müşteri id'sini almak için farklı tablolarda bulunan tabloları JOIN komutunu kullanarak birleştirdim 


Toplanan sonuçları sales.customer_id’e göre gruplandırdım.


Her müşterinin yaptığı (katkıda bulunduğu)toplam satışları hesaplamak için SUM'u kullandım .
Toplanan sonuçları sales.customer_id ‘e göre gruplandıralım 

![Screen Shot 2025-01-27 at 16 51 36](https://github.com/user-attachments/assets/e50e54a1-0e27-4f94-a5ae-f4ac24c60624)




**Conclusion:**

![Screen Shot 2025-01-27 at 16 51 48](https://github.com/user-attachments/assets/2d7f9c6d-4547-44db-abbf-f3df83c774bb)

Customer A spent the most at 152, while customer C spent the least.

Sonuç:
A müşterisi 152  ile en fazla harcamayı yaparken C müşterisi en az harcamayı yapmıştır.


**2. How many days has each customer visited the restaurant?**

I used COUNT(DISTINCT) and GROUP BY to get the answer.
To determine the unique number of visits for each customer, utilize COUNT(DISTINCT order_date). It’s important to apply the DISTINCT keyword while calculating the visit count to avoid duplicate counting of days. 


**Türkçe:**
Her siparişin bir sipariş tarihi vardır ve ziyaret eden bir müşteri bir günde birden fazla sipariş verebilir.
Her müşteri için benzersiz ziyaret sayısını belirlemek için COUNT(DISTINCT order_date) işlevini kullandım ve müşteriye göre gruplamak için de müşteri id’sine göre group by komutunu kullandım.
**Conclusion:**

![Screen Shot 2025-01-27 at 16 53 16](https://github.com/user-attachments/assets/805842cd-9e61-4ea5-8f77-e0cd57733066)

Customer A visited 4 times.
Customer B visited 6 times.
Customer C visited 2 times.
Sonuç:

Müşteri A , 4 kez ziyaret etti.
Müşteri B ,6 kez ziyaret etti.
Müşteri C,  2 kez ziyaret etti.




**3. What was the first item from the menu purchased by each customer?**

Her müşterinin menüden satın aldığı ilk ürün neydi?

Explanation
**Stage 1:

FIRST, I WILL FIND THE FIRST ORDER DATE, THEN I WILL DETERMINE THE FILTER CRITERIA ACCORDING TO THIS DATE AND WRITE THE CODE.

İLK OLARAK İLK SİPARİŞ TARİHİNİ BULACAĞIM SONRASINDA BU TARİHE GÖRE FİLTRE KRİTERİ BELİRLEYEREK kod yazacağım.

**Output:

![Screen Shot 2025-01-27 at 16 53 31](https://github.com/user-attachments/assets/96590b50-c092-4de5-8c75-d0a78d5f5b28)

![Screen Shot 2025-01-27 at 16 53 42](https://github.com/user-attachments/assets/dc9d1577-72ee-4b5a-8095-af7319fbac1a)

Stage 2:
![Screen Shot 2025-01-27 at 16 54 04](https://github.com/user-attachments/assets/3172984d-1dbc-4221-b211-0cbca15fc863)


Conclusion:


![Screen Shot 2025-01-27 at 16 54 16](https://github.com/user-attachments/assets/9a72f9f8-3743-40af-bf90-fe28e1f28338)

Customer A ordered sushi and curry on their first visit. We don't know which was ordered first due to the lack of time information, but we know both were ordered on the same day. Customer B's first order was curry, and Customer C's was ramen.



**Sonuç:**
Müşteri A ilk ziyaretinde suşi ve köri sipariş etti. Sunulan verilerde zaman bilgisi eksikliğinden dolayı hangisinin daha önce sipariş edildiğini bilmiyoruz, ancak ikisinin de aynı gün sipariş edildiğini biliyoruz. 
Müşteri B'nin ilk siparişi köri ve Müşteri C'ninki ramen’dir.



4. What is the most purchased item on the menu and how many times was it purchased by all customers?


Explanation

**Stage 1:**
First, we need to determine how many of each product was sold.
(Menüde en çok satın alınan ürün hangisidir ve tüm müşteriler tarafından kaç kez satın alınmıştır?
Öncelikle her üründen kaç adet satıldığını tespit etmemiz gerekiyor.)

**Output:**


![Screen Shot 2025-01-27 at 17 04 56](https://github.com/user-attachments/assets/a0177f04-cf50-4fc8-943d-2b030064eeb2)


Stage 2:
We will sort the products in descending order (highest count to lowest). Using the LIMIT 1 expression, we can filter our sales results to only show the product with the highest count that appears in the first row.

Ürünleri azalan düzende (en yüksek sayıdan en düşüğe) sıralayacağız. LIMIT 1 ifadesini kullanarak salessonuçlarımızı yalnızca ilk satırda görünen en yüksek sayıma sahip ürünü gösterecek şekilde filtreleyebiliriz.

![Screen Shot 2025-01-27 at 17 06 13](https://github.com/user-attachments/assets/abf97a25-714b-4315-98da-b9df66dd4c96)



**Output**

![Screen Shot 2025-01-27 at 17 06 23](https://github.com/user-attachments/assets/f0728c74-7e90-4a0d-9b73-b895539c954d)

**Conclusion:**

Ramen is the most ordered item on the menu. It's crucial to ensure that the ingredients required for ramen are always in stock to meet customer demand.

**Sonuç:**
Ramen, menüdeki en çok sipariş edilen üründür. Müşteri talebini karşılamak için ramen için gereken malzemeleri bulundurmak fayda sağlar.

**5. Which item was the most popular for each customer?**

–Her bir müşterinin en popüler ürünü,yani en çok satın aldığı ürün hangisidir?

**Stage 1:**
sales tablosu ile menu tablosunu JOIN komutu ile birleştirelim
her üründen kaç tane aldığını count ile saydıralım
--product_id'ye göre tabloları bağladığımız için bu product id'yi hangi tablodan çağırdığımızı da belirtmemiz gerekiyor; bunu s.product_id diye yazarak belirtebiliriz.
---aggregate function kullandığımız için 1,2 'ye göre group by yaparak çalıştırabiliriz komut.

![Screen Shot 2025-01-27 at 17 07 14](https://github.com/user-attachments/assets/75ad52b7-4302-4c2f-bc12-8f016a583143)



**Output: Her bir müşterinin hangi ürünü kaç defa  aldığını görebiliyoruz.**
![Screen Shot 2025-01-27 at 17 07 27](https://github.com/user-attachments/assets/ee5e2dce-c7e2-4e85-8d26-4f6fa3c40cd3)

**Stage 2:**
In this stage, we use the RANK() function to rank the products for each customer based on how many times they ordered them. The product with the highest rank is the one they ordered the most. Next, we turn this query into a Common Table Expression (CTE) and then retrieve the most frequently ordered product(s) for each customer.

![Screen Shot 2025-01-27 at 17 08 07](https://github.com/user-attachments/assets/fb8f57cf-738c-4b11-bc43-64e429b3c8eb)



**Output:**
![Screen Shot 2025-01-27 at 17 08 23](https://github.com/user-attachments/assets/284dba17-d532-426a-8e04-937435806d23)

**Conclusion**
Customer A's most ordered product is ramen. Customer B ordered curry, sushi and ramen in equally . Customer C's favorite product is ramen


**Türkçe:**
Müşteri A'nın en çok sipariş ettiği ürün ramendir. Müşteri B, köri, suşi ve ramen'i eşit olarak sipariş etti. Müşteri C'nin en sevdiği ürün ramendir.











