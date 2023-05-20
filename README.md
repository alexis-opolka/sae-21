# SAE-21 - Petits Réseaux

![schema-reseaux](./src/schema-reseau.drawio.svg)

- A faire
- Explication des choix d'architectures, de sécurité, etc.
- Fichiers de Configuration
- Faire des scénarios pour tester les connexions et/ou créer une démarche de tests unitaires

## A faire:

- [x] ACLs
  - [x] Service commercial (VLAN 10)
    - [x] Accès au serveur interne
    - [x] Accès à la DMZ
    - [x] Accès à Internet
    - [x] Pas accès aux autres services internes
  - [x] Service administratif (VLAN 20)
    - [x] Accès au serveur interne
    - [x] Accès à la DMZ
    - [x] Accès à Internet
    - [x] Pas accès aux autres services internes
  - [x] Service technique (VLAN 30)
    - [x] Accès à tous les services internes
    - [x] Ne doit pas pouvoir sortir du réseau Internet
- [x] DMZ
  - [x] Addressage IP publique en 200.0.0.0/24
  - [x] Serveur Web
    - [x] Accessible depuis Internet
    - [x] Contient une page d'acceuil de l'entreprise
  - [x] Serveur DNS
    - [x] Serveur d'autorité de Nom
    - [x] Accessible depuis Internet
- [x] Choisir un nom pour l'entreprise
- [x] Réseau Interne
  - [x] NAT sur le routeur Interne-DMZ
  - [x] Addresses privées sur le réseau (ne doivent pas pouvoir sortir)
  - [x] 3 services
    - [x] Service commercial (VLAN 10)
    - [x] Service administratif (VLAN 20)
    - [x] Service technique (VLAN 30)
    - [x] Services internes (VLAN 200) -> représenté par le serveur Web interne
  - [ ] Accès au réseau interne via des VPN pour les sites délocalisés
    - [X] Accès VPN du site délocalisé 1
    - [ ] Accès VPN du site délocalisé 2
  - [x] Serveur DHCP interne en fonction des VLANs
    - [x] Création des pools d'adresses IP
      - [x] VLAN 10
        - [x] Référencement
          - [x] DNS interne
          - [x] Gateway par défaut
      - [x] VLAN 20
        - [x] Référencement
          - [x] DNS interne
          - [x] Gateway par défaut
      - [x] VLAN 30
        - [x] Référencement
          - [x] DNS interne
          - [x] Gateway par défaut
      - [x] VLAN 200
        - [x] Gateway par défaut
- [x] Sites délocalisés
  - [x] Accès DMZ
  - [x] Accès Internet
  - [x] VPN: Accès réseau interne
- [x] Internet
  - [x] Être accessible par tout le monde
  - [x] Accès à la DMZ
  - [x] Pas accès au réseau interne
  - [x] Pas accès au réseau des sites délocalisés
- [x] Interconnexion et Routage
  - [x] Mise en place d'une solution de routage dynamique
    - [x] BGP (AS: 100, 200, 300, 900)
