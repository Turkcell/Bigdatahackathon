# Turkcell Big Data Hackathon Sorular

## Soru 1
Size verilen datanın ortalama konuşma süresini mapreduce kullanarak bulun.
- Programlama dili bağımsız olacaktır. (MapReduce kullanmak koşuluyla Java, Python, Perl... olabilir.)
- Hive veya Pig kullanılmaması gerekmektedir.
- Output formatınız output_sample_a1.txt ile aynı olmalıdır.

Data :
SAMPLE : wasb://samplecalldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
FULL : wasb://calldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
START_TIME|END_TIME|CALLED_NO|CALLING_NO|TERMINATION_CAUSE_ID|CONVERSATION_TIME

Bu veri kullanıcıların arama aranma ilişkilerini tutmaktadır.

Aşağıda kolon tanımlarını bulabilirsiniz :
START_TIME : Arama başlama zamanı  Örnek veri: 2015-04-01 07:14:15.223
END_TIME : Arama bitiş zamanı  Örnek veri: 2015-04-01 07:16:00.000
CALLED_NO : Aranan abone kodu   Örnek veri: 12806310
CALLING_NO : Arayan abone kodu   Örnek veri: 12395211
TERMINATION_CAUSE_ID : Arama sonlandırma tipi bu veri karartılmıştır.  Örnek veri : 8
CONVERSATION_TIME : Arama süresi  Örnek veri: 12,5

## Soru 2
Toplam en uzun süre arayan ve toplam en uzun süre aranan kişiyi MapReduce kullanarak bulun.
- Programlama dili bağımsız olacaktır. (MapReduce kullanmak koşuluyla Java, Python, Perl... olabilir.)
- Hive veya Pig kullanılmaması gerekmektedir.
- Output formatınız output_sample_a2.txt ile aynı olmalıdır.

Data :
SAMPLE : wasb://samplecalldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
FULL : wasb://calldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
START_TIME|END_TIME|CALLED_NO|CALLING_NO|TERMINATION_CAUSE_ID|CONVERSATION_TIME

Veri tanımı soru 1 de açıklanmıştır.

## Soru 3
İstanbul’daki arama sürelerinin ortalamasını bulun.
- Hive veya Pig kullanılması gerekmektedir. Dileyenler mapreduce kullanılabilir.
- Output formatınız output_sample_a3.txt ile aynı olmalıdır.
İpucu: Her bir abonenin bulunduğu şehir ile arama kayıtlarının bulunduğu tablo joinlenecektir.

Data :
SAMPLE : wasb://samplecalldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
FULL : wasb://calldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
START_TIME|END_TIME|CALLED_NO|CALLING_NO|TERMINATION_CAUSE_ID|CONVERSATION_TIME

Veri tanımı soru 1 de açıklanmıştır.

SAMPLE : wasb://samplesubscriberlocationcontainer@tbigdatahackathonstorage.blob.core.windows.net/
FULL : wasb://subscriberlocationcontainer@tbigdatahackathonstorage.blob.core.windows.net/
SUBSCRIBER_ID|CITY_OF_RESIDENCE

Bu veri kullanıcıların yaşadıkları şehirleri bulundurmaktadır.
SUBSCRIBER_ID : Abone kodu.  Örnek veri: 12806310
CITY_OF_RESIDENCE : Abonenin yaşadığı şehir.  Örnek veri: ISTANBUL

## Soru 4
Bir abone diğer aboneyi arar ancak görüşme olmaz. Aranılan abone arayan aboneyi 1 dakika içerisinde tekrar arar ve konuşur.
Bu şarta uyan en çok arama yapan 10 kişiyi bulun.
- Hive veya Pig kullanılması gerekmektedir. Dileyenler mapreduce kullanılabilir.
- Output formatınız output_sample_a4.txt ile aynı olmalıdır.
Örnek: Ahmet, Mehmet’i 14:01:00 arar. Ancak konuşma yapmazlar.
Mehmet, Ahmet’i 14:02:00 saati öncesinde geri arar ve belli bir süre konuşurlar.
Ahmet’in davranışını en çok sergileyen 10 kişiyi bulun.

Data :
SAMPLE : wasb://samplecalldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
FULL : wasb://calldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
START_TIME|END_TIME|CALLED_NO|CALLING_NO|TERMINATION_CAUSE_ID|CONVERSATION_TIME

Veri tanımı soru 1 de açıklanmıştır.

## Soru 5
En az aranan ildeki en çok aranan 3 aboneyi bulun.
- Hive veya Pig kullanılması gerekmektedir. Dileyenler mapreduce kullanılabilir.
- Output formatınız output_sample_a5.txt ile aynı olmalıdır.
İpucu: Her bir abonenin bulunduğu şehir ile arama kayıtlarının bulunduğu tablo joinlenecektir.

Data :
SAMPLE : wasb://samplecalldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
FULL : wasb://calldatacontainer@tbigdatahackathonstorage.blob.core.windows.net/
START_TIME|END_TIME|CALLED_NO|CALLING_NO|TERMINATION_CAUSE_ID|CONVERSATION_TIME

Veri tanımı soru 1 de açıklanmıştır.

SAMPLE : wasb://samplesubscriberlocationcontainer@tbigdatahackathonstorage.blob.core.windows.net/
FULL : wasb://subscriberlocationcontainer@tbigdatahackathonstorage.blob.core.windows.net/
SUBSCRIBER_ID|CITY_OF_RESIDENCE

Veri tanımı soru 3 de açıklanmıştır.

## Soru 6
Size verilen data içerisinde bir kişinin kaç farklı kişiye sms attığını büyükten küçüğe sıralayın. Sadece ilk 20 kayıt istenmektedir.
- Programlama dili bağımsız olacaktır. (MapReduce kullanmak koşuluyla Java, Python, Perl... olabilir.)
- Hive veya Pig kullanılmaması gerekmektedir.
- Output formatınız output_sample_a6.txt ile aynı olmalıdır.

Data :
SAMPLE : wasb://samplesubscriberusagecontainer@tbigdatahackathonstorage.blob.core.windows.net/
FULL : wasb://subscriberusagecontainer@tbigdatahackathonstorage.blob.core.windows.net/
CALLING_NO|CALLED_NO|CALL_TYPE|DURATION|CALL_COUNT

Bu veri kullanıcıların arama aranma ve SMS gönderme alma ilişkilerini tutmaktadır.

CALLED_NO : Aranan abone kodu   Örnek veri: 12806310
CALLING_NO : Arayan abone kodu   Örnek veri: 12395211
CALL_TYPE : Arama tipi  Örnek veri: SMS
DURATION : Arama süresi  Örnek veri: 12
CALL_COUNT : Arama sayısı  Örnek veri: 25
