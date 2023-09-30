# ***Découpage Symetrique:***

on va prendre le pôle avec le plus de machine afin d'établir le découpage d'adressage adequate : pôle informatique = 50 equipements

donc il nous faut au minimun 50 adresses grace la table des puissance de 2 je sais que `2^6 = 64` donc j'aurais 64 adresses disponible par sous reseau pour 62 equipements

le CIDR est equal a `2^5 = 32 - 6 = 26` donc `CIDR /26`


| Nom du Pole | Adresse réseau | Adresse de broadcast | Adresse de début de plage | Adresse de fin de plage |
|:-----|:-----|:----|:-----|:-----|
|Le Pôle informatique (6 bureaux, environ 50 équipements au total) | 172.16.1.0/26 | 172.16.1.63 | 172.16.1.1 | 172.16.1.62 |
|Le Pôle développement (6 bureaux, environ 12 équipements au total) | 72.16.1.64/26 | 172.16.1.127 | 172.16.1.65 | 172.16.1.126 |
|Le Pôle Administratif (4 bureaux, environ 20 équipements au total) | 172.16.1.128/26 | 172.16.1.191 | 172.16.1.130 | 172.16.1.190 |
|Le Pôle Technicien (4 bureaux, environ 15 équipements au total) | 172.16.1.192/26 | 172.16.2.0| 172.16.1.193 | 172.16.1.255 |


# ***Découpage Asymetrique:***

on va calculer pour chaque pôle le nombre d adresse par rapport aux equipements en prenant les pôles ayant le plus d'équipements en 1er: 

 - le Pôle informatiques ( 6 bureaux, environ 50 équipements au totals ) : `2^6 = 64` adresses du coup CIDR de `2^5 = 32 - 6 = 26` donc `CIDR /26`

 - Le Pôle Administratif ( 4 bureaux, environ 20 équipements au totals ) : `2^5 = 32` adresses du coup CIDR de `2^5 = 32 - 5 = 27` donc `CIDR /27` 

 - Le Pôle Technicien (4 bureaux, environ 15 équipements au total) : `2^5 = 32` adresses du coup CIDR de `2^5 = 32 - 5 = 27` donc `CIDR /27` 

 - Le Pôle développement (6 bureaux, environ 12 équipements au total) : `2^4 = 16` adresse du coup CIDR de `2^5 = 32 - 4 = 28` donc `CIDR /28`

 | Nom du Pole | Adresse réseau | Adresse de broadcast | Adresse de début de plage | Adresse de fin de plage |
|:-----|:-----|:----|:-----|:-----|
|Le Pôle informatique (6 bureaux, environ 50 équipements au total) | 172.16.1.0/26 | 172.16.1.63 | 172.16.1.1 | 172.16.1.62 |
| Le Pôle Administratif (4 bureaux, environ 20 équipements au total) | 72.16.1.64/27 | 172.16.1.95 | 172.16.1.65 | 172.16.1.94 |
| Le Pôle Technicien (4 bureaux, environ 15 équipements au total) | 172.16.1.96/27 | 172.16.1.127 | 172.16.1.97 | 172.16.1.126 |
|Le Pôle développement (6 bureaux, environ 12 équipements au total) | 172.16.1.128/28 | 172.16.1.144| 172.16.1.129 | 172.16.1.143 |
