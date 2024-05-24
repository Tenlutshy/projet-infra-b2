# Projet Infra

## R.A.C.I.

| Tâches   | Réalisateur | Approbateur | Consulté | Informé |
| ------------------- | -------------- | -------------- | -------------- | -------------- |
| Analyze             | F  | F   | C   | C  |
| Planification  | F    | F            | C             | C             |
| Réalisation  | F    | F            | C             | C             |
| Validation recette      | F/C    | C            | F/C             | F/C             |

---

## Tableau des VLANs

- Association VLAN <> réseau IP 

| VLAN              | VLAN 10 `client`    | VLAN 20 `serv`    | VLAN 30 `dir1`    |
| ----------------- | ------------------- | ----------------- | ----------------- |
| Réseau IP associé | `10.33.10.0/23`     | `10.33.20.0/28`   | `10.30.30.0/27`   |

---

## Tableau d'adressage

| Machine - Réseau  | `10.33.10.0/24` | `10.33.20.0/28` | `10.33.30.0/29` |
| ----------------- | --------------- | --------------- | --------------- |
| `ROUTEUR`         | `10.33.10.254`  | `10.33.20.14`   | `10.33.30.6`    |
| `AD/DHCP`         | ❌              | ❌             | `10.33.30.1`    |
| `SRV.Applicatif`  | ❌              | `10.33.20.1`    | ❌             |
| `SRV.Fichier`     | ❌              | `10.33.20.2`    | ❌             |
| `PC.CL1`          | `10.33.10.1`     | ❌             | ❌             |
| `PC.CL2`          | `10.33.10.2`     | ❌             | ❌             |
| `PC.CL3`          | `10.33.10.3`     | ❌             | ❌             |
| `PC.CL4`          | `10.33.10.4`     | ❌             | ❌             |
