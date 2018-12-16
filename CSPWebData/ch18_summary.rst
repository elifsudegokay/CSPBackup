..  Copyright (C)  Mark Guzdial, Barbara Ericson, Briana Morrison
    Permission is granted to copy, distribute and/or modify this document
    under the terms of the GNU Free Documentation License, Version 1.3 or
    any later version published by the Free Software Foundation; with
    Invariant Sections being Forward, Prefaces, and Contributor List,
    no Front-Cover Texts, and no Back-Cover Texts.  A copy of the license
    is included in the section entitled "GNU Free Documentation License".

.. setup for automatic question numbering.

.. 	qnum::
	:start: 1
	:prefix: csp-18-9-


Ünite 11 ~ Kavram Özeti
============================

.. Chapter 18 included the following concepts from computing.

Bu bölüm bilgisayar bilimleri ile ilgili aşağıdaki kavramları içermektedir.

..	index::
    single: close
    single: comment
    single: find
    single: open
    single: split


- **Yorum ~ Açıklama ~ Comment** - Kod açıklamaları Python dilinde # ile başlamaktadır. Bilgisayar # ile başlayan herşeyi yok saymaktadır. Hatırlayacağınız gibi açıklamalar adında anlaşıldığı gibi kodu yazan yada inceleyen kişilere bırakılmış notlardır

Python Anahtar Kelimelerinin ve İşlevlerinin Özeti
------------------------------------------- 
- **Close** - ``close`` yordamı üzerinde işlem yapıldıktan sonra dosyayı kapatma işlemi için kullanılmaktadır.  
- **Find** - ``find`` fonksiyonu ``strName.find(test)`` şeklinde kullanılır. Aradığınız kelime, harf veya hecenin bulunduğu sırayı geri döndürür, eğer bulunmuyorsa geri dönen değer ``-1`` olacaktır.
- **Open** -  ``open`` işlevi işlem yapmak için kullanacağımız dosyayı açma yani okuma işlemi için kullanılmaktadır.
- **Split** - ``split`` işlevi vermiş olduğunuz karaktere göre ( “:”, “,”, “.”, “ “ v.s.) cümleyi parçalara ayırıp liste halinde geri döndürür. Örnek olarak ``mesaj = "Nora, Jones, 15"`` -> ``mesaj.split(",")``  bize dönen veri ``['Nora', 'Jones', '15']`` olacaktır.

- **Strip** - ``strip`` işlevi karakter dizisi türünden bir değerde belirttiğiniz karakterlerin kaldırılması için kullanılmaktadır. Girdi olarak bir değer verilmezse karakter dizisinin sonundaki enter karakterini (crlf) kaldırmaktadır.

.. - **Yorum ~ Comment** - A comment in Python starts with a ``#`` and the computer will ignore everything from that character to the end of that line.  Comments are used to explain your code to people.

.. Summary of Python Keywords and Functions
------------------------------------------- 
.. - **Close** - The ``close`` procedure closes a file after you are done processing it.  
.. - **Find** - The ``find`` function is used like this ``strName.find(test)``.  It returns the index of ``test`` in ``strName`` if it is found and -1 if it is not found.
.. - **Open** - The ``open`` procedure opens the passed file for either reading or writing.  
.. - **Split** - The ``split`` function returns a list of strings separated by a specified character.  For example, if ``message = "Nora, Jones, 15"`` then ``message.split(",")`` w.. ould return ``['Nora', 'Jones', '15']``.
