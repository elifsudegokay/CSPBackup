..  Copyright (C)  Mark Guzdial, Barbara Ericson, Briana Morrison
    Permission is granted to copy, distribute and/or modify this document
    under the terms of the GNU Free Documentation License, Version 1.3 or
    any later version published by the Free Software Foundation; with
    Invariant Sections being Forward, Prefaces, and Contributor List,
    no Front-Cover Texts, and no Back-Cover Texts.  A copy of the license
    is included in the section entitled "GNU Free Documentation License".

.. 	qnum::
	:start: 1
	:prefix: csp-18-8-

Bir İlçenin Nüfus Yoğunluğunu Bulma
===================================

Verileri arasında ``:`` bulunan bir veri setini ``ayrıştırma (split)`` işlemine tabi tutabiliriz. Aynı zamanda  kelime aralarındaki boşluklara da ayrıştırma işlemi uygulayabiliriz. Eğer İl / İlçe bilgisini boşluklarına göre ayırırsak elimizde ayrı ayrı kullanabileceğimiz il ve ilçe elementlerinden oluşan bir liste olacaktır.

.. We can use **split** to chop up our data by fields, separated by ":".But we can also use it *within*  field, to separate by space.  If we split the city/state by "space", we'd get city and state as two different elements of the list.

Bu bölümde ISTANBUL ilinin 2017 yılında nüfus yoğunluğuna göre hazırlanmış sıralı ilçe detay verilerini kullanacağız. Bütün ilçelerin detaylarını görmek için aşağıdaki *Göster* butonuna tıklayabilirsiniz. Tekrar kapatmak için *Gizle* butonuna tıklayabilirsiniz.


.. reveal:: pol_Data_71
    :showtitle: Göster
    :hidetitle: Gizle
    
    .. raw:: html
    
       <pre id= "istanbul_ilceler.txt">
       Esenyurt, ISTANBUL :5.63 :1 :Avrupa
       Küçükçekmece, ISTANBUL :5.13 :2 :Avrupa
       Bağcılar, ISTANBUL :4.98 :3 :Avrupa
       Ümraniye, ISTANBUL :4.66 :4 :Asya
       Pendik, ISTANBUL :4.65 :5 :Asya
       Bahçelievler, ISTANBUL :3.98 :6 :Avrupa
       Üsküdar, ISTANBUL :3.55 :7 :Asya
       Sultangazi, ISTANBUL :3.52 :8 :Asya
       Gaziosmanpaşa, ISTANBUL :3.31 :9 :Avrupa
       Maltepe, ISTANBUL :3.31 :10 :Asya
       Kartal, ISTANBUL :3.08 :11 :Asya
       Esenler, ISTANBUL :3.02 :12 :Avrupa
       Kadıköy, ISTANBUL :3 :13 :Asya
       Kağıthane, ISTANBUL :2.95 :14 :Avrupa
       Avcılar, ISTANBUL :2.9 :15 :Avrupa
       Fatih, ISTANBUL :2.89 :16 :Avrupa
       Ataşehir, ISTANBUL :2.82 :17 :Asya
       Sancaktepe, ISTANBUL :2.68 :18 :Asya
       Başakşehir, ISTANBUL :2.64 :19 :Avrupa
       Eyüp, ISTANBUL :2.54 :20 :Avrupa
       Sarıyer, ISTANBUL :2.29 :21 :Avrupa
       Sultanbeyli, ISTANBUL :2.2 :22 :Asya
       Beylikdüzü, ISTANBUL :2.09 :23 :Avrupa
       Güngören, ISTANBUL :1.98 :24 :Avrupa
       Zeytinburnu, ISTANBUL :1.91 :25 :Avrupa
       Bayrampaşa, ISTANBUL :1.82 :26 :Avrupa
       Şişli, ISTANBUL :1.82 :27 :Avrupa
       Arnavutköy, ISTANBUL :1.74 :28 :Avrupa
       Tuzla, ISTANBUL :1.68 :29 :Asya
       Beykoz, ISTANBUL :1.67 :30 :Asya
       Çekmeköy, ISTANBUL :1.66 :31 :Asya
       Büyükçekmece, ISTANBUL :1.62 :32 :Avrupa
       Beyoğlu, ISTANBUL :1.57 :33 :Avrupa
       Bakırköy, ISTANBUL :1.48 :34 :Avrupa
       Beşiktaş, ISTANBUL :1.23 :35 :Avrupa
       Silivri, ISTANBUL :1.2 :36 :Avrupa
       Çatalca, ISTANBUL :0.46 :37 :Avrupa
       Şile, ISTANBUL :0.23 :38 :Asya
       Adalar, ISTANBUL :0.01 :39 :Asya
       </pre>

.. activecode:: split_il_ilce1
   
   # Veriler : İl / İlçe bilgisi Nüfus yoğunluğunun yüzdesi ve 
   # ilçenin nüfus yoğunluk sırası olarak verilmiştir.
   ilce = "Kadıköy, ISTANBUL :3 :13 :Asya "
   #ilce verisinin detayları aralarındaki : işaretine göre ayrıştırılıyor.
   veriler = ilce.split(":") 
   print("İlçe bilgilerini yazdıralım")
   print(veriler)


   # Verileri ilk ayırma işleminden sonra 1. Sıradaki verimiz 
   # (index=0) Kadıköy, ISTANBUL olacaktır. Bu veriyi " " (boşluk)
   # ayracı kullanarak tekrar ayırdığımızda ilçe ve il adlarını
   # ayrı ayrı alabileceğiz

   ilce_sehir = veriler[0].split(" ")

   #İlçe adı
   print("İlçe: ", ilce_sehir[0])

   #İl adı
   print("İl: ",ilce_sehir[1]) 

Eğer ilçe il verisinde il adı bölümünde de boşluk varsa ne yapacağız? Ayrıştırdığımız bilgiler hata olacak bu yüzden ayrıştırma işlemi için boşluk yerine ``,`` kullanmak daha güvenli.

.. activecode:: split_il_ilce2
   
   # Veriler : İl / İlçe bilgisi Nüfus yoğunluğunun yüzdesi ve 
   # ilçenin nüfus yoğunluk sırası olarak verilmiştir.

   ilce = "Kadıköy, ISTANBUL :3 :13 :Asya "

   #ilce verisinin detayları aralarındaki : işaretine göre ayrıştırılıyor.
   veriler = ilce.split(":")

   print("İlçe bilgilerini yazdıralım")
   print(veriler)

   # İlçe il verisini ayrışmak için boşluk yerine virgül kullanıyoruz.

   ilce_sehir = veriler[0].split(",")

   #İlçe adı
   print("Ilce : ", ilce_sehir[0])
   
   #İl adı
   print("İl: ",ilce_sehir[1])

Belirli bir durumu kontrol etmek için (örnek: ilçe yoğunluk % bilgisi gibi) mevcut verinin aradığımız veri ile ile eşleşip eşleşmediğini kontrol etmemiz gerekir (örnek: Kadıköy ilçesinin nüfus yoğunluk sırasını bulmak için **ilce = Kadıköy** filtrelemesi yapmamız gerekmektedir.) Bunun için ``find`` işlevini kullanıyoruz. Kullanım şekli ``strName.find(test)`` şeklindedir. Arama işlemi aradığımız verinin ``index (sıra)`` numarasını vermektedir. Eğer aradığımız kelime veya bilgi yoksa ``find`` işlevi  değer olarak -1 dönmektedir.

.. So, to check for particular state, we want to know if the current state name *matches* the one we're looking for.  We can use the ``strName.find(test)`` function to see if the current state is the one we are looking for.  The ``find`` function returns the index of the ``test`` in ``strName`` or -1 if it isn't found.

Şimdi ilçe listemizin olduğu *istanbul_ilceler.txt* dosyasını kullanarak bir ilçe araması yapıp Asya yakasındaki ilçelerin İSTANBUL geneline göre nüfus yoğunluk yüzdesini bulalım. Bunun için Asya yakasında bulunan ilçelerin yüzdelik dilimlerini toplamamız yeterli olacaktır. Bulduğumuz sayı %50 nin üzerinde ise İstanbul'un nufüs oranına göre *Asya yakası daha yoğun nüfusa sahiptir* diyebileceğiz.

.. Now, let's reuse the average code and look for a particular state

.. note::
    Aşağıdaki örnekte tavsiye edilen decimal kütüphanesi tarayıcınız üzerinde kullanılamayacaktır. İlgili kütüphaneyi online olmayan yorumlayıcılar (interpreter) üzerinden kullanabilirsiniz. 

.. activecode:: average25state
   

   # Nufüs yoğunluk yüzdelik degerleri okuyacagimiz icin gelen string veriyi
   # ondalıklı sayıya cevirmek icin decimal ya da float kullanabiliriz. 
   #from decimal import Decimal
 

   # *ilce_dosya* değişkenine verilerimizin bulunduğu dosyayı referans vererek dosyayı açıyoruz.
   ilce_dosya = open("istanbul_ilceler.txt") 
   
   # dosyamızın içindeki bütün verileri satır satır okuyarak *ilce_list* değişkenine verileri atıyoruz.
   ilce_list = ilce_dosya.readlines() 
   
   #okuma işlemi bittikten sonra dosyayı kapatıyoruz.
   ilce_dosya.close() 
   
   #Nufüs yoğunluk değerlerinin toplamını almak için bir değişken oluşturuyoruz.
   toplam = 0 
   
   #Asya yakasındaki ilçelerin sayısını tutmak için bir değişken tanımlıyoruz.
   asya_ilceler = 0 
       
   #ilce_list değişkenine atadığımız ilce listesi üzerinde teker teker kontrol yapacağımızdan
   for ilce in ilce_list:       
       #ilçe bilgilerini ayrıştırıyoruz 0: İlçe Adı, 1: Nufüs yoğunluk yüzdesi, 2: Yoğunluğa göre sıra, 3: Bulunduğu yaka
       ilce_detay = ilce.split(":")
       
       #İlçe Asya yakasında ise kontrolü
       if(ilce_detay[3].strip()=="Asya"): 
           #Eğer Asya yakasında ise Nufüs yoğunluk değerini toplama ekliyoruz.
	   toplam += float(ilce_detay[1])
	   #ve Asya yakasındaki ilçe sayısına 1 ekliyoruz.
   	   asya_ilceler = asya_ilceler + 1
           
   #Asya yakasındaki ilçelerin sayılarına ekrana yazdırıyoruz.
   print("Asya yakasında toplam ",asya_ilceler," ilçe bulunmaktadır.")
	 
   #Eğer Asya yakasındaki ilçe nufüs yoğunluk yüzdesi %50 den fazla ise
   if(float(toplam) > 50) :
	#ekrana Asya yakasının Avrupa yakasına göre daha yoğun nüfusu olduğu bilgisini yazıdırıyoruz
	print ("% ", toplam, " Nüfus yoğunluğu ile Asya yakasında Avrupa yakasına göre daha fazla insan yaşadığını anlıyoruz.")
   else:
	print("% ", toplam, " Nüfus yoğunluğu ile Asya yakasında Avrupa yakasına göre daha az insanın yaşadığını anlıyoruz.")


Asya yakasında bulunan ilçeleri bulduk, Peki ya Asya yakasında bulunan ilçelerden adında “ka” geçen ilçelerin listesini almak istersek ne yapmamız gerekir?

.. activecode:: average10states
   :nocodelens:

   # *ilce_dosya* değişkenine verilerimizin bulunduğu dosyayı referans vererek dosyayı açıyoruz.
   ilce_dosya = open("istanbul_ilceler.txt") 
   
   # dosyamızın içindeki bütün verileri satır satır okuyarak *ilce_list* değişkenine verileri atıyoruz.
   ilce_list = ilce_dosya.readlines() 
   
   #okuma işlemi bittikten sonra dosyayı kapatıyoruz.
   ilce_dosya.close()
   
   #içerisinde ka geçen ilçeleri filtreleyeceğiz.
   arama_kriteri = "Ka"

   #Adında arama kriterinde belirlitilen veri geçen ilçelerin sayısını atayacağımız bir değişken tanımlıyoruz.
   toplam = 0
   
   #ilce_list değişkenine atadığımız ilce listesi üzerinde teker teker kontrol yapacağımızdan
   for ilce in ilce_list:       
       #ilçe bilgilerini ayrıştırıyoruz 0: İlçe Adı, 1: Nufüs yoğunluk yüzdesi, 2: Yoğunluğa göre sıra, 3: Bulunduğu yaka
       ilce_detay = ilce.split(":")
       print(ilce_detay[0])

       #Adında arama kriterim olan ka geçip geçmediğini kontrol ediyoruz
       if(ilce_detay[0].find(arama_kriteri) > -1 ):
	   #Eğer İlçenin adında ka geçiyorsa toplamı 1 arttırıyoruz.
           toplam += 1

   #İstanbuldaki ilçelerin arasında adında ka geçenlerin adedini yazıyoruz.
   print("İSTANBUL ilinde adının içerisinde ",arama_kriteri," geçen toplam ",toplam ," ilçe bulunmaktadır.")
.. What states have the highest average pollution values?  What do you think is most related to pollution: Population, area, or wealth?  Does it differ by PM 2.5 and PM 10?  For a list of the state two-letter abbreviations see http://www.50states.com/abbreviations.htm#.VJCB9r5NsXc.



.. parsonsprob:: 18_6_1_avg26

   Aşağıdaki kod bloklarını aşağıya doğru sürükleyip bırakarak gerekli kod bloğunu oluşturun.
   -----
   ilce_dosya = open("istanbul_ilceler.txt") 
   ilce_list = ilce_dosya.readlines() 
   ilce_dosya.close()
   =====
   toplam = 0 
   asya_ilceler = 0 
   =====
   for ilce in ilce_list:       
    ilce_detay = ilce.split(":")
       
    if(ilce_detay[3].strip()=="Asya"): 
     asya_ilceler = asya_ilceler + 1
   =====    
   print("Asya yakasında toplam ",asya_ilceler," ilçe bulunmaktadır.")
   if(float(toplam) > 50) :
    print ("% ", toplam, " Nüfus yoğunluğu ile Asya yakasında Avrupa yakasına göre daha fazla insan yaşadığını anlıyoruz.")
   =====    
    else:
      print("% ", toplam, " Nüfus yoğunluğu ile Asya yakasında Avrupa yakasına göre daha az insanın yaşadığını anlıyoruz.")


