Konfiguracja route
------------------

* routing
    * dodaj trasę default
    * dodaj trasę przez bramę
    * dodaj trasę przez interfejs
    * usuń trasę
    * zmień trasę
    * pobierz trasę dla adresu
     
ip 
-------------------------
| subcommand    |  polecenie   | opis  |
| ------------- |:-------------| :---------------| 
|   ``route``    |                               | |
|               |   ``ip route add``             | |
|               |   ``ip route del``             | |
|               |   ``ip route add default via 10.0.10.1 (opcjonalne:) dev enp0s3``             |``via adres swojego routera`` |
|               |   ``ip route get 10.0.10.15``             | ``gdzie pakiet zmierza``|
|               |   ``cat /proc/sys/net/ipv4/ip_forward``             | |
|               |   ``echo 1 > /proc/sys/net/ipv4/ip_forward``             | `` nadanie wartosci 1``|


Zadanie
------------

![zadanie 4](cwiczenia4.svg)

1.
   * Przygotuj konfigurację sieci zgodnie z powyższym diagramem, 
   * Przetestuj połączenie pomiędzy wszystkimi elementami sieci
   * Dlaczego połączenie może nie działać
2. Przygotuj konfigurację tak aby została załadowana poprawnie po ponownym uruchomieniu systemu
   * Patrz ``utrwalanie statycznej konfiguracji cwiczenia 2``
   * zwróć uwagę na różnice pomiędzy dydtrybucjami systemu
3. Zainstaluj, uruchom i przetestuj działanie aplikacji ``HTTP_CHAT``
   * aplikacja dostępna w serwisie github ``https://github.com/jkanclerz/http-chat``

Zadanie do domu
---------------

1. Przygotuj konfigurację z zadania 1 wykorzystując inny system operacyjny na komputerze pełniącym rolę routera.
  * debian -> centos lub centos -> debian
  * zapewnij poprawną komunikację pomiędzy PC3 -> PC1
  
  
   KOLEJNOSC DODANIE SIECI W GLOBANYCH USTAWIENIACH>DODANIE SIECI W MASZYNACH NA POZIOMIE VB> IP ADDR.../POSTAIWNIE INTERFEJSU(LINK SET...)
  
