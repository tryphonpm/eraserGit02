<p><a target="_blank" href="https://app.eraser.io/workspace/xS2Yq5uBG4M0IqsndikC" id="edit-in-eraser-github-link"><img alt="Edit in Eraser" src="https://firebasestorage.googleapis.com/v0/b/second-petal-295822.appspot.com/o/images%2Fgithub%2FOpen%20in%20Eraser.svg?alt=media&amp;token=968381c8-a7e7-472a-8ed6-4a6626da5501"></a></p>

## script : LDAP_QUERY
'EMPLOYEE_ID_ARRAY'

```
Definir ( [
EmployeeID_array = MBS( "JSON.CreateArrayRef" )
; jsonRef= MBS( "JSON.CreateObjectRef" )
; r = MBS("JSON.AddStringToObject"; jsonRef; "SERVEUR"; "non")
; r = MBS("JSON.AddStringToObject"; jsonRef; "ACTION"; "PULL_MANY")
; r = MBS("JSON.AddStringToObject"; jsonRef; "MODELE"; "LDAP_PROD")
; r = MBS("JSON.AddStringToObject"; jsonRef; "LOG"; "LDAP::_notes_comparatif")
; r = MBS("JSON.AddStringToObject"; jsonRef; "RECORDS"; "MANY")
];MBS( "JSON.Format"; jsonRef) )
```
## script : LDAP_PULL_MANY
### pré-requis
- champs à actualiser : $attributes
### boucle sur 'EMPLOYEE_ID_ARRAY'
1. vérification de la présence/accessibilité du compte LDAP
2. recherche et suppression de la fiche GDI::LDAP
3. nouvelle fiche GDI::LDAP
4.  boucle sur les 'attributes' -> 'LDAP.SearchResult'
5. traitements spécifiques :
    1. ObjectGUID
    2. ThumbnailPhoto -> script : 'récupérer_photo'
6. logs > `LDAP::_notes_comparatif` 




<!--- Eraser file: https://app.eraser.io/workspace/xS2Yq5uBG4M0IqsndikC --->