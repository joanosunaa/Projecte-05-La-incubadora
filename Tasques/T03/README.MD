## 🎯 Objectius de la formació

En acabar aquesta formació, haureu de ser capaços de respondre a aquestes preguntes **amb fets i configuracions reals**:


### ❓ Com funciona el protocol FTP?

El **protocol FTP (File Transfer Protocol)** és un protocol de la capa d’aplicació que permet transferir fitxers entre un client i un servidor a través d’una xarxa TCP/IP.

Característiques principals:
- Utilitza **dues connexions TCP**:
  - **Connexió de control** (port 21): per enviar ordres (login, llistar fitxers, canviar directoris…)
  - **Connexió de dades**: per transferir fitxers o llistes de directoris
- Les dades i credencials **viatgen en text pla** (no xifrat)
- És simple però **insegur** en entorns moderns


### ❓ Quina diferència hi ha entre el mode actiu i el mode passiu?

**Mode actiu:**
- El client obre la connexió de control cap al servidor (port 21)
- El servidor obre la connexió de dades cap al client
- Problemes habituals amb **firewalls i NAT**, ja que el servidor inicia connexions cap al client

**Mode passiu:**
- El client obre tant la connexió de control com la de dades
- El servidor indica quin port utilitzarà per a la connexió de dades
- És el mode **més utilitzat actualment** perquè evita problemes amb firewalls

📌 **Conclusió:**  
El mode passiu és més compatible i segur en xarxes modernes.


### ❓ Implementació d’un servidor FTP segur

Un servidor FTP segur es pot implementar mitjançant **FTPS (FTP sobre TLS/SSL)**.

Mesures clau:
- Xifrat de la connexió amb **TLS**
- Ús de certificats digitals
- Desactivació de connexions anònimes
- Limitació d’usuaris i permisos
- Ús de firewall per restringir ports

Exemples de servidors FTP segurs:
- **vsftpd**
- **ProFTPD**
- **FileZilla Server**


### ❓ Protocol SFTP com alternativa al FTP tradicional

**SFTP (SSH File Transfer Protocol)** és un protocol de transferència de fitxers que funciona sobre **SSH**.

Avantatges:
- Connexió totalment **xifrada**
- Utilitza **un sol port (22)** 
- Autenticació mitjançant:
  - Usuari i contrasenya
  - Claus SSH
- Més segur i fàcil de gestionar que FTP/FTPS

📌 **Conclusió:**  
SFTP és l’alternativa **recomanada** al FTP tradicional.


### ❓ Engabiat d’usuaris en connexions SFTP

L’**engabiament (chroot)** permet limitar un usuari a un directori concret del sistema.

Beneficis:
- L’usuari no pot sortir del seu directori assignat
- Millora la **seguretat**
- Evita accessos no autoritzats al sistema

Implementació habitual:
- Configuració de `sshd_config`
- Assignació de directoris amb permisos controlats
- Ús de `ChrootDirectory`

📌 **Resultat:**  
Cada usuari només pot veure i modificar els seus propis fitxers.


### ❓ Altres mètodes alternatius per la transferència de fitxers

A més de FTP i SFTP, existeixen altres mètodes:

- **SCP**: còpia segura de fitxers via SSH
- **rsync**: sincronització eficient de fitxers locals o remots
- **WebDAV**: transferència via HTTP/HTTPS
- **Cloud storage**: Google Drive, OneDrive, S3
- **HTTP/HTTPS**: descàrrega i pujada de fitxers via web

📌 **Elecció del mètode** depèn de:
- Seguretat requerida
- Volum de dades
- Automatització
- Entorn de xarxa



