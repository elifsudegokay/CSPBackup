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

Ünite 10 ~ Değerlendirme Soruları
--------------------
Bu bölümdeki tüm sorularda, sorularda belirtilen görsellerin  yanısıra aşağıda **dosya yollarıyla (path)** ile  birlikte verilen görselleri de kullanabilirsiniz. 



.. raw:: html

    <br><br><br><table><tr><td><img src="../_static/beach.jpg" id="beach.jpg"></td><td><img src="../_static/vangogh.jpg" id="vangogh.jpg"></td><td><img src="../_static/swan.jpg" id="swan.jpg"></td></tr><tr><td>beach.jpg</td><td>vangogh.jpg</td><td>swan.jpg</td></tr></table><br><br><br><table><tr><td><img src="../_static/gal2.jpg" id="gal2.jpg"></td><td><img src="../_static/eiffel.jpg" id="eiffel.jpg"></td><td> </td><td><img src="../_static/lady_tiny.png" id="lady_tiny.png"></td></tr><tr><td>gal2.jpg</td><td>eiffel.jpg</td><td> </td><td>lady_tiny.png</td></tr></table><br><br><br><table><tr><td><img src="../_static/puppy.jpg" id="puppy.jpg"></td><td><img src="../_static/motorcycle.jpg" id="motorcycle.jpg"></td><td><img src="../_static/gal1.jpg" id="gal1.jpg"></td></tr><tr><td>puppy.jpg</td><td>motorcycle.jpg</td><td>gal1.jpg</td></tr>
   </table><br><br><br>
   <table><tr><td><img src="../_static/kitten.jpg" id="kitten.jpg"></td><td><img src="../_static/girl.jpg" id="girl.jpg"></td><tr><td>kitten.jpg</td><td>girl.jpg</td></tr></tr>
   </table><br><br><br><br><br>





#.

    .. tabbed:: ch9ex11t

        .. tab:: Soru

            Resmin piksellerinin değerleri ile oynayacak bir kod yazınız

             .. raw:: html
	      
 
		  <center>
		  <img src="../_static/beach.jpg" id="beach.jpg" align="middle">
		  </center>
		   
		  


	    .. activecode:: ch15ex11q
                :nocodelens:


        .. tab:: Cevap

	    .. activecode::  ch15ex11a
                :nocodelens:


                # ADIM 1: Image kütüphanesini kullan
		from image import *

		# ADIM 2: Resmi seç
		resim = Image("beach.jpg")

		# ADIM 3: Bütün pikselleri teker teker gez
		pikseller = resim.getPixels()
		for p in pikseller:

		    # ADIM 4: renk veriyi al.
    		    r = p.getRed()

    		    # ADIM 5: rengi değiştir
		    p.setRed(r * 1.5)

    		    # ADIM 6: resmi güncelle
    		    resim.updatePixel(p)
    
    		    #update other pixels here

		# ADIM 7: sonucu göster
		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)
		

#.

    .. tabbed:: ch15ex21t

        .. tab:: Soru

            Aşağıdaki kodu çalıştırdığımız zaman sizce resimde nasıl bir değişiklik olur ? 

             .. raw:: html
	      
 
		  <center>
		  <img src="../_static/vangogh.jpg" id="vangogh.jpg">
		  </center>

            .. activecode::  ch15ex22q
                :nocodelens:

		from image import *

		resim = Image("vangogh.jpg")
		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

		limit = min(resim.getWidth(), resim.getHeight())

		for x in range(limit):
		    for y in range(limit):
		
			p = resim.getPixel(x, y)
			resim.setPixel(y, x, p)

		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

                

        .. tab:: Cevap

	    .. activecode::  ch15ex22a
                :nocodelens:

                from image import *

		resim = Image("vangogh.jpg")
		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

		limit = min(resim.getWidth(), resim.getHeight())

		for x in range(limit):
		    for y in range(limit):
		
			p = resim.getPixel(x, y)
			resim.setPixel(y, x, p)

		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

#.

    .. tabbed:: ch15ex32t

        .. tab:: Soru

            Aşağıdaki görselin ("beach.jpg") sol üst köşesinden 50x50’lik bir parçayı silen kodu yazın.

             .. raw:: html
	      
 
		  <center>
		  <img src="../_static/beach.jpg" id="beach.jpg" align="middle">
		  </center>
           .. activecode::  ch15ex32q
                :nocodelens:

		



                


        .. tab:: Cevap

	    .. activecode::  ch15ex32a
                :nocodelens:

                from image import *

		resim = Image("beach.jpg")

		for x in range(50):
    		    for y in range(50):
        		p = resim.getPixel(x,y)
        		p.setRed(255)
        		p.setGreen(255)
        		p.setBlue(255)
        		resim.updatePixel(p)    
    

		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

#.

    .. tabbed:: ch15ex42t

        .. tab:: Soru

            Aşağıdaki resmi ("vangogh.jpg") ters çeviren (180 derece döndüren)  kodu yazınız.

             .. raw:: html
	      
 
		  <center>
		  <img src="../_static/vangogh.jpg" id="vangogh.jpg">
		  </center>

            .. activecode::  ch15ex42q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch15ex42a
                :nocodelens:

		from image import *

		resim = Image("vangogh.jpg")
		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

		maxY=resim.getHeight()
		maxX=resim.getWidth()

		for y in range(int(maxY/2)):
    		    for x in range(maxX):

        		p1 = resim.getPixel(x, y)
        		p2 = resim.getPixel(x, maxY-y-1)

        		resim.setPixel(x, maxY-y-1, p1)
        		resim.setPixel(x,y, p2)
    		    #pencere = ImageWin(resim.getWidth(),resim.getHeight())
    		    #resim.draw(pencere)

		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

#.

    .. tabbed:: ch15ex52t

        .. tab:: Soru

            Birinci görselin ("lady_tiny.png") kenarlarındaki boşluğu silerek diğer görselin ("eiffel.jpg") içine yerleştiren kodu yazınız.

             .. raw:: html
	      
 
		  
		  <img style="float: left;" src="../_static/lady_tiny.png" id="lady_tiny.png">
		  <center>
		  <img src="../_static/eiffel.jpg" id="eiffel.jpg">
		  </center>

	

           .. activecode::  ch15ex52q
                :nocodelens:

                


        .. tab:: Cevap

	    .. activecode::  ch15ex52a
                :nocodelens:

                from image import *

		# CREATE THE IMAGES
		resim1 = Image("lady_tiny.png")
		resim2 = Image("eiffel.jpg")

		# LOOP THROUGH ALL THE PIXELS IN IMG1
		for x in range(resim1.getWidth()):
    		    for y in range(resim1.getHeight()):
        		p1 = resim1.getPixel(x, y)
        		r1 = p1.getRed()
        		g1 = p1.getGreen()
        		b1 = p1.getBlue()

        		# Piksel beyaz mı değil mi kontrol et
        		if r1 < 250 and g1 < 250 and b1 < 250:
            		    # pikseli diğer resme kopyala
            		    resim2.setPixel(x, y + 130, p1)


		pencere = ImageWin(resim2.getWidth(),resim2.getHeight())
		resim2.draw(pencere)

#.

    .. tabbed:: ch9ex62t

        .. tab:: Soru

            Aşağıda arka planı beyaz olan vesikalık bir fotoğraf ("gal2.jpg") verilmiştir, bu fotoğrafın arka planını mora dönüştürünüz. Morun RGB değeri (128,0,128). 

             .. raw:: html
	      
 
		  <center>
		  <img src="../_static/gal2.jpg" id="gal2.jpg">
		  </center>

            .. activecode::  ch15ex62q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch15ex62a
                :nocodelens:

                 
		from image import *

		resim = Image("gal2.jpg")

		for x in range(resim.getWidth()):
    		    for y in range(resim.getHeight()):
        		p = resim.getPixel(x, y)
        		r = p.getRed()
        		g = p.getGreen()
        		b = p.getBlue()

        		if r >250 and g > 250 and b >250:
          		    yeniPiksel = Pixel(128, 0, 128)
          		    resim.setPixel(x, y, yeniPiksel)

		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)

#.

    .. tabbed:: ch15ex72t

        .. tab:: Soru

            Bir resimdeki nesnelerin şekillerini ortaya çıkarma ve geri kalan her şeyin siyaha dönüştürme işlemine kenar tespiti (edge detection) denir. Genelde kenarlar, birbirine komşu iki pikselin ortalama renk değerleri arasındaki farkın yüksek olduğu yerlerdedir. Bu bilgileri ve aşağıdaki fotoğrafı ("swan.jpg") da kullanarak kenar tespit eden bir program yazınız

             .. raw:: html
	      
 
		  <center>
		  <img src="../_static/swan.jpg" id="swan.jpg">
		  </center>

           .. activecode::  ch15ex72q
                :nocodelens:

                

        .. tab:: Cevap

	    .. activecode::  ch15ex72a
                :nocodelens:

                from image import *


		resim = Image("swan.jpg")


		for x in range(resim.getWidth() - 1):
    		    for y in range(resim.getHeight()):
       			p = resim.getPixel(x, y)
        		p2 = resim.getPixel(x + 1, y)
        		r1 = p.getRed()
        		g1 = p.getGreen()
        		b1 = p.getBlue()
        		ortalama1 = (r1 + g1 + b1) / 3
        		r2 = p2.getRed()
        		g2 = p2.getGreen()
        		b2 = p2.getBlue()
        		ortalama2 = (r2 + g2 + b2) / 3

       
        		if abs(ortalama2 - ortalama1) > 10:
            		    yeniPiksel = Pixel(0, 0, 0)
        		else:
            		    yeniPiksel = Pixel(255, 255, 255)

       
        		resim.setPixel(x, y, yeniPiksel)


		pencere = ImageWin(resim.getWidth(),resim.getHeight())
		resim.draw(pencere)
