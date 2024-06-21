Q.2.1.1


On va créer un compte personnel du nom de Yanis


![2024-06-21 10_58_29-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/069f2bce-286a-4e7a-82c4-ddb37052a208)



![2024-06-21 10_59_13-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/6910aa7d-270c-4449-b85e-c736678f0962)



Q.2.1.2


On vas rajouter le compte Yanis aux groupes `sudo`, 


![2024-06-21 11_01_31-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/f79ec2a5-2621-4ddc-9172-a502db228912)



Q.2.2.1

Pour désactiver l'accès à distance en root, on vas se rendre sur le fichier `/etc/ssh/sshd_config` et modifier la ligne `PermitRootLogin` avec à la fin de celle-ci *no*


![2024-06-21 11_04_21-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/4b63ff3e-36f8-4650-bbd2-3e36c71c6062)





![2024-06-21 11_06_27-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/4a82b1d5-d32c-4ab7-a3da-7a81d205e57a)



![2024-06-21 11_07_26-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/6ad4e2a9-3d74-4f96-8afe-457bed49c000)


Q.2.2.2

Pour autoriser l'accès à distance on vas modifier la ligne AllowUsers ou la créer dans la cas présent comme ci dessous
`AllowUsers Yanis`



![2024-06-21 11_10_54-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/664f6ab7-94c7-4aa7-8186-4a498fcba4f2)




Q.2.2.3

On vas utiliser la commande `ssh-keygen -t rsa -b 4096` pour génerer une clé et envoyer la clé sur le serveur avec la commande `ssh-copy-id`




![2024-06-21 11_19_23-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/9185d04b-040e-4314-87e0-270dd880a324)


On vas modifier la ligne `PasswordAuthenication` avec à la fin de celle-ci *no* pour désactiver l'identification par mot de passe 
Et on vas  modifier la ligne `PubkeyAuthentication` avec à la fin de celle-ci *yes* pour une authentification par clé valide  

![2024-06-21 11_23_42-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/d8dfaadb-d9a0-489d-9ca0-acb033036f0b)




![2024-06-21 11_12_25-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/9fa012b5-3ab3-47a0-ac98-14a51ab28b60)

On vas redémarrer le service SSH 
On peut executer `sshd -t` pour vérifier que tout fonctionne 


Q.2.3.1 


![2024-06-21 11_50_10-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/138a1515-449c-46c4-92a8-1c63b7215b5d)


Q.2.3.2

![2024-06-21 11_50_46-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/5452b925-b9e7-4781-94a5-80d4d822279a)



Q.2.3.3


On partionnne le disque avec la commande 

`fdisk /dev/sdb`

On ajoute le nouveau disque au RAID avec la commande :

`mdadm --manage /dev/md0 --add /dev/sdb1`

![2024-06-21 11_57_59-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/ff46d21c-4a4d-4ad0-ad54-3818c6a27b59)

On controle que tout soit ok avec la commande :

`mdadm --detail /dev/md0`

![2024-06-21 12_38_54-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/9e6ab5db-943b-4d72-a903-71bb106c21fe)


Q.2.3.4


On créer un volume logique ( Storage pour moi )

![2024-06-21 12_26_12-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/6b88530e-26a0-445f-ae36-ca5ec21ad4f5)

On formate le nouveau volume logique 

![2024-06-21 12_28_03-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/bd02561a-9a22-48cf-85a5-893810025229)

On le monte volume automatiquement au démarage dans l'emplacement ciblé 


![2024-06-21 12_29_31-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/2a4a074d-976c-4ccf-9580-2af11f659a2e)


Q.2.3.5

La commande est `vgisplay` ou `vgs` donc 1,79GB


![2024-06-21 12_33_28-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/94482b49-3eee-4595-a063-ef970d192483)



Q.2.4.1

Director (bareos-dir) : Gère la configuration, la planification et les métadonnées.
Storage Daemon (bareos-sd) : Gère les périphériques de stockage et stocke les données de sauvegarde.
File Daemon (bareos-fd) : Installe sur les machines clientes pour envoyer les données à sauvegarder au storage daemon.

Q.2.5.1

Blocage des éléments entrant sur hook input
L'échange de paquet est autorisé dans les deux sens une fois authentifié 
Bloque l'échange de paquet si la connexion n'est pas valide 
La communication avec la loopback est accepté
La communication avec le port 22 est accepté 
Le protocole ICMP est accepté 
Le protocole ICMP est accepté en IPV6



![2024-06-21 12_57_20-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/bd65582a-df27-4280-a145-26dc1c189b1c)


Q.2.5.2

Le protocole ICMP, le port 22 est celle que la machine à établie dont l'état de connexion est valide.

Q.2.5.3

Celle qui ne font pas partie d'une connexion connue établie par la machine ( état invalide )

Q.2.5.4

On ajoute les trois ports 9101,9012 et 9103 dans le fichier mais je ne trouve pas la bonne commande

![2024-06-21 13_17_09-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/c38f3fb7-56ce-4889-b9da-7a0a4e9fe83f)


Q.2.6.1


![2024-06-21 13_18_04-Checkpoint3-SRVLX01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/e3d435d5-3063-42ea-9215-14a35fe103fe)
