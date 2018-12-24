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
	:prefix: 25-10-

Ünite 12 - Genel Tekrar Soruları
--------------------

#.

    .. tabbed:: ch25ex1t

        .. tab:: Soru

            Aşağıdaki hatalı kodu düzeltin.

            .. activecode:: ch25ex1q
                :nocodelens:

                x = (input("bir sayı giriniz"))
		y = (input("başka bir sayı giriniz"))

		sonuc = x * x + y * y
		print(Sonuc		
		

        .. tab:: Cevap

	    .. activecode::  ch25ex1a
                :nocodelens:

                x = int (input("bir sayı giriniz"))
		y = int (input("başka bir sayı giriniz"))

		sonuc = x * x + y * y
		print(sonuc)
		

#.

    .. tabbed:: ch25ex2t

        .. tab:: Soru

            Kullanıcıdan aldığınız 3 sayıdan en küçük olanı ekrana bastırınız.

            .. activecode::  ch25ex2q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch25ex2a
                :nocodelens:
		
		x = int (input("bir sayı giriniz"))
                y = int (input("başka bir sayı giriniz"))
		z = int (input("başka bir sayı daha giriniz"))
		
		if x < y and x < z:
		    print("en küçük: " , x)
		elif y < x and y < z:
		    print("en küçük: " , y)
		elif z < x and z < y:
		    print("en küçük: " , z)

#.

    .. tabbed:: ch25ex3t

        .. tab:: Soru

           Bir listenin içindeki bütün negatif sayıları 0 yapan bir programı yazınız. 

           .. activecode::  ch25ex3q
                :nocodelens:

                


        .. tab:: Cevap

	    .. activecode::  ch25ex3a
                :nocodelens:

                liste=[6,-2,7,-1,9]

		
		for i in range(len(liste)):
		    if liste[i] < 0:
			liste[i] = 0
		print(liste)


#.

    .. tabbed:: ch25ex4t

        .. tab:: Soru

            Verilen bir listeyi sıralayan program yazınız.

            .. activecode::  ch25ex4q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch25ex4a
                :nocodelens:
		
		liste = [6, 3, 7, 2, 9]
		for i in range(len(liste)):
		    min = i
		    for j in range(i,len(liste)):
			if liste[j] < liste[min]:
			    min = j
		    temp = liste[i]
		    liste[i] = liste[min]
		    liste[min] = temp

		print(liste)

#.

    .. tabbed:: ch25ex5t

        .. tab:: Soru

           Girdi olarak bir liste alan ve aldığı listedeki çift sayıları döndüren bir işlev yazınız.

           .. activecode::  ch25ex5q
                :nocodelens:

                

		

        .. tab:: Cevap

	    .. activecode::  ch25ex5a
                :nocodelens:

                def ciftSayiSec(liste):
		    yeniListe= []
		    for sayi in liste:
			if sayi % 2 == 0:
			    yeniListe.append(sayi)
		    return yeniListe

		liste=[1,2,3,4,5]
		yeni = ciftSayiSec(liste)
		print(yeni)

#.

    .. tabbed:: ch25ex6t

        .. tab:: Soru

            Aşağıdaki resmi ("gal2.jpg") siyah beyaz yapan bir program yazınız.  

             .. raw:: html
	      
 
		  <center>
		  <img src="../_static/gal2.jpg" id="gal2.jpg">
		  </center>

            .. activecode::  ch25ex62q
                :nocodelens:

                



		

        .. tab:: Cevap

	    .. activecode::  ch25ex6a
                :nocodelens:

                from image import *

		resim = Image("gal2.jpg")

		for x in range(resim.getWidth()):
		    for y in range(resim.getHeight()):
			p = resim.getPixel(x, y)
			r = p.getRed()
			g = p.getGreen()
        		b = p.getBlue()
        		avg = (r + g + b) // 3
	
			yeniPiksel = Pixel(avg, avg,avg)
        		resim.setPixel(x, y, yeniPiksel)
		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

	
#.

    .. tabbed:: ch25ex7t

        .. tab:: Soru

           Turtle kütüphanesi ile F harfini ekrana çizen program yazın.

           .. activecode::  ch25ex7q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch25ex7a
                :nocodelens:

		from turtle import *
		space = Screen()
		alex = Turtle()
		alex.left(90)
		alex.forward(100)
		alex.right(90)
		alex.forward(50)
		alex.penup()
		alex.goto(0,60)
		alex.pendown()
		alex.forward(50)


.. raw:: html

    <br><br><br><table><tr><td><img src="../_static/beach.jpg" id="beach.jpg"></td><td><img src="../_static/vangogh.jpg" id="vangogh.jpg"></td><td><img src="../_static/swan.jpg" id="swan.jpg"></td></tr><tr><td>beach.jpg</td><td>vangogh.jpg</td><td>swan.jpg</td></tr></table><br><br><br><table><tr><td><img src="../_static/gal2.jpg" id="gal2.jpg"></td><td><img src="../_static/eiffel.jpg" id="eiffel.jpg"></td><td> </td><td><img src="../_static/lady_tiny.png" id="lady_tiny.png"></td></tr><tr><td>gal2.jpg</td><td>eiffel.jpg</td><td> </td><td>lady_tiny.png</td></tr></table><br><br><br><table><tr><td><img src="../_static/puppy.jpg" id="puppy.jpg"></td><td><img src="../_static/motorcycle.jpg" id="motorcycle.jpg"></td><td><img src="../_static/gal1.jpg" id="gal1.jpg"></td></tr><tr><td>puppy.jpg</td><td>motorcycle.jpg</td><td>gal1.jpg</td></tr>
   </table><br><br><br>
   <table><tr><td><img src="../_static/kitten.jpg" id="kitten.jpg"></td><td><img src="../_static/girl.jpg" id="girl.jpg"></td><tr><td>kitten.jpg</td><td>girl.jpg</td></tr></tr>
   </table><br><br><br><br><br>

