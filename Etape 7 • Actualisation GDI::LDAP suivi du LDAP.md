<p><a target="_blank" href="https://app.eraser.io/workspace/4Rm0hUHxAbJmwYO1WQmb" id="edit-in-eraser-github-link"><img alt="Edit in Eraser" src="https://firebasestorage.googleapis.com/v0/b/second-petal-295822.appspot.com/o/images%2Fgithub%2FOpen%20in%20Eraser.svg?alt=media&amp;token=968381c8-a7e7-472a-8ed6-4a6626da5501"></a></p>

# Description
- Synchronisation GDI::SALARIE <> GDI::LDAP
- Actualisation GDI::LDAP => LDAP
# Mongo
Table GDI/ldap

```
{
  "_id": {
    "$oid": "66ecfdf1d705c48e660908b3"
  },
  "UPDATED": {
    "6": {
      "ldap::mail": "Kevin.BELKACEM@alfa3a.org",
      "LDAP_mail": "",
      "ope": "<<"
    },
    "20": {
      "ldap::Title": "Animateur Forfaitaire",
      "PAIE_Titre": "Animateur Bafa",
      "ope": ">>"
    },
    "23": {
      "ldap::extensionAttribute1": "08/01/2024",
      "PAIE_DateDebutContrat": "02/09/2024",
      "ope": ">>"
    },
    "27": {
      "ldap::MemberOf": "CN=App_Lucca_Cleemy,OU=Applications,OU=Groupes,OU=ALFA3A,DC=alatfa,DC=fr\rCN=App_GLPI_Utilisateurs,OU=Applications,OU=Groupes,OU=ALFA3A,DC=alatfa,DC=fr\rCN=App_EXTRANET_Utilisateurs,OU=Sites_ALFA3A,OU=Applications,OU=Groupes,OU=ALFA3A,DC=alatfa,DC=fr\rCN=App_Office_365_A1,OU=Applications,OU=Groupes,OU=ALFA3A,DC=alatfa,DC=fr\rCN=Gr_Utilisateurs_Alfa3a,OU=Fichiers,OU=Groupes,OU=ALFA3A,DC=alatfa,DC=fr",
      "LDAP_memberOf": "",
      "ope": "<<"
    },
    "28": {
      "ldap::DisplayName": "Kevin BELKACEM",
      "LDAP_displayName": "",
      "ope": "<<"
    },
    "29": {
      "ldap::SamAccountName": "Kevin.BELKACEM",
      "LDAP_sAMAccountName": "",
      "ope": "<<"
    },
    "30": {
      "ldap::UserPrincipalName": "Kevin.BELKACEM@alfa3a.org",
      "LDAP_UserPrincipalName": "",
      "ope": "<<"
    },
    "32": {
      "ldap::accountExpires": "133961400000000000",
      "LDAP_accountExpires": "133960536000000000",
      "ope": "<<"
    }
  },
  "MATRICULE": "139",
  "NOM_USAGE": "BELKACEM",
  "NOM_NAISSANCE": "BELKACEM",
  "PRENOM": "Kevin",
  "LOG_DATE": "20/09/2024",
  "LOG_HEURE": "05:17:59",
  "SAMACCOUNTNAME": "Kevin.BELKACEM"
}
```
# Remarques
## Nom naissance, nom usage, prénom, sama
> actualisation sous conditions > == A REVOIR ==

> selon les contraintes samaccountname, email, authentificatiion...

## Date de fin de contrat
> accountExpiresDate : ne peut être éditée car calculée par le LDAP en fonction du champs codé : accountExpires
Au niveau GDI : codage de la DFC > accountExpires => LDAP

## MemberOf
> champs LDAP non-éditable directement > possible de passer par les GROUPES (déjà testé, mais pas mis en place)

> Calcul d'une liste 'MemberOf' standard, déclinable selon les profils => Charlotte





<!--- Eraser file: https://app.eraser.io/workspace/4Rm0hUHxAbJmwYO1WQmb --->