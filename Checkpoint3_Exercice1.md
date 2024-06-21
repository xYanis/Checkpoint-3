Q.1.1.1

On va faire un clique droit sur Kelly Rhameur, sélectionner ``copy` et remplir comme ci dessous et Lionel aura les mêmes attributs que Kelly

![2024-06-21 09_27_04-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/15a7ba40-e92f-49f1-b08a-5835ae43a2bf)


![2024-06-21 09_27_38-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/d6c3d95d-85fc-476b-a73e-270dafc1fadb)

Q.1.1.2

On va crée un nouvelle OU dans LABUSERS et faire glisser Kelly Rhameur dedans

![2024-06-21 09_29_35-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/7b32a495-c52c-4ee0-99d9-6b5919987c4f)


Q.1.1.3

On va faire un clique droit sur Kelly et aller dans l'onglet move et retirer Kelly de son ancien groupe ( j'en ai crée un nouveau pour mettre Kelly dedans, j'étais pas sur )

![2024-06-21 09_32_47-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/61e3b5e5-78b0-42ba-866c-2a1c059b6e53)


Q.1.1.4

On vas créer un dossier ARCHIVE pour mettre le dossier de Kelly à l'intérieur et créer un dossier pour Lionel avec les paramètres ci dessous

![2024-06-21 09_51_40-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/5a1f6fc6-2d8a-45c3-b56d-ae020cc2d6cc)

![2024-06-21 09_53_26-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/b954f680-f598-4de8-9125-5b79f840dab1)

![2024-06-21 09_55_48-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/d63f6dc4-275b-4c6f-bfe4-8265fb17d90b)

Q.1.2.1

Pour crée une plage horaires pour Gabriel
Clique droit / Properties / Account / Logon Hours



![2024-06-21 10_00_50-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/28bbf438-6de6-442e-8ef6-c9463bf516ac)



Q.1.2.2

Clique droit / Properties / Account / Log on to et on indique le CLIENT1


![2024-06-21 10_03_54-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/80ea8fcc-72fc-4093-953c-fe83a8dfb8b8)


Q.1.2.3

Nous allons crée une GPO pour créer un GPO pour avoir un minimum de 10 caractères pour les mots de passe utilisateurs

![2024-06-21 10_07_45-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/375a268c-baab-4cc6-bdb9-e7aa17d4ce2c)


![2024-06-21 10_09_00-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/3ae76da0-7cb2-4324-8caa-e48b20cf0304)





Q.1.3.1

Nous allons partager dans un premier temps, les disques `DossiersIndividuels` et `DossiersCommuns` pour ensuite récupérer le chemin ( Pour F : \\Srvwin01\f et pour E : \\Srvwin01\e )
et l'implémenter pour le mappage des GPO

![2024-06-21 10_22_34-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/ed394900-ed17-4348-9690-ee8ebacc3f77)


![2024-06-21 10_28_28-Checkpoint3-SRVWIN01  En fonction  - Oracle VM VirtualBox](https://github.com/xYanis/Checkpoint-3/assets/161461625/03eda469-abeb-41ce-8b42-510bc8d5342d)


