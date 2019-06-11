Zadanie 1
---------

![zadanie 1](zadanie-1.svg)

1. Zaprojektuj oraz przygotuj prototyp rozwiązania z wykorzystaniem oprogramowania ``VirtualBox`` lub podobnego. 
Zaproponuj rozwiązanie spełniające poniższe wymagania:
   * Usługodawca zapewnia domunikację z siecią internet poprzez interfejs ``eth0`` ``PC0``
   * Zapewnij komunikację z siecią internet na poziomie ``LAN1`` oraz ``LAN2``
   * Dokonaj takiego podziału sieci o adresie ``172.22.128.0/17`` aby w ``LAN1`` można było zaadresować ``500`` adresów natomiast w LAN2 ``5000`` adresów    
   * Przygotuj dokumentację powyższej architektury w formie graficznej w programie ``DIA``

Zadanie- Rozwiązanie:
---
Podział sieci na 2 podsieci:
---
  * LAN1 172.22.160.0/23 
  * LAN2 172.22.128.0/19

PC0
---
* eth0: Zapewnia usługodawca
* eth1: 172.22.160.1/23
* eth2: 172.22.128.1/19

PC1
---
* eth0: 172.22.160.2/23

PC2
---
* eth0: 172.22.128.2/19

Konfiguracja PC0
---
* Nadanie adresu Ip: ``ip addr add 172.22.160.1/23 dev enp0s8``
* Nadanie adresu Ip: ``ip addr add 172.22.128.1/19 dev enp0s9``

Konfiguracja PC1
---
* Nadanie adresu Ip: ``ip addr add 172.22.160.2/23 dev enp0s3``
* Nadanie routingu: ``ip route add default via 172.22.160.1 dev enp0s3``
* Postawienie interfejsu: ``ip link set enp0s3 up``
* Postawienie interfejsu: ``ip link set enp0s8 up``
* Postawienie interfejsu: ``ip link set enp0s9 up``
* Włączenie ip forwarding: ``echo 1 >/proc/sys/net/ipv4/ip_forward``
* Reguła Masquerade dla Lan1: ``iptables -t nat -A POSTROUTING -s 172.22.160.0/23 -o enp0s3 -j MASQUERADE``
* Reguła Masquerade dla Lan2:`` iptables -t nat -A POSTROUTING -s 172.22.128.0/19 -o enp0s3 -j MASQUERADE``

Konfiguracja PC2
---
* Nadanie adresu Ip: ``ip addr add 172.22.128.2/19 dev enp0s3``
* Nadanie routingu: ``ip route add default via 172.22.128.1/19 dev enp0s3``

Diagram
---
(DIAGRAM.png)
