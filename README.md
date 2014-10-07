IMPORT_COVADIS_2.0
==================

Imtégration des Documents d'urbanisme 2.0 dans une Géobase

2.0.2	MAJ 900_MODULE_COVADIS_01A06v2.0.2.mb
	- ajout de l'intégration de N_SECTEUR_CC_XXCCC et N_SECTEUR_CC_038
	- ajout du module d'intégration N_INFO_SURF_xxccc et N_INFO_SURF_038
	MAJ 900_MODULE_COVADIS_07A012v2.0.2.mb
	- ajout du module d'intégration N_INFO_LIN_xxccc et N_INFO_PCT_038
	- ajout du module d'intégration N_INFO_PCT_xxccc et N_INFO_PCT_038
	- maj modules d'import des habillages car procedure CC = procedure POS/PLU

en cours d'intégration

2.0.1	MAJ 900_MODULE_COVADIS_01A06v2.0.1.mb
	MAJ 900_MODULE_COVADIS_07A12vv2.0.1.mb
	- ajout de la MAJ du champs [URLFIC] pour mettre le lien vers FTP_Carto

2.0	CREATION 00_IMPORT_COVADIS_38XXX_v2.0.mb
	- pour intégrer les documents aux formats COVADIS 2.0
	CREATION 900_MODULE_COVADIS_01A06v2.0.mb
	CREATION 900_MODULE_COVADIS_07A12vv2.0.mb

1.9.6 	MAJ 901_MODULE_01a06v1.9.5.mb
	-remplacement des COL1, COL2, etc. par vrais noms des champs dans la procédure Insert Into
	MAJ 902_MODULE_07a12v1.9.5.mb
	-remplacement des COL1, COL2, etc. par vrais noms des champs dans la procédure Insert Into

1.9.5	MAJ MAJ 00_IMPORT_EUROPRIM_38xxx_v1.9.5.mb
	- Ajout du répertoire COVADIS 2.0
	- Ajout de la procédure pour créer tous les répertoires de la COVADIS
	MAJ 901_MODULE_01a06v1.9.5.mb
	- sauvegarde dans les nouveaux répertoires COVADIS
	- passage de 38"+Right$(INSEECOMMUNE,3) à INSEECOMMUNE
	- passage des Alter des 6 modules à la V2.0 sauf module 2-CC
	- suppression du compactage des couches départementales
	MAJ 902_MODULE_07a12v1.9.5.mb
	- passage de 38"+Right$(INSEECOMMUNE,3) à INSEECOMMUNE
	- suppression du compactage des couches départementales
	- passage des Alter des modules INFO_LIN et HABILLAGE_TXT à la V2.0
	MAJ 01_POSPLU_SUPPRESSION_V1.9.5.mb
	- remplacement de ID_DOC_URBA par IDURBA
	MAJ 911_POSPLU_SUPP_TOUT_V1.9.5.mb
	- remplacement de ID_DOC_URBA par IDURBA
	- passage de 38"+Right$(INSEECOMMUNE,3) à INSEECOMMUNE sauf module 2-CC
	MAJ 912_POSPLU_SUPP_UNEAUNE_V1.9.5.mb
	- remplacement de ID_DOC_URBA par IDURBA
	- passage de 38"+Right$(INSEECOMMUNE,3) à INSEECOMMUNE sauf module 2-CC
attention : module supression à tester

1.9.2	MAJ 901_MODULE_01a06v1.9.6.mb
	MAJ 902_MODULE_07a12v1.9.6.mb
	- ajout de la MAJ du champs [URLFIC] pour mettre le lien vers FTP_Carto
à vérifier

1.9.1	MAJ 992_MODULE_07a12v1.9.mb
	- [NATTRAC] char(254) non conforme à la COVADIS pour les Tables :
		= HABILLAGE_SURF
		= HABILLAGE_LIN
		= HABILLAGE_TXT
	- [TXT] char(254) non conforme à la COVADIS pour les Tables :
		= HABILLAGE_TXT
		

1.9	MAJ 991_MODULE_01a06v1.9.mb
	- correction de la procédure 2CC pour les cartes communales
	- ajout de la procédure 6CC pour intégrer les éléments paysagers surfaciques dans l'information surfacique
	- ajout de la procédure 6CCbis & 6CCter pour intégrer la préhemption surfacique dans l'information surfacique
	- ajout de la procédure 6CCquater & 6CCquint pour intégrer l'information surfacique de la commune dans la table départementale
	MAJ 992_MODULE_07a12v1.9.mb
	- ajout des procédures 7CC & 7CCBIS pour intégrer l'information linéaire des cartes communales
	- ajout des procédures 8CC & 8CCBIS pour intégrer l'information ponctuelle des cartes communales
	MAJ 911_POSPLU_SUPP_TOUT_V1.9.mb
	- ajout de la procédure 2CC pour supprimer les données de ZONAGE_CC

1.8.1	MAJ 00_IMPORT_EUROPRIM_38xxx_v1.8.1.mb
	ajour de la procédure 99-Conversion org2ogr des fichiers communaux

1.8	MAJ 00_IMPORT_EUROPRIM_38xxx_v1.8.mb et 991_MODULE_01a06v1.8.mb et 992_MODULE_07a12v1.8.mb
	Pas d'import dans les couches départementales si document non opposable 

1.7.1	MAJ 01_POSPLU_SUPPRESSION_V1.7.1.mb :
	Eclatement en deux sous-procédures :
		- 011_POSPLU_SUPP_TOUT_V1.7.1.mb :
*			Plus de vérification de la présence de la commune dans la couche N_DOCUMENT_URBA
		- 012_POSPLU_SUPP_UNEAUNE_V1.7.1.mb :
*			permet d'enlever les éléments de toutes les couche même si N_DOCUMENT_URBA est vide
*			option : supprimer les couches une par une
*	comparaison entre le nombre d'objets dans BDD_RECAP_GEOBASE_POS_PLU.TAB et ce qui est réellement supprimé	


1.7	MAJ 00_IMPORT_EUROPRIM_38xxx_v1.7.mb et 991_MODULE_01a06v1.7.mb et 992_MODULE_07a12v1.7.mb :
* 		ajout des résultats d'insersion dans une nouvelle base de données
			BDD_RECAP_GEOBASE_POS_PLU.TAB
	MAJ 01_POSPLU_SUPPRESSION_V1.7 : 
* 		ajout des résultats de suppression dans une nouvelle base de données
			BDD_RECAP_GEOBASE_POS_PLU.TAB
    				TYPE Char (20) Index 1 ;
   				DATE Date ;
   				TYPEDOC Char (3) Index 2 ;
   				INSEE Char (5) Index 3 ;
   				ID_DOC_URBA Char (20) Index 4 ;
   				TABLE Char (50) ;
   				DEPARTEMENTALE Logical Index 5 ;
   				NBRE_LIGNES Integer ;
   				GB_IDUSER Char (16) ;
	MAJ 991_MODULE_01a06v1.7.mb :
* 		ajout du module 2CC pour intégration de la couche N_SECTEUR_CC_038
* 		Couche N_DOCUMENT_URBA_COM_38 la valeur DATE_COG est mise à jour au 1er janvier de l'année d'importation


1.6.2	MAJ Module 991 & MAJ Module 992 :
* 	Remplacement du répertoire SHP_DDT par le répertoire SHP_CG pour les tables ESRI
*	Procédure DOUZE : remise en place du choix avec ou sans extension _CORRIGE : si "_CORRIGE" ouvre le TAB,
	si "" importe le MIF/MID et ensuite ouvre le TAB

1.6.1	MAJ Module 992_MODULE_07a12v1.6.mb :
*	Procédure Un : Correction Bug : non inserstion de la Valeur "INSEECOMMUNE" dans le champs [ID_MAP]
*	Procédure DEUX : Correction Bug : N_ZONE_URBA_ddd avec [LIBELLE] à Char(254) au lieu de Char(10)
*	Procédure Douze : import du 38XXX_HABILLAGE_TXT MIF/MID présent sous MIF_MID au lieu du TAB


1.6	MAJ :
	Module 00_IMPORT_EUROPRIM_38XXXv1.6.mb permet de configurer les variables pour une commune donnée
	Module 991_MODULE_01a06v1.6.mb pour les modules 1 à 6 
	Module 992_MODULE_07a12v1.6.mb pour les modules 7 à 12 

1.5 :	ajout :
*	POS/PLU_SUPPRESSION_V1 : permet de supprimer les entrées départementales et les couches communes pour une commune donnée
*	Ajout des modules de saisie des valeurs
*	la valeur INSEECOMMUNE passe à 5 caratères au lieu de 3 et dans les formules INSEECOMMUNE devient Right$(INSEECOMMUNE,3)
*	tout se fait en Lambert93 BORNE France


Correction de Bugs :
*	Commande Pack table N_PRESCRIPTION_PCT_038 Graphic Data mis de la même façon partout
*	Module 5bis : DATAPPRO et DATVALID non présents dans la table N_PRESCRIPTION_PCT_03 alors qu'ils étaient présents dans N_PRESCRIPTION_PCTXXX_03
	il manquait ajout de COL7 et COL8 dans la commande Insert Into N_PRESCRIPTION_PCT_038
*	Variable REPTEMP était à "D:\_TEMP" au lieu de "D\_TEMP\"


1.4.1 : ajout :
*	N_PRESCRIPTION_SURFXXX_038.TAB
  	Update "N_PRESCRIPTION_SURF"+INSEECOMMUNE+"_038" Set NOMFIC = "38"+INSEECOMMUNE+"_reglement_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"
  	Print "Mise à jour du champs [NOMFIC] avec la valeur : 38"+INSEECOMMUNE+"_reglement_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"
*	N_PRESCRIPTION_LINXXX_038.TAB
	Update "N_PRESCRIPTION_LIN"+INSEECOMMUNE+"_038" Set NOMFIC = "38"+INSEECOMMUNE+"_reglement_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"
	Print "Mise à jour du champs [NOMFIC] avec la valeur : 38"+INSEECOMMUNE+"_reglement_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"
*	N_PRESCRIPTION_PCTXXX_038.TAB
	Update "N_PRESCRIPTION_PCT"+INSEECOMMUNE+"_038" Set NOMFIC = "38"+INSEECOMMUNE+"_reglement_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"
	Print "Mise à jour du champs [NOMFIC] avec la valeur : 38"+INSEECOMMUNE+"_reglement_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"
*	N_INFO_SURFXXX_038.TAB
	Update "N_INFO_SURF"+INSEECOMMUNE+"_038" Set NOMFIC = "38"+INSEECOMMUNE+"_docgraphiques_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"
	Print "Mise à jour du champs [NOMFIC] avec la valeur : 38"+INSEECOMMUNE+"_docgraphiques_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"

1.4 : modifications pour correspondre au standard 1.1 de la COVADIS
- supression de la variable [NOMREGL] as String pour la rempacler par une valeur calculée : "38"+INSEECOMMUNE+"_reglement_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"
- supression de la variable [NOMPLANS] as String pour la rempacler par une valeur calculée : "38"+INSEECOMMUNE+"_docgraphiques_"+ANNEEAPPRO+MOISAPPRO+JOURAPPRO+".pdf"

bug : pose problèmes pour le nom du fichier PDF de référence pour :
Informations surfaciques, Prescriptions Linéaires, ponctuelles et surfaciques
