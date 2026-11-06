# Configurations – Routage dynamique RIP

Configuration complète de chaque équipement, exportée depuis le fichier Packet Tracer.
Les mots de passe et numéros de série sont masqués ; les interfaces sans configuration sont omises.
Les fichiers bruts (un par équipement) sont dans [`configs/`](configs/).

## Sommaire

- [Router0](#router0) – Router Router-PT
- [Router1](#router1) – Router Router-PT
- [Router2](#router2) – Router Router-PT
- [Switch0](#switch0) – Switch Switch-PT
- [Switch1](#switch1) – Switch Switch-PT
- [Switch2](#switch2) – Switch Switch-PT
- [Postes et serveurs](#postes-et-serveurs)

## Postes et serveurs

| Nom | Type | Adresse IP | Masque | Passerelle | DNS |
|---|---|---|---|---|---|
| PC0 | Pc | 192.168.10.2 | 255.255.255.0 | 192.168.10.1 | – |
| PC1 | Pc | 192.168.10.3 | 255.255.255.0 | 192.168.10.1 | – |
| PC2 | Pc | 192.168.20.2 | 255.255.255.0 | 192.168.20.1 | – |
| PC3 | Pc | 192.168.20.3 | 255.255.255.0 | 192.168.20.1 | – |
| PC4 | Pc | 192.168.30.2 | 255.255.255.0 | 192.168.30.1 | – |
| PC5 | Pc | 192.168.30.3 | 255.255.255.0 | 192.168.30.1 | – |

## Router0

Router · modèle Router-PT · hostname `Router`

```cisco
!
version 12.2
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
ip cef
no ipv6 cef
!
interface FastEthernet0/0
 ip address 192.168.10.1 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet1/0
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Serial2/0
 ip address 10.0.0.1 255.0.0.0
 clock rate 2000000
!
interface Serial3/0
 no ip address
 clock rate 2000000
 shutdown
!
interface FastEthernet4/0
 no ip address
 shutdown
!
interface FastEthernet5/0
 no ip address
 shutdown
!
router rip
 network 10.0.0.0
 network 192.168.10.0
!
ip classless
!
ip flow-export version 9
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
end
```

## Router1

Router · modèle Router-PT · hostname `Router`

```cisco
!
version 12.2
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
ip cef
no ipv6 cef
!
interface FastEthernet0/0
 ip address 192.168.20.1 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet1/0
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Serial2/0
 ip address 10.0.0.2 255.0.0.0
!
interface Serial3/0
 ip address 11.0.0.1 255.0.0.0
 clock rate 2000000
!
interface FastEthernet4/0
 no ip address
 shutdown
!
interface FastEthernet5/0
 no ip address
 shutdown
!
router rip
 network 10.0.0.0
 network 11.0.0.0
 network 192.168.20.0
!
ip classless
!
ip flow-export version 9
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
end
```

## Router2

Router · modèle Router-PT · hostname `Router`

```cisco
!
version 12.2
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
ip cef
no ipv6 cef
!
interface FastEthernet0/0
 ip address 192.168.30.1 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet1/0
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Serial2/0
 no ip address
 clock rate 2000000
 shutdown
!
interface Serial3/0
 ip address 11.0.0.2 255.0.0.0
!
interface FastEthernet4/0
 no ip address
 shutdown
!
interface FastEthernet5/0
 no ip address
 shutdown
!
router rip
 network 11.0.0.0
 network 192.168.30.0
!
ip classless
!
ip flow-export version 9
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
end
```

## Switch0

Switch · modèle Switch-PT · hostname `Switch`

```cisco
!
version 12.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface Vlan1
 no ip address
 shutdown
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
end
```

## Switch1

Switch · modèle Switch-PT · hostname `Switch`

```cisco
!
version 12.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface Vlan1
 no ip address
 shutdown
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
end
```

## Switch2

Switch · modèle Switch-PT · hostname `Switch`

```cisco
!
version 12.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface Vlan1
 no ip address
 shutdown
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
end
```
