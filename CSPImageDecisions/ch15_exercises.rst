..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".


.. setup for automatic question numbering.

.. 	qnum::
	:start: 1
	:prefix: 15-6-

Ünite 9 ~ Değerlendirme Soruları
--------------------

#.

    .. tabbed:: ch9ex1t

        .. tab:: Soru

            Dikdörtgen çizen turtle fonksiyonu yazınız.

            .. activecode:: ch15ex1q
                :nocodelens:


        .. tab:: Cevap

	    .. activecode::  ch15ex1a
                :nocodelens:


                from turtle import *
		def dikDortgenYap(myTurtle,x,y):
    		    myTurtle.forward(x)
    		    myTurtle.left(90)
    		    myTurtle.forward(y)
    		    myTurtle.left(90)
    		    myTurtle.forward(x)
    		    myTurtle.left(90)
    		    myTurtle.forward(y)


		space = Screen()
		alex = Turtle()
		dikDortgenYap (alex,40,80)

		#kareYap(alex,40,40)
		#kareYap(alex,80,80)
		#kareYap(alex,60,60)
		

#.

    .. tabbed:: ch15ex2t

        .. tab:: Soru

            Eskenar üçgen çizen turtle fonksiyonu yazınız.

            .. activecode::  ch15ex2q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch15ex2a
                :nocodelens:

                from turtle import *

		def eskenarUcgenYap(myTurtle,x):
		    myTurtle.forward(x)
    		    myTurtle.left(120)
    		    myTurtle.forward(x)
    		    myTurtle.left(120)
    		    myTurtle.forward(x)
    
		space = Screen()
		alex = Turtle()
		eskenarUcgenYap (alex,80)

#.

    .. tabbed:: ch15ex3t

        .. tab:: Soru

           Kullanıcı “kare” girerse kare, “üçgen” girerse üçgen çizdir. Kare ve üçgen için gereken uzunluk değerlerini kullanıcıdan iste. Bir önceki sorularda yazdığınız fonksiyonları kullanın.

           .. activecode::  ch15ex3q
                :nocodelens:

                


        .. tab:: Cevap

	    .. activecode::  ch15ex3a
                :nocodelens:

                from turtle import *

		def dikDortgenYap(myTurtle,x,y):
		    myTurtle.forward(x)
    		    myTurtle.left(90)
    		    myTurtle.forward(y)
   		    myTurtle.left(90)
   		    myTurtle.forward(x)
 		    myTurtle.left(90)
		    myTurtle.forward(y)

		def eskenarUcgenYap(myTurtle,x):
 		   myTurtle.forward(x)
  		   myTurtle.left(120)
  		   myTurtle.forward(x)
  		   myTurtle.left(120)
  		   myTurtle.forward(x)

		space = Screen()
		alex= Turtle()

		tercih = input("kare ya da üçgen")

		if tercih == "kare":
		    x = int(input("kenarı girin"))
		    dikDortgenYap(alex,x,x)
		elif tercih == "üçgen":
		    x = int(input("kenarı girin"))
		    eskenarUcgenYap(myTurtle,x)
		else:
     		    print("hatalı girdi")   

		#kareYap(alex,40,80)
		#kareYap(alex,40,80)
		#kareYap(alex,40,80)

#.

    .. tabbed:: ch15ex4t

        .. tab:: Soru

            Eğer dikdörtgen yapma fonksiyonunu aynı değerlerle 4 kez arka arkaya çağırırsak ekranda ne görürüz?

            .. activecode::  ch15ex4q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch15ex4a
                :nocodelens:

		from turtle import *

		def dikDortgenYap(myTurtle,x,y):
		    myTurtle.forward(x)
 	            myTurtle.left(90)
   		    myTurtle.forward(y)
  		    myTurtle.left(90)
 		    myTurtle.forward(x)
 		    myTurtle.left(90)
		    myTurtle.forward(y)

		space = Screen()
		alex = Turtle()

		dikDortgenYap (alex,40,80)
		dikDortgenYap (alex,40,80)
		dikDortgenYap (alex,40,80)
		dikDortgenYap (alex,40,80)

#.

    .. tabbed:: ch15ex5t

        .. tab:: Soru

           Eğer 4 kez değil de 10 kez ard arda çağırsaydık ekrana ne basardı? Aşağıdaki şekle benzer bir sonuç almak isteseydik kodu nasıl düzenlememiz gerekirdi?

		.. figure:: Figures/5.png
  	 	 :align: center	

           .. activecode::  ch15ex5q
                :nocodelens:

                


        .. tab:: Cevap

	    .. activecode::  ch15ex5a
                :nocodelens:

                from turtle import *

		def dikDortgenYap(myTurtle,x,y):
    		    myTurtle.forward(x)
    		    myTurtle.left(90)
  		    myTurtle.forward(y)
 		    myTurtle.left(90)
		    myTurtle.forward(x)
  		    myTurtle.left(90)
  		    myTurtle.forward(y)
		
		space = Screen()
		alex = Turtle()

		for i in range(20):
    		    dikDortgenYap (alex,40,80)
    		    alex.left(100)

#.

    .. tabbed:: ch9ex6t

        .. tab:: Soru

            Dikdörtgenlerin rengini ve çizgilerin boyutunu değiştirmek isteseydik nasıl bir yol izlerdik ?

            .. activecode::  ch15ex6q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch15ex6a
                :nocodelens:

                from turtle import *

		def dikDortgenYap(myTurtle,x,y):
		    myTurtle.forward(x)
		    myTurtle.left(90)
		    myTurtle.forward(y)
		    myTurtle.left(90)
		    myTurtle.forward(x)
		    myTurtle.left(90)
		    myTurtle.forward(y)
		space = Screen()
		alex = Turtle()
		renkler=['black','red','blue','yellow']
		for i in range(5):
 		    sonrakiRenk=renkler[(i) % len(renkler)]
		    alex.pensize(i*5)
		    alex.color(sonrakiRenk)
		    dikDortgenYap (alex,40,80)
		    alex.left(100) 

#.

    .. tabbed:: ch15ex7t

        .. tab:: Soru

           Hadi N X N'lik bir oyun tahtası çizelim.

           .. activecode::  ch15ex7q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch15ex7a
                :nocodelens:

                from turtle import *

		def dikDortgenYap(myTurtle,x,y):
		    myTurtle.forward(x)
		    myTurtle.left(90)
		    myTurtle.forward(y)
		    myTurtle.left(90)
		    myTurtle.forward(x)
		    myTurtle.left(90)
		    myTurtle.forward(y)
    
		space = Screen()
		alex = Turtle()
		renkler=['black','red','blue','yellow']
		kareSayisi = 2
		for i in range(kareSayisi):
		    for i in range(kareSayisi):
		        dikDortgenYap (alex,40,40)
		        alex.left(90)  
		        alex.forward(40)
		    alex.left(180)
		    alex.forward(40*kareSayisi)
		    alex.left(90)
		    alex.forward(40)
		    alex.left(90)

		#sondaki fazlalığı silmek için
		alex.left(90)
		alex.color('white')
		alex.forward(40)
