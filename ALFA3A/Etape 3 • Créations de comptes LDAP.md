<p><a target="_blank" href="https://app.eraser.io/workspace/jb8gm8OxOQw5m1dcsBFw" id="edit-in-eraser-github-link"><img alt="Edit in Eraser" src="https://firebasestorage.googleapis.com/v0/b/second-petal-295822.appspot.com/o/images%2Fgithub%2FOpen%20in%20Eraser.svg?alt=media&amp;token=968381c8-a7e7-472a-8ed6-4a6626da5501"></a></p>

# MONGO
table GDI/creations

```
{
  "_id": {
    "$oid": "66eb94e1d705c48e6608fa3d"
  },
  "PRESENCE": "absent_salarie",
  "LOG_DATE": "19/09/2024",
  "LOG_HEURE": "05:02:39",
  "DATE_CREATION": "19/09/2024",
  "MODE": "1",
  "MATRICULE": "7266",
  "NOM_USAGE": "BELLOTTO",
  "NOM_NAISSANCE": "BELLOTTO",
  "PRENOM": "Enzo",
  "MANAGER": "jassans.cs.direction",
  "MANAGER_MATRICULE": "206",
  "SAMACCOUNTNAME": "enzo.bellotto",
  "NATURE_CONTRAT": "CDD",
  "DATE_FIN_CONTRAT": "05/08/2026",
  "DATE_SOR_GROUP": "05/08/2026",
  "BOITE_MAIL": "4GO",
  "DUREE_CONTRAT": "685",
  "PRESENCE_SALARIE": "oui",
  "PRESENCE_LDAP": "oui",
  "OK_creationLDAP": "oui",
  "TAG_RETURN_PS": "NEW_USER_OK",
  "MDP_PROVISOIRE": "A3rOBMeFSH",
  "CTRL_1": "OK",
  "CTRL_2": "OK",
  "CTRL_3": "OK",
  "CTRL_4": "OK"
}
```
## Analyse (ex. 20/09/2024)
### retour TAG script PS
```
# EMPLOYEEID_IN_USE :
784 ana-filipa.carvalho
1677 olivier.cassange
2431 seda-nur.kacir
762 shaimaa.abdelrahman
1188 stephanie.crokaert

# USER_ALREADY_ACTIVE :
7248 olivier.demond
1337 thibaut.fonton

# UPDATE_USER_DATE_OK :
7270 julie.duburcq

# OLD_USER_OK :
896 berenice.clemens
775 mohamed.naceur

# NEW_USER_OK :
```
Les retours `EMPLOYEEID_IN_USE` `USER_ALREADY_ACTIVE`  :

> comptes désactivés > aucune ré-activation automatique

Les retours `UPDATE_USER_DATE_OK` et `OLD_USER_OK` et `NEW_USER_OK`  :

> comptes OK



```
# ERREUR :
7303 axel.dreux
5009 gilly.groccia
```
Le marquage `ERREUR` : 

> le script ne renvoie rien,** aucun tag** ou message d'erreur >
mais **les comptes sont toujours créés **sur le LDAP.
Par contre, la routine est interrompue.
Le traitement et l'actualisation de tous les champs sont bloqués .

#### Anomalies récurrentes :
- sAMAccountName du manager qui n'est pas 'nominatif' 
---

### Les comptes nouveaux, créés dans GDI::SALARIE mais filtrés en amont du script PS
```
# Ces contrats sont d'une durée de moins de moins de 31 jours :
6787 mj.tshisuaka
7234 amar.boufendi
4486 audrey.clery
...

#  Contrats de stage :
7072 abdelkader.bensebiat
1388 celia.parras
5131 jason.frey
```
Les deux filtres en place :

- durée de contrat par rapport à la date courante < 31 jours
- nature du contrat : stage
---

# Anomalies courantes
### champs non-renseignés (scripts associés)
- sAMAccountName > formatage_noms_prenoms_SALARIE
- accountExpires > actualisation_contrats
- Manager DN > formatage_Manager_DN
- Description
- (DN_LIEN : normalement obsolète > LDAP_DistinguishName récupéré du LDAP)
- **... à voir : champs liés au SITE** 
> Les scripts sont communs à la routine quotidienne (étape 3) et au script (toujours en cours de dev) 'corrections_anomalies'

### Anomalies apparues dans la table importée NOVRH 
- date de fin de contrat pour des contrats de type CDD
- champs Manager (matricule)
- CODANA
- doublons
## Documentation
![Figure 1](/.eraser/jb8gm8OxOQw5m1dcsBFw___f4QvwUwjoWgyG5YzFw7uRY0I6SG3___---figure---eLsdoJq2LkLprVOY09Um8---figure---FfC_41ZUiItEGHiTtb25VA.png "Figure 1")





<!--- Eraser file: https://app.eraser.io/workspace/jb8gm8OxOQw5m1dcsBFw --->