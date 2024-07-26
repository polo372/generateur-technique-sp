<script lang="ts">
  const techniques = [
    { name: "Utilisation du halligan-tool", 
      url:"https://extranet.sdis37.fr/jcms/jcms/1401_DBFileDocument/fit-055-inc-outil-de-forcement-halligan-tool?details=true",
    documents: [
        { name: "Halligan Tool", url: "Halligan Tool.pdf" }
      ]
     },
  { name: "Mise en place d'un groupe électrogène", iframe: "https://www.youtube.com/embed/aydVCwnWJII?si=GvSX5WT_lSbVdUKH" },
  { name: "Aspiration du bache à incendie", iframe: "https://www.youtube.com/embed/WI0d4eRLuxM?si=SdvN1LFSw5SDQSKq" },
  { name: "ETB1-Ldt", pdf: "ETB1-Ldt.pdf" },
  { name: "ETB2-Prise d'eau", pdf: "ETB2-Prise d'eau.pdf" },
  { name: "ETB3-Lance", pdf: "ETB3-Lance.pdf" },
  { name: "ETB4-Alimentation", pdf: "ETB4-Alimentation.pdf" },
  { name: "ETB5-Etablissement particuliers", pdf: "ETB5-Etablissement particuliers.pdf" },
  { name: "ETB6-Prolongement/remplacement", pdf: "ETB6-Prolongement/remplacement.pdf" },
  { name: "TDE1-Refroidissement des fumées", pdf: "TDE1-Refroidissement des fumées.pdf" },
  { name: "TDE2-Extinction directe", pdf: "TDE2-Extinction directe.pdf" },
  { name: "TDE3-Extinction indirecte", pdf: "TDE3-Extinction indirecte.pdf" },
  { name: "TDE4-Extinction combinée/massive", pdf: "TDE4-Extinction combinée/massive.pdf" },
  { name: "TDE5-Situation pre-backdraft", pdf: "TDE5-Situation pre-backdraft.pdf" },
  { name: "TDE6-Repli sous protection hydraulique", pdf: "TDE6-Repli sous protection hydraulique.pdf" },
  { name: "TDE7-Feu soumis aux effets du vent et effet chalumeau", pdf: "TDE7-Feu soumis aux effets du vent et effet chalumeau.pdf" },
  { name: "TDE8-Attaque d'atténuation", pdf: "TDE8-Attaque d'atténuation.pdf" },
  { name: "Contrôle croisé", pdf: "Contrôle croisé.pdf" },
  { name: "Engagement a vue", pdf: "Engagement a vue.pdf" },
  { name: "Engagement au moyen d'une ligne de vie", pdf: "Engagement au moyen d'une ligne de vie.pdf" },
  { name: "Engagement sur ligne de vie méthode latérale", pdf: "Engagement sur ligne de vie méthode latérale.pdf" },
  { name: "Engagement sur ligne de vie méthode circulaire", pdf: "Engagement sur ligne de vie méthode circulaire.pdf" },
  { name: "Méthode AIDES", pdf: "Méthode AIDES.pdf" },
  { name: "Deplacement-progression sous ARI", pdf: "Deplacement-progression sous ARI.pdf" },
  { name: "Règle de marquage", pdf: "Règle de marquage.pdf" },
  { name: "Utilisation échelle à coulisse en mode secours", pdf: "Utilisation échelle à coulisse en mode secours.pdf" },
  { name: "Attendre les secours, binome en difficulté", pdf: "Attendre les secours.pdf" },
  { name: "Passage dans des fils ou des câbles", pdf: "Passage dans des fils ou des câbles.pdf" },
  { name: "Franchissement passage étroit", pdf: "Franchissement passage étroit.pdf" },
  { name: "Retrait de l'ARI-Autosauvetage", pdf: "Retrait de l'ARI-Autosauvetage.pdf" },
  { name: "Technique de respiration (gestion air)", pdf: "Technique de respiration (gestion air).pdf" },
  { name: "Gérer une fuite", pdf: "Gérer une fuite.pdf" },
  { name: "Bail-out", pdf: "Bail-out.pdf" },
  { name: "Evacuation au moyen d'un tuyau", pdf: "Evacuation au moyen d'un tuyau.pdf" },
  { name: "Evaluation et stabilisation d'un équipier en difficulté", pdf: "Evaluation et stabilisation d'un équipier en difficulté.pdf" },
  { name: "Traction au sol d'un SP sans matériel", pdf: "Traction au sol d'un SP sans matériel.pdf" },
  { name: "Traction au sol avec matériel", pdf: "Traction au sol avec matériel.pdf" },
  { name: "Sauvetage par un binome", pdf: "Sauvetage par un binome.pdf" },
  { name: "Evacuation par l'escalier", pdf: "Evacuation par l'escalier.pdf" },
  { name: "Le Denver-drill", pdf: "Le Denver-drill.pdf" },
  { name: "Technique d'évacuation de SP sur echelle à coulisse", pdf: "Technique d'évacuation de SP sur echelle à coulisse.pdf" },
  { name: "Remontée d'un équipier avec sa lance", pdf: "Remontée d'un équipier avec sa lance.pdf" },
  { name: "Le Nance-drill", pdf: "Le Nance-drill.pdf" },
  { name: "Utilisation de l'échelle à crochet", pdf: "Utilisation de l'échelle à crochet.pdf" },
  { name: "Cas particulier de l'utilisation de l'échelle à crochet", pdf: "Cas particulier de l'utilisation de l'échelle à crochet.pdf" },
  { name: "Utilisation échelle à coulisse-sauvetage d'un victime valide", pdf: "Utilisation échelle à coulisse-sauvetage d'un victime valide.pdf" },
  { name: "Utilisation échelle à coulisse-sauvetage d'un victime invalide", pdf: "Utilisation échelle à coulisse-sauvetage d'un victime invalide.pdf" },
  { name: "Utilisation échelle à coulisse en excavation", pdf: "Utilisation échelle à coulisse en excavation.pdf" },
  { name: "Accès à une personne visible en hauteur", pdf: "Accès à une personne visible en hauteur.pdf" },
  { name: "Utilisation particulière de l'échelle à coulisse", pdf: "Utilisation particulière de l'échelle à coulisse.pdf" },
  { name: "Dégagement d'urgence sans matériel", pdf: "Dégagement d'urgence sans matériel.pdf" },
  { name: "Dégagement d'urgence avec matériel", pdf: "Dégagement d'urgence avec matériel.pdf" },
  { name: "LSPCC-Sauvetage au moyen du harnais", pdf: "LSPCC-Sauvetage au moyen du harnais.pdf" },
  { name: "LSPCC-Sauvetage par l'extérieur", pdf: "LSPCC-Sauvetage par l'extérieur.pdf" },
  { name: "LSPCC-Excavation", pdf: "LSPCC-Excavation.pdf" },
  { name: "LSPCC-Reconnaissance d'appartement", pdf: "LSPCC-Reconnaissance d'appartement.pdf" },
  { name: "Décontamination aux fumées d'incendie", pdf: "Décontamination aux fumées d'incendie.pdf" },
  { name: "Retournement en urgence d’une victime à 2", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444223/retournement-en-urgence-d-une-victime-a-1?details=true" },
  { name: "Retournement en urgence d’une victime à 1", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444445/retournement-en-urgence-d-une-victime-a-1?details=true" },
  { name: "Evaluer la respiration", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444395/evaluer-la-respiration?details=true" },
  { name: "Evaluer la circulation", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444393/evaluer-la-circulation?details=true" },
  { name: "Mesurer la glycémie capillaire", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444419/mesurer-la-glycemie-capillaire?details=true" },
  { name: "Mesurer la pression artérielle (auto-tensiomètre)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444420/mesurer-la-pression-arterielle-auto-tensiometre?details=true" },
  { name: "Mesure de la saturation en oxygène", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444418/mesure-de-la-saturation-en-oxygene?details=true" },
  { name: "Mesurer la température de la victime", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444421/mesurer-la-temperature-de-la-victime?details=true" },
  { name: "Evaluer la fonction neurologique", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444394/evaluer-la-fonction-neurologique?details=true" },
  { name: "Recherche de lésions", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444222/recherche-de-lesions?details=true" },
  { name: "Équipement de protection risques infectieux", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444390/equipement-de-protection-risques-infectieux?details=true" },
  { name: "Friction des mains", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444405/friction-des-mains?details=true" },
  { name: "Lavage des mains", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444410/lavage-des-mains?details=true" },
  { name: "Mise en place de gants stériles", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444423/mise-en-place-de-gants-steriles?details=true" },
  { name: "Nettoyage et désinfection d’un véhicule ou d’un local", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444424/nettoyage-et-desinfection-d-un-vehicule-ou-d-un-local?details=true" },
  { name: "Nettoyage et désinfection du matériel", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444425/nettoyage-et-desinfection-du-materiel?details=true"},
  { name: "Retrait des gants à usage unique", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444448/retrait-des-gants-a-usage-unique?details=true" },
  { name: "Lavage occulaire", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444411/lavage-occulaire?details=true" },
  { name: "Aspiration de mucosités", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444370/aspiration-de-mucosites?details=true" },
  { name: "Compression manuelle", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444375/compression-manuelle?details=true" },
  { name: "Compressions thoraciques (adultes)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444376/compressions-thoraciques?details=true" },
  { name: "Compressions thoraciques (enfant)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444376/compressions-thoraciques?details=true" },
  { name: "Compressions thoraciques (nourrisson, nouveau-né)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444376/compressions-thoraciques?details=true" },
  { name: "Claques dans le dos (adulte et enfant)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444374/claques-dans-le-dos?details=true" },
  { name: "Claques dans le dos (nourrisson)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444374/claques-dans-le-dos?details=true" },
  { name: "Désostruction par compressions abdominales (adulte et enfant)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444386/desostruction-par-compressions-abdominale?details=true" },
  { name: "Désostruction par compressions thoraciques (femme enceinte et obèse)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444387/desostruction-par-compressions?details=true" },
  { name: "Désostruction par compressions thoraciques (nourrisson)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444387/desostruction-par-compressions?details=true" },
  { name: "Pose d’un garrot", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444433/pose-d-un-garrot?details=true" },
  { name: "LVA victime assise", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444412/lva-victime-assise?details=true" },
  { name: "LVA victime non traumatisée", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444413/lva-victime-non-traumatisee?details=true" },
  { name: "LVA victime traumatisée", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444414/lva-victime-traumatisee?details=true" },
  { name: "Mise en place d’une canule oropharyngée", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444422/mise-en-place-d-une-canule-oropharyngee?details=true" },
  { name: "Pose d’un pansement compressif (israélien)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444435/pose-d-un-pansement-compressif-israelien?details=true", iframe: "https://www.youtube.com/embed/7G0jN--29bI?si=omYHBr3C3bKfA5pP" },
  { name: "Utilisation du DAE", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444454/utilisation-du-dae?details=true" },
  { name: "Ventilation artificielle orale (adulte, enfant)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444456/ventilation-artificielle-orale?details=true" },
  { name: "Ventilation artificielle orale (nourrisson, nouveau-né)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444456/ventilation-artificielle-orale?details=true" },
  { name: "Ventilation artificielle avec insufflateur (1 secouriste)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444455/ventilation-artificielle-avec-insufflateur?details=true" },
  { name: "Ventilation artificielle avec insufflateur (2 secouristes)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444455/ventilation-artificielle-avec-insufflateur?details=true" },
  { name: "PLS à 1 secouriste", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444426/pls-a-1-secouriste?details=true" },
  { name: "PLS à 2 secouristes", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444428/pls-a-2-secouristes?details=true" },
  { name: "Inhalation d’oxygène (masque haute concentration)", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444458/administration-d-oxygene-par-inhalation?details=true" },
  { name: "Utilisation d’une bouteille d’oxygène", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444453/utilisation-d-une-bouteille-d-oxygene?details=true" },
  { name: "Réchauffement d'une victime", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444441/rechauffement-d-une-victime?details=true" },
  { name: "Les différentes positions d'attente", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444436/position-d-attente?details=true" },
  { name: "Aide à la prise de médicaments", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444461/aide-a-la-prise-de-medicaments?details=true" },
  { name: "Manoeuvres physiques", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444417/manoeuvres-physiques?details=true" },
  { name: "Soin au cordon", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444452/soin-au-cordon?details=true" },
  { name: "Réaliser un pansement non-occlusif", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444439/realiser-un-pansement-non-occlusif?details=true" },
  { name: "Contention pelvienne", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444377/contention-pelvienne?details=true" },
  { name: "Immobilisation d’un membre avec une attelle à dépression", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444431/pose-d-attelle-a-depression?details=true" },
  { name: "Immobilisation de l'épaule avec une attelle à dépression", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444431/pose-d-attelle-a-depression?details=true" },
  { name: "Écharpe simple", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444388/echarpe?details=true" },
  { name: "Contre-écharpe", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444388/echarpe?details=true" },
  { name: "Écharpe oblique", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444388/echarpe?details=true" },
  { name: "Immobilisation victime plat dos sur plan dur", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444408/immobilisation-sur-plan-dur?details=true" },
  { name: "Immobilisation victime allongée sur le ventre sur plan dur", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444408/immobilisation-sur-plan-dur?details=true" },
  { name: "Immobilisation victime debout sur plan dur", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444408/immobilisation-sur-plan-dur?details=true" },
  { name: "Immobilisation au moyen du MID", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444406/immobilisation-au-moyen-du-mid?details=true" },
  { name: "Maintien de la tête à 2 mains victime debout ou assise", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444415/maintien-de-la-tete?details=true" },
  { name: "Maintien de la tête à 2 mains victime plat dos", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444415/maintien-de-la-tete?details=true" },
  { name: "Pose d’une attelle cervico-thoracique", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444434/pose-d-une-attelle-cervico-thoracique?details=true" },
  { name: "Pose d’un collier cervical", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444432/pose-d-un-collier-cervical?details=true" },
  { name: "Réalignement de membre", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444438/realignement-de-membre?details=true" },
  { name: "Retrait d’un casque de protection en secouriste isolé", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444447/retrait-d-un-casque?details=true" },
  { name: "Retrait d’un casque de protection à 2", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444447/retrait-d-un-casque?details=true" },
  { name: "Application de froid", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444368/application-de-froid?details=true" },
  { name: "Emballage au moyen d’un pansement stérile", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444389/emballage-au-moyen-d-un-pansement-sterile?details=true" },
  { name: "Réaliser un pansement", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444440/realiser-un-pansement?details=true" },
  { name: "Maintien d'un pansement", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444416/maintien-d-un-pansement?details=true" },
  { name: "Utilisation d’un lot membre sectionné", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444451/utilisation-d-un-lot-membre-sectionne?details=true" },
  { name: "Aide à la marche", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444460/aide-a-la-marche?details=true" },
  { name: "Arrimage d’une victime sur un dispositif de transport", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444369/arrimage-d-une-victime-sur-un-dispositif-de-transport?details=true" },
  { name: "Brancardage à 4 sauveteurs : passage étroit", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444373/brancardage-a-4-sauveteurs?details=true" },
  { name: "Brancardage à 4 sauveteurs : en pente ou dans un escalier", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444373/brancardage-a-4-sauveteurs?details=true" },
  { name: "Brancardage à 3 sauveteurs : en terrain plat", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444372/brancardage-a-3-sauveteurs?details=true" },
  { name: "Brancardage à 3 sauveteurs : franchissement d’obstacle", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444372/brancardage-a-3-sauveteurs?details=true" },
  { name: "Brancardage à 3 sauveteurs : passage étroit", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444372/brancardage-a-3-sauveteurs?details=true" },
  { name: "Brancardage à 3 sauveteurs : en pente ou dans un escalier", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444372/brancardage-a-3-sauveteurs?details=true" },
  { name: "Déplacement par une chaise à « mains »", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444385/deplacement-par-une-chaise-a-mains?details=true" },
  { name: "Déplacement d'une victime non-valide", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444383/deplacement-d-une-victime-non-valide?details=true" },
  { name: "Installation d’une victime dans un VSAV", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444409/installation-d-une-victime-dans-un-vsav?details=true" },
  { name: "Préparation d'un dispositif de portage", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444437/preparation-d-un-dispositif-de-portage?details=true" },
  { name: "Relevage au moyen d’un brancard cuillère", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444442/relevage-au-moyen-d-un-brancard-cuillere?details=true" },
  { name: "Pont amélioré", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444430/pont-a-4-sauveteurs?details=true", iframe: "https://www.youtube.com/embed/-5hCOq5GEm4?si=eVsSGpHKqmA6K0V4" },
  { name: "Pont néerlandais à 4 sauveteurs", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444430/pont-a-4-sauveteurs?details=true" },
  { name: "Pont simple", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444429/pont-a-3-sauveteurs?details=true", iframe: "https://www.youtube.com/embed/dGmoJ9KGauA?si=S0-_Zhx5VPBhgvze" },
  { name: "Pont néerlandais à 3 sauveteurs", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444429/pont-a-3-sauveteurs?details=true" },
  { name: "Relevage d’une victime plat dos, cuisses fléchies", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444443/relevage-d-une-victime-particuliere?details=true" },
  { name: "Relevage d’une victime en PLS", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444443/relevage-d-une-victime-particuliere?details=true" },
  { name: "Relevage d’une victime assise sur une chaise de transport", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444443/relevage-d-une-victime-particuliere?details=true" },
  { name: "Relevage d’une victime en position demi-assise", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444443/relevage-d-une-victime-particuliere?details=true" },
  { name: "Transfert d’une victime à l’aide d’une alèse portoir", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444450/transfert-d-une-victime-a-l-aide-d-une-alese-portoir?details=true" },
  { name: "Repérage nombreuses victimes", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444444/reperage-nombreuses-victimes?details=true" },
  { name: "Extraction latérale d'une victime en position assise", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444403/extraction-laterale-d-une-victime-en-position-assise?details=true" },
  { name: "Extraction latérale d'une victime en position allongée", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444402/extraction-laterale-d-une-victime-en-position-allongee?details=true" },
  { name: "Extraction axiale d'une victime", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444396/extraction-axiale-d-une-victime?details=true" },
  { name: "Extraction oblique d'une victime", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444404/extraction-oblique-d-une-victime?details=true" },
  { name: "Extraction d'une victime affalée sur le capot", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444401/extraction-d-une-victime-affalee-sur-le-capot?details=true" },
  { name: "Extraction d’une victime dans un véhicule immobilisé sur le toit", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444400/extraction-d-une-victime-dans-un-vehicule-immobilise-sur-le-toit?details=true" },
  { name: "Extraction d’une victime dans un véhicule immobilisé sur le côté", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444399/extraction-d-une-victime-dans-un-vehicule-immobilise-sur-le-cote?details=true" },
  { name: "Extraction d’une victime ceinturée dans un véhicule sur le toit", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444218/extraction-d-une-victime-ceinturee-dans-un-vehicule-sur-le-toit?details=true" },
  { name: "Extraction d’une victime dans un utilitaire ou sortie verticale", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444398/extraction-d-une-victime-dans-un-utilitaire-ou-sortie-verticale?details=true" },
  { name: "Balisage en virage", pdf: "Balisage en virage.pdf" },
  { name: "Balisage sur rond point", pdf: "Balisage sur rond point.pdf" },
  { name: "Balisage sur voies bidirectionnelles", pdf: "Balisage sur voies bidirectionnelles.pdf" },
  { name: "Balisage sur voies unidirectionnelles", pdf: "Balisage sur voies unidirectionnelles.pdf" },
  { name: "Utilisation des balises lumineuses", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2420850/fit-180-inc-balises-de-signalisation-lumineuses-flashcodes?details=true" },
  { name: "Utilisation des sangles rhinoevac", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2419175/fit-188-inc-sangle-multifonction-rhino-evac?details=true" },
  { name: "Utilisation de l'explosimètre Altair 4X",  url: "https://extranet.sdis37.fr/jcms/jcms/mig_2347135/fit-79-inc-explosimetre-toximetre-msa-altair-4x-4xr-ex-co-h2s?details=true" },
  { name: "Utilisation de la pompe de l'explosimètre Altair 4X", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2347136/fit-80-inc-pompe-explosimetre-toximetre-msa-4x-4xr?details=true" },
  { name: "Rideau stoppeur de fumée", url:"https://extranet.sdis37.fr/jcms/jcms/mig_2337590/fit-149-inc-rideau-stoppeur-de-fumees-v2-rsf?details=true" },
  { name: "Utilisation des lances", url: "https://extranet.sdis37.fr/jcms/jcms/1397_DBFileDocument/fit-042-inc-lance-slide-o-matic?details=true" },
  { name: "Utilisation du détécteur monoxyde de carbone", url: "https://extranet.sdis37.fr/jcms/jcms/1370_DBFileDocument/fit-88-inc-msa-detecteur-co?details=true"},
  { name: "Secours éléctrique du CIS", url: "https://extranet.sdis37.fr/jcms/jcms/1580_DBFileDocument/fit-142-div-secours-electrique-cis?details=true" },
  { name: "Mise en place du pédimat", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444427/pedimat?details=true" },
  { name: "Echelle 1 plan téléscopique", url: "https://extranet.sdis37.fr/jcms/jcms/1402_DBFileDocument/fit-058-inc-echelle-1-plan-telescopique?details=true" },
  { name: "Ceinturon d'intervention", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2288450/fit-69-top-ceinturons-d-intervention-v2?details=true" },
  { name: "Couteau à vêtement", url: "https://extranet.sdis37.fr/jcms/jcms/1413_DBFileDocument/fit-051-sap-couteau-a-vetement?details=true" },
  { name: "Coussin de tête", url: "https://extranet.sdis37.fr/jcms/jcms/1417_DBFileDocument/fit-111-sap-coussin-de-tete-pour-pls?details=true" },
  { name: "Corde flottante", url: "https://extranet.sdis37.fr/jcms/jcms/1406_DBFileDocument/fit-026-sap-corde-de-securite-flottante?details=true" }/*
  
  { name: "Tuyaux avec réserve en spirale", pdf: "Tuyaux avec réserve en spirale.pdf" },
  { name: "Detecteur CO", pdf: "Detecteur CO.pdf" },
  { name: "Anti-vol VSAV", pdf: "Anti-vol VSAV.pdf" },
{ name: "batfan", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2411835/fit-189-inc-ventilateur-sur-batterie-batfan?details=true"},
  { name: "Communication opérationnel-utilisation des radios", pdf: "Communication opérationnel-utilisation des radios.pdf" },
  { name: "Le repli d'urgence (FDF)", pdf: "Le repli d'urgence (FDF).pdf" },
  { name: "Etablissement de la LDT (FDF)", pdf: "Etablissement de la LDT (FDF).pdf" },
  { name: "L’établissement d’une lance 500 /d’une prise d’eau jusqu’à 120 mètres (FDF)", pdf: "etablissement d’une lance 500 (FDF).pdf" },
  { name: "La transformation d’une lance 500 en 2 lances 150 sans prolongement (FDF)", pdf: "La transformation d’une lance 500 en 2 lances 150 sans prolongement (FDF).pdf" },
  { name: "Le prolongement d’une lance 500 (FDF)", pdf: "Le prolongement d’une lance 500 (FDF).pdf" },
  { name: "La transformation d’une lance 500 en 2 lances 150 après prolongement (FDF)", pdf: "La transformation d’une lance 500 en 2 lances 150 après prolongement (FDF).pdf" },
  { name: "Déshabiller un sauveteur inconscient en tenue de feu", pdf: "Déshabiller un sauveteur inconscient en tenue de feu.pdf" },
  { name: "Extinction d'un feu de VL nouvelle énergie", pdf:"Extinction d'un feu de VL nouvelle énergie" },
  { name: "Utilisation d'une tronçonneuse", pdf: "Utilisation d'une tronçonneuse.pdf" },
{ name: "Optimisation du dispositif de ventilation", pdf: "Optimisation du dispositif de ventilation.pdf" },
{ name: "Ventilation par entraînement d'air aux lances", pdf: "Ventilation par entraînement d'air aux lances.pdf" },{ name: "Pompe prélèvement", pdf: "Pompe prélèvement.pdf" },
{ name: "LSPCC-Progression horizontale", pdf: "LSPCC-Progression horizontale.pdf" },
{ name: "Ouverture de porte Halligan+masse", pdf: "Ouverture de porte Halligan+masse.pdf" },
{ name: "Envoyer un message de détresse", pdf: "Envoyer un message de détresse.pdf" },
{ name: "Utilisation TGR", pdf: "Utilisation TGR.pdf" },
{ name: "CCRM-Utilisation du chariot de balisage", pdf: "CCRM-Utilisation du chariot de balisage.pdf" },
{ name: "Utilisation d'un extincteur", pdf: "Utilisation d'un extincteur.pdf" },
{ name: "Accident d’exposition à un risque viral", pdf: "Accident d’exposition à un risque viral.pdf" },
{ name: "Bilan d’urgence : XABCDE", pdf: "Bilan d’urgence : XABCDE.pdf" },
{ name: "Évaluer la motricité et la sensibilité", pdf: "Évaluer la motricité et la sensibilité.pdf" },
{ name: "Examiner les pupilles", pdf: "Examiner les pupilles.pdf" },
{ name: "Rechercher et apprécier le pouls carotidien", pdf: "Rechercher et apprécier le pouls carotidien.pdf" },
{ name: "Rechercher et apprécier le pouls radial", pdf: "Rechercher et apprécier le pouls radial.pdf" },
{ name: "Rechercher et apprécier le pouls huméral", pdf: "Rechercher et apprécier le pouls huméral.pdf" },
{ name: "Rechercher et apprécier le pouls fémoral", pdf: "Rechercher et apprécier le pouls fémoral.pdf" },
{ name: "Mesurer le temps de recoloration cutanée", pdf: "Mesurer le temps de recoloration cutanée.pdf" },
{ name: "Examen de la peau et des muqueuses", pdf: "Examen de la peau et des muqueuses.pdf" },
{ name: "Bilan complémentaire malade malaise", pdf: "Bilan complémentaire malade malaise.pdf" },
{ name: "Surveillance de la victime", pdf: "Surveillance de la victime.pdf" },
{ name: "Arroser une brûlure", pdf: "Arroser une brûlure.pdf" },
{ name: "Compression d’un saignement de nez", pdf: "Compression d’un saignement de nez.pdf" },
{ name: "Utilisation des emballages à élimination de déchets", pdf: "Utilisation des emballages à élimination de déchets.pdf" },
{ name: "Aspiration avec MPE", pdf: "Aspiration avec MPE.pdf" },
{ name: "Aspiration avec pompe électrique", pdf: "Aspiration avec pompe électrique.pdf" },
{ name: "Capture de serpent", pdf: "Capture de serpent.pdf" },
{ name: "Capture d'animaux au moyen du lasso", pdf: "Capture d'animaux au moyen du lasso.pdf" },
{ name: "Assèchement avec aspirateur", pdf: "Assèchement avec aspirateur.pdf" },

    Exemple d'ajout de document
    {
      name: "Mise en place d'un groupe électrogène",
      pdf: "Mise en place d'un groupe électrogène.pdf",
      image: "image1.jpg",
      video: "video1.mp4",
      iframe: "https://www.youtube.com/embed/aydVCwnWJII?si=GvSX5WT_lSbVdUKH",
      documents: [
        { name: "Document 1", url: "document1.pdf" },
        { name: "Document 2", url: "document2.pdf" }
      ]
    },
    */
    // Ajoutez plus de techniques selon vos besoins
  ];

  let technique = genererTechnique();

function genererTechnique() {
  const nombre = Math.floor(Math.random() * techniques.length);
  return techniques[nombre];
}

function genererNouvelleTechnique() {
  technique = genererTechnique();
}
</script>


<main>
  <h1>Générateur de Technique</h1>
  <div class="container">
    <div class="text">
      <p>Cliquez sur le bouton pour générer une technique</p>
    </div>
    <button on:click={genererNouvelleTechnique}>Générer</button>
    <div class="result">
      <h3>{technique.name}</h3>
      {#if technique.pdf}
        <a href={technique.pdf} target="_blank">Voir le PDF</a>
      {/if}
      {#if technique.image}
        <div class="image">
          <img src={technique.image} alt={technique.name} />
        </div>
      {/if}
      {#if technique.video}
        <div class="video">
          <video controls>
            <source src={technique.video} type="video/mp4" />
            Your browser does not support the video tag.
          </video>
        </div>
      {/if}
      {#if technique.iframe}
        <div class="iframe">
          <iframe src={technique.iframe} frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      {/if}
      {#if technique.url}
        <p>
          <a href={technique.url} target="_blank">Plus d'infos</a>
        </p>
      {/if}
      {#if technique.documents}
        <div class="documents">
          <h5>Documents supplémentaires :</h5>
          <ul>
            {#each technique.documents as doc}
              <li><a href={doc.url} target="_blank">{doc.name}</a></li>
            {/each}
          </ul>
        </div>
      {/if}
    </div>
  </div>
  <div class="mail">
    <a href="mailto:plbd@laposte.net">Suggérer une amélioration ?</a>
  </div>
</main>

<style>
/* Ajoutez vos styles ici */
.iframe {
  margin-top: 1em;
}

iframe {
  width: 100%;
  height: 315px;
}
</style>
