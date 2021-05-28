>    Ödev iki aşamadan oluşmaktadır. [link](https://data.ibb.gov.tr/dataset/saatlik-trafik-yogunluk-veri-seti) üzerinde bulunan seçmiş olduğunuz bir aylık veriyi download edip aşağıda belirtilen şekillerde yükleme yapmanız bekleniyor.
> 
> 1.  Aşama: Datayı, Task – 1 için seçmiş olduğunuz teknolojiye göre (ilgili python kütüphanelerini kullanarak)
> 
> -   Kafka seçenler, datayı bir Kafka Topic'e,
> -   Postgre seçenler, datayı bir PG Table'a,
> -   Cassandra seçenler, datayı bir Cassandra tablosuna  yüklemelisiniz.
>  2.  Aşama: Datayı, Task – 2 için oluşturduğunuz minio object storage
> üzerinde bir bucket'a (ilgili python kütüphanelerini kullanarak)  yüklemelisiniz.

Kurgulanan Ortam yapısı şu şekildedir.

 - core/centos : 192.168.233.134
 - centos 1 : 192.168.233.133/24
 - centos :2 : 192.168.233.132/24
 - centos 3:  192.168.233.129/24 
