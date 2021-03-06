Struktura adresu IP
-------------------

```192.168.100.192```
```255.255.255.0```

Adres sieci
-----------

1. adres w postaci binarnej
2. maska w postaci binarnej
3. BITAND(Adres ;maska )

Adres rozgłoszeniowy
-----------

1. odwrotnosc maski w postaci binarnej
2. odwrotnosc w postaci decimal
3. BITOR(Adres sieci;odwrotnosc maski decimal)


Podział na równą ilość podsieci
-------------------------------

```2^S >= n```

Chcemy 7 -> 2^3 >= 7, szukamy pierwszej wolnej liczby wiekszej od chcianej

Maska -> 255.255.255.11100000 -> 255.255.255.224 -> /27


Wprowadzenie
------------

------------------------------
| dziesiętnie |  binarnie   | 
| --------- |:-------------| 
| ``10``  | ``1010`` | 
| ``92``  |``1011100`` | 
| ``37``  |``100101`` | 
| ``240`` |``11110000`` | 
| ``192`` |``11000000`` | 
| ``255`` | ``11111111``| 
| ``128`` | ``10000000``| 
| ``168`` |``10101000`` | 


------------------------------
| binarnie |  dziesiętnie   | 
| --------- |:-------------| 
| ``00100000``  | ``32`` | 
| ``11111000``  | ``248``| 
| ``10100000``  | ``160``| 
| ``00110000`` |``48`` | 
| ``10101100`` | ``172``| 
| ``01000000`` |``64`` | 
| ``11111100`` | ``252``| 
| ``01100010`` | ``98``| 
 
Notacja CIDR
------------
 
------------------------------
| maska |  /(X) x - liczba bitów   | 
| --------- |:-------------| 
| ``255.255.255.0``   | ``24``| 
| ``255.128.0.0``     | ``9``| 
| ``255.255.252.0``   | ``22``| 
| ``255.255.254.0``   | ``23``| 
| ``255.255.255.240`` |``28`` | 
| ``255.240.0.0``     | ``12``| 

------------------------------
| CIDR |  Maska   | 
| --------- |:-------------| 
| ``/8``    | ``255.0.0.0``| 
| ``/20``   | ``255.255. | 
| ``/30``   | ``255.255.240.0``| 
| ``/16``   |``255.255.0.0`` | 
| ``/27``   | ``255.255.255.224``| 
| ``/11``   | ``255.224.0.0``| 


Liczba hostów
-------------

------------------------------
| sieć |  liczba   | 
| --------- |:-------------| 
| ``10.0.0.0/8``    | | 
| ``172.16.0.0/16``   | | 
| ``192.168.1.0/24``   | | 
| ``192.168.1.0/27``   | | 
| ``192.168.1.0/29``   | | 
| ``192.168.1.0/31``   | | 

* liczba 0 w masce?


Parametry na podstawie adresu
-----------------------------

Mając dany adres hosta i maskę znajdź:
  * adres sieci
  * początkowy adres hosta w sieci
  * liczbę hostów w zadanej podsieci ```2^(32 bity - bity maski maska) - 2 (siec i broadcast)```
  * końcowy zakres adresu hosta w sieci
  * adres rozgłoszeniowy
  
  ------------------------------
| Parametr |  wartość   | 
| --------- |:-------------| 
| ``ip``    | 192.168.1.145| 
| ``maska``   | 255.255.255.128 | 
| ``adres sieci``   | 192.168.1.128|
| ``liczba hostów``   | 126|
| ``host - min``   |192.168.1.129 | 
| ``host - max``   |192.168.1.254 | 
| ``broadcast``   |192.168.1.255 | 
 

