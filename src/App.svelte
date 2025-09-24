<script lang="ts">
  import { onMount } from "svelte";
  const techniques = [
    {
      name: "Utilisation du halligan-tool",
      url: "https://extranet.sdis37.fr/jcms/jcms/1401_DBFileDocument/fit-055-inc-outil-de-forcement-halligan-tool?details=true",
      documents: [{ name: "Halligan Tool", url: "Halligan Tool.pdf" }],
      category: "INC",
    },
    {
      name: "Mise en place d'un groupe électrogène",
      iframe: "https://www.youtube.com/embed/aydVCwnWJII?si=GvSX5WT_lSbVdUKH",
      category: "DIV",
    },
    {
      name: "Aspiration sur une bache à incendie",
      iframe: "https://www.youtube.com/embed/WI0d4eRLuxM?si=SdvN1LFSw5SDQSKq",
      category: "INC"
    },
    { name: "ETB1-Ldt", pdf: "ETB1-Ldt.pdf", category: "INC" },
    { name: "ETB2-Prise d'eau", pdf: "ETB2-Prise d'eau.pdf", category: "INC" },
    { name: "ETB3-Lance", pdf: "ETB3-Lance.pdf", category: "INC"},
    { name: "ETB4-Alimentation", pdf: "ETB4-Alimentation.pdf", category: "INC"},
    { name: "ETB5-Etablissement particuliers", pdf: "ETB5-Etablissement particuliers.pdf", category: "INC"},
    { name: "ETB6-Prolongement/remplacement", pdf: "ETB6-Prolongement/remplacement.pdf", category: "INC" },
    { name: "TDE1-Refroidissement des fumées", pdf: "TDE1-Refroidissement des fumées.pdf",category: "INC"},
    { name: "TDE2-Extinction directe", pdf: "TDE2-Extinction directe.pdf", category: "INC" },
    { name: "TDE3-Extinction indirecte", pdf: "TDE3-Extinction indirecte.pdf", category: "INC" },
    { name: "TDE4-Extinction combinée/massive", pdf: "TDE4-Extinction combinée/massive.pdf", category: "INC"},
    { name: "TDE5-Situation pre-backdraft", pdf: "TDE5-Situation pre-backdraft.pdf", category: "INC"},
    { name: "TDE6-Repli sous protection hydraulique", pdf: "TDE6-Repli sous protection hydraulique.pdf", category: "INC"},
    { name: "TDE7-Feu soumis aux effets du vent et effet chalumeau", pdf: "TDE7-Feu soumis aux effets du vent et effet chalumeau.pdf", category: "INC"},
    {
      name: "TDE8-Attaque d'atténuation",
      pdf: "TDE8-Attaque d'atténuation.pdf",
      category: "INC",
    },
    { name: "Contrôle croisé", pdf: "Contrôle croisé.pdf", category: "INC" },
    { name: "Engagement a vue", pdf: "Engagement a vue.pdf", category: "INC" },
    {
      name: "Engagement au moyen d'une ligne de vie",
      pdf: "Engagement au moyen d'une ligne de vie.pdf",
      category: "INC",
    },
    {
      name: "Engagement sur ligne de vie méthode latérale",
      pdf: "Engagement sur ligne de vie méthode latérale.pdf",
      category: "INC",
    },
    {
      name: "Engagement sur ligne de vie méthode circulaire",
      pdf: "Engagement sur ligne de vie méthode circulaire.pdf",
      category: "INC",
    },
    { name: "Méthode AIDES", pdf: "Méthode AIDES.pdf", category: "INC" },
    {
      name: "Deplacement-progression sous ARI",
      pdf: "Deplacement-progresnsion sous ARI.pdf",
      category: "INC",
    },
    {
      name: "Règle de marquage",
      pdf: "Règle de marquage.pdf",
      category: "INC",
    },
    {
      name: "Utilisation échelle à coulisse en mode secours",
      pdf: "Utilisation échelle à coulisse en mode secours.pdf",
      category: "INC",
    },
    {
      name: "Attendre les secours, binome en difficulté",
      pdf: "Attendre les secours.pdf",
      category: "INC",
    },
    {
      name: "Passage dans des fils ou des câbles",
      pdf: "Passage dans des fils ou des câbles.pdf",
      category: "INC",
    },
    {
      name: "Franchissement passage étroit",
      pdf: "Franchissement passage étroit.pdf",
      category: "INC",
    },
    {
      name: "Retrait de l'ARI-Autosauvetage",
      pdf: "Retrait de l'ARI-Autosauvetage.pdf",
      category: "INC",
    },
    {
      name: "Technique de respiration (gestion air)",
      pdf: "Technique de respiration (gestion air).pdf",
      category: "INC",
    },
    { name: "Gérer une fuite", pdf: "Gérer une fuite.pdf", category: "INC" },
    { name: "Bail-out", pdf: "Bail-out.pdf", category: "INC" },
    {
      name: "Evacuation au moyen d'un tuyau",
      pdf: "Evacuation au moyen d'un tuyau.pdf",
      category: "INC",
    },
    {
      name: "Evaluation et stabilisation d'un équipier en difficulté",
      pdf: "Evaluation et stabilisation d'un équipier en difficulté.pdf",
      category: "INC",
    },
    {
      name: "Traction au sol d'un SP sans matériel",
      pdf: "Traction au sol d'un SP sans matériel.pdf",
      category: "INC",
    },
    {
      name: "Traction au sol avec matériel",
      pdf: "Traction au sol avec matériel.pdf",
      category: "INC",
    },
    {
      name: "Sauvetage par un binome",
      pdf: "Sauvetage par un binome.pdf",
      category: "INC",
    },
    {
      name: "Evacuation par l'escalier",
      pdf: "Evacuation par l'escalier.pdf",
      category: "INC",
    },
    { name: "Le Denver-drill", pdf: "Le Denver-drill.pdf", category: "INC" },
    {
      name: "Technique d'évacuation de SP sur echelle à coulisse",
      pdf: "Technique d'évacuation de SP sur echelle à coulisse.pdf",
      category: "INC",
    },
    {
      name: "Remontée d'un équipier avec sa lance",
      pdf: "Remontée d'un équipier avec sa lance.pdf",
      category: "INC",
    },
    { name: "Le Nance-drill", pdf: "Le Nance-drill.pdf", category: "INC" },
    {
      name: "Utilisation de l'échelle à crochet",
      pdf: "Utilisation de l'échelle à crochet.pdf",
      category: "INC",
    },
    {
      name: "Cas particulier de l'utilisation de l'échelle à crochet",
      pdf: "Cas particulier de l'utilisation de l'échelle à crochet.pdf",
      category: "INC",
    },
    {
      name: "Utilisation échelle à coulisse-sauvetage d'un victime valide",
      pdf: "Utilisation échelle à coulisse-sauvetage d'un victime valide.pdf",
      category: "INC",
    },
    {
      name: "Utilisation échelle à coulisse-sauvetage d'un victime invalide",
      pdf: "Utilisation échelle à coulisse-sauvetage d'un victime invalide.pdf",
      category: "INC",
    },
    {
      name: "Utilisation échelle à coulisse en excavation",
      pdf: "Utilisation échelle à coulisse en excavation.pdf",
      category: "INC",
    },
    {
      name: "Accès à une personne visible en hauteur",
      pdf: "Accès à une personne visible en hauteur.pdf",
      category: "INC",
    },
    {
      name: "Utilisation particulière de l'échelle à coulisse",
      pdf: "Utilisation particulière de l'échelle à coulisse.pdf",
      category: "INC",
    },
    {
      name: "Dégagement d'urgence sans matériel",
      pdf: "Dégagement d'urgence sans matériel.pdf",
      category: "INC",
    },
    {
      name: "Dégagement d'urgence avec matériel",
      pdf: "Dégagement d'urgence avec matériel.pdf",
      category: "INC",
    },
    {
      name: "LSPCC-Sauvetage au moyen du harnais",
      pdf: "LSPCC-Sauvetage au moyen du harnais.pdf",
      category: "INC",
    },
    {
      name: "LSPCC-Sauvetage par l'extérieur",
      pdf: "LSPCC-Sauvetage par l'extérieur.pdf",
      category: "INC",
    },
    { name: "LSPCC-Excavation", pdf: "LSPCC-Excavation.pdf", category: "INC" },
    {
      name: "LSPCC-Reconnaissance d'appartement",
      pdf: "LSPCC-Reconnaissance d'appartement.pdf",
      category: "PPABE",
    },
    {
      name: "Décontamination aux fumées d'incendie",
      pdf: "Décontamination aux fumées d'incendie.pdf",
      category: "INC",
    },
    {
      name: "Retournement en urgence d’une victime à 2",
      pdf: "Retournement en urgence d’une victime à 2.pdf",
      category: "SUAP",
    },
    {
      name: "Retournement en urgence d’une victime à 1",
      pdf: "Retournement en urgence d’une victime à 1.pdf",
      category: "SUAP",
    },
    {
      name: "Evaluer la respiration",
      pdf: "Evaluer la respiration.pdf",
      category: "SUAP",
    },
    {
      name: "Evaluer la circulation",
      pdf: "Evaluer la circulation.pdf",
      category: "SUAP",
    },
    {
      name: "Mesurer la glycémie capillaire",
      pdf: "Mesurer la glycémie capillair.pdf",
      category: "SUAP",
    },
    {
      name: "Mesurer la pression artérielle (auto-tensiomètre)",
      pdf: "Mesurer la pression artérielle (auto-tensiomètre).pdf",
      category: "SUAP",
    },
    {
      name: "Mesure de la saturation en oxygène",
      pdf: "Mesure de la saturation en oxygène.pdf",
      category: "SUAP",
    },
    {
      name: "Mesurer la température de la victime",
      pdf: "Mesurer la température de la victime.pdf",
      category: "SUAP",
    },
    {
      name: "Evaluer la fonction neurologique",
      pdf: "Evaluer la fonction neurologique.pdf",
      category: "SUAP",
    },
    {
      name: "Recherche de lésions",
      pdf: "Recherche de lésions.pdf",
      category: "SUAP",
    },
    {
      name: "Équipement de protection risques infectieux",
      pdf: "Équipement de protection risques infectieux.pdf",
      category: "SUAP",
    },
    {
      name: "Friction des mains",
      pdf: "Friction des mains.pdf",
      category: "SUAP",
    },
    {
      name: "Lavage des mains",
      pdf: "Lavage des mains.pdf",
      category: "SUAP",
    },
    {
      name: "Mise en place de gants stériles",
      pdf: "Mise en place de gants stériles.pdf",
      category: "SUAP",
    },
    {
      name: "Nettoyage et désinfection d’un véhicule ou d’un local",
      pdf: "Nettoyage et désinfection d’un véhicule ou d’un local.pdf",
      category: "SUAP",
    },
    {
      name: "Nettoyage et désinfection du matériel",
      pdf: "Nettoyage et désinfection du matériel.pdf",
      category: "SUAP",
    },
    {
      name: "Retrait des gants à usage unique",
      pdf: "Retrait des gants à usage unique.pdf",
      category: "SUAP",
    },
    {
      name: "Lavage occulaire",
      pdf: "Lavage occulaire.pdf",
      category: "SUAP",
    },
    {
      name: "Aspiration de mucosités",
      pdf: "Aspiration de mucosités.pdf",
      category: "SUAP",
    },
    {
      name: "Compression manuelle",
      pdf: "Compression manuelle.pdf",
      category: "SUAP",
    },
    {
      name: "Compressions thoraciques (adultes)",
      pdf: "Compressions thoraciques (adultes).pdf",
      category: "SUAP",
    },
    {
      name: "Compressions thoraciques (enfant)",
      pdf: "Compressions thoraciques (enfant).pdf",
      category: "SUAP",
    },
    {
      name: "Compressions thoraciques (nourrisson, nouveau-né)",
      pdf: "Compressions thoraciques (nourrisson, nouveau-né).pdf",
      category: "SUAP",
    },
    {
      name: "Claques dans le dos (adulte et enfant)",
      pdf: "Claques dans le dos (adulte et enfant).pdf",
      category: "SUAP",
    },
    {
      name: "Claques dans le dos (nourrisson)",
      pdf:  "Claques dans le dos (nourrisson).pdf",
      category: "SUAP",
    },
    {
      name: "Désostruction par compressions abdominales (adulte et enfant)",
      pdf: "Désostruction par compressions abdominales (adulte et enfant).pdf",
      category: "SUAP",
    },
    {
      name: "Désostruction par compressions thoraciques (femme enceinte et obèse)",
      pdf: "Désostruction par compressions thoraciques (femme enceinte et obèse).pdf",
      category: "SUAP",
    },
    {
      name: "Désostruction par compressions thoraciques (nourrisson)",
      pdf: "Désostruction par compressions thoraciques (nourrisson).pdf",
      category: "SUAP",
    },
    {
      name: "Pose d’un garrot",
      pdf:  "Pose d’un garrot.pdf",
      category: "SUAP",
    },
    {
      name: "LVA victime assise",
      pdf: "LVA victime assise.pdf",
      category: "SUAP",
    },
    {
      name: "LVA victime non traumatisée",
      pdf: "LVA victime non traumatisée.pdf",
      category: "SUAP",
    },
    {
      name: "LVA victime traumatisée",
      pdf: "LVA victime traumatisée.pdf",
      category: "SUAP",
    },
    {
      name: "Mise en place d’une canule oropharyngée",
      pdf: "Mise en place d’une canule oropharyngée.pdf",
      category: "SUAP",
    },
    {
      name: "Pose d’un pansement compressif (israélien)",
      pdf: "Pose d’un pansement compressif (israélien).pdf",
      iframe: "https://www.youtube.com/embed/7G0jN--29bI?si=omYHBr3C3bKfA5pP",
      category: "SUAP",
    },
    {
      name: "Utilisation du DAE",
      pdf: "Utilisation du DAE.pdf",
      category: "SUAP",
    },
    {
      name: "Ventilation artificielle orale (adulte, enfant)",
      pdf: "Ventilation artificielle orale.pdf",
      category: "SUAP",
    },
    {
      name: "Ventilation artificielle orale (nourrisson, nouveau-né)",
      pdf:  "Ventilation artificielle orale.pdf",
      category: "SUAP",
    },
    {
      name: "Ventilation artificielle avec insufflateur (1 secouriste)",
      pdf: "Ventilation artificielle avec insufflateur.pdf",
      category: "SUAP",
    },
    {
      name: "Ventilation artificielle avec insufflateur (2 secouristes)",
      pdf: "Ventilation artificielle avec insufflateur.pdf",
      category: "SUAP",
    },
    {
      name: "PLS à 1 secouriste",
      pdf: "PLS à 1 secouriste.pdf",
      category: "SUAP",
    },
    {
      name: "PLS à 2 secouristes",
      pdf: "PLS à 2 secouristes.pdf",
      category: "SUAP",
    },
    {
      name: "Inhalation d’oxygène (masque haute concentration)",
      pdf: "Inhalation d’oxygène (masque haute concentration).pdf",
      category: "SUAP",
    },
    {
      name: "Utilisation d’une bouteille d’oxygène",
      pdf: "Utilisation d’une bouteille d’oxygène.pdf",
      category: "SUAP",
    },
    {
      name: "Réchauffement d'une victime",
      pdf: "Réchauffement d'une victime.pdf",
      category: "SUAP",
    },
    {
      name: "Les différentes positions d'attente",
      pdf: "Les différentes positions d'attente.pdf",
      category: "SUAP",
    },
    {
      name: "Aide à la prise de médicaments",
      pdf: "Aide à la prise de médicaments.pdf",
      category: "SUAP",
    },
    {
      name: "Manoeuvres physiques",
      pdf: "Manoeuvres physiques.pdf",
      category: "SUAP",
    },
    {
      name: "Soin au cordon",
      pdf: "Soin au cordon.pdf",
      category: "SUAP",
    },
    {
      name: "Réaliser un pansement non-occlusif",
      pdf: "Réaliser un pansement non-occlusif.pdf",
      category: "SUAP",
    },
    {
      name: "Immobilisation d’un membre avec une attelle à dépression",
      pdf: "Immobilisation d’un membre avec une attelle à dépression.pdf",
      category: "SUAP",
    },
    {
      name: "Immobilisation de l'épaule avec une attelle à dépression",
      pdf: "Immobilisation de l'épaule avec une attelle à dépression.pdf",
      category: "SUAP",
    },
    {
      name: "Écharpe simple",
      pdf: "Écharpe simple.pdf",
      category: "SUAP",
    },
    {
      name: "Contre-écharpe",
      pdf:  "Contre-écharpe.pdf",
      category: "SUAP",
    },
    {
      name: "Écharpe oblique",
      pdf: "Écharpe oblique.pdf",
      category: "SUAP",
    },
    {
      name: "Immobilisation victime plat dos sur plan dur",
      pdf: "Immobilisation victime plat dos sur plan dur.pdf",
      category: "SUAP",
    },
    {
      name: "Immobilisation victime allongée sur le ventre sur plan dur",
      pdf: "Immobilisation victime allongée sur le ventre sur plan dur.pdf",
      category: "SUAP",
    },
    {
      name: "Immobilisation victime debout sur plan dur",
      pdf: "Immobilisation victime debout sur plan dur.pdf",
      category: "SUAP",
    },
    {
      name: "Immobilisation au moyen du MID",
      pdf: "Immobilisation au moyen du MID.pdf",
      category: "SUAP",
    },
    {
      name: "Maintien de la tête à 2 mains victime debout ou assise",
      pdf: "Maintien de la tête à 2 mains victime debout ou assise.pdf",
      category: "SUAP",
    },
    {
      name: "Maintien de la tête à 2 mains victime plat dos",
      pdf: "Maintien de la tête à 2 mains victime plat dos.pdf",
      category: "SUAP",
    },
    {
      name: "Pose d’une attelle cervico-thoracique",
      pdf: "Pose d’une attelle cervico-thoracique.pdf",
      category: "SUAP",
    },
    {
      name: "Pose d’un collier cervical",
      pdf: "Pose d’un collier cervical.pdf",
      category: "SUAP",
    },
    {
      name: "Réalignement de membre",
      pdf: "Réalignement de membre.pdf",
      category: "SUAP",
    },
    {
      name: "Retrait d’un casque de protection en secouriste isolé",
      pdf: "Retrait d’un casque de protection en secouriste isolé.pdf",
      category: "SUAP",
    },
    {
      name: "Retrait d’un casque de protection à 2",
      pdf: "Retrait d’un casque de protection à 2.pdf",
      category: "SUAP",
    },
    {
      name: "Application de froid",
      pdf: "Application de froid.pdf",
      category: "SUAP",
    },
    {
      name: "Emballage au moyen d’un pansement stérile",
      pdf: "Emballage au moyen d’un pansement stérile.pdf",
      category: "SUAP",
    },
    {
      name: "Réaliser un pansement",
      pdf: "Réaliser un pansement.pdf",
      category: "SUAP",
    },
    {
      name: "Maintien d'un pansement",
      pdf: "Maintien d'un pansement.pdf",
      category: "SUAP",
    },
    {
      name: "Utilisation d’un lot membre sectionné",
      pdf: "Utilisation d’un lot membre sectionné.pdf",
      category: "SUAP",
    },
    {
      name: "Aide à la marche",
      pdf: "Aide à la marche.pdf",
      category: "SUAP",
    },
    {
      name: "Arrimage d’une victime sur un dispositif de transport",
      pdf: "Arrimage d’une victime sur un dispositif de transport.pdf",
      category: "SUAP",
    },
    {
      name: "Brancardage à 4 sauveteurs : passage étroit",
      pdf: "Brancardage à 4 sauveteurs.pdf",
      category: "SUAP",
    },
    {
      name: "Brancardage à 4 sauveteurs : en pente ou dans un escalier",
      pdf: "Brancardage à 4 sauveteurs.pdf",
      category: "SUAP",
    },
    {
      name: "Brancardage à 3 sauveteurs : en terrain plat",
      pdf: "Brancardage à 3 sauveteurs.pdf",
      category: "SUAP",
    },
    {
      name: "Brancardage à 3 sauveteurs : franchissement d’obstacle",
      pdf: "Brancardage à 3 sauveteurs.pdf",
      category: "SUAP",
    },
    {
      name: "Brancardage à 3 sauveteurs : passage étroit",
      pdf: "Brancardage à 3 sauveteurs.pdf",
      category: "SUAP",
    },
    {
      name: "Brancardage à 3 sauveteurs : en pente ou dans un escalier",
      pdf: "Brancardage à 3 sauveteurs.pdf",
      category: "SUAP",
    },
    {
      name: "Déplacement par une chaise à « mains »",
      pdf: "Déplacement par une chaise à « mains ».pdf",
      category: "SUAP",
    },
    {
      name: "Déplacement d'une victime non-valide",
      pdf: "Déplacement d'une victime non-valide.pdf",
      category: "SUAP",
    },
    {
      name: "Installation d’une victime dans un VSAV",
      pdf: "Installation d’une victime dans un VSAV.pdf",
      category: "SUAP",
    },
    {
      name: "Préparation d'un dispositif de portage",
      pdf: "Préparation d'un dispositif de portage.pdf",
      category: "SUAP",
    },
    {
      name: "Relevage au moyen d’un brancard cuillère",
      pdf: "Relevage au moyen d’un brancard cuillère.pdf",
      category: "SUAP",
    },
    {
      name: "Pont amélioré",
      pdf: "Pont à 4 sauveteurs.pdf",
      iframe: "https://www.youtube.com/embed/-5hCOq5GEm4?si=eVsSGpHKqmA6K0V4",
      category: "SUAP",
    },
    {
      name: "Pont néerlandais à 4 sauveteurs",
      pdf: "Pont à 4 sauveteurs.pdf",
      category: "SUAP",
    },
    {
      name: "Pont simple",
      pdf: "Pont à 3 sauveteurs.pdf",
      iframe: "https://www.youtube.com/embed/dGmoJ9KGauA?si=S0-_Zhx5VPBhgvze",
      category: "SUAP",
    },
    {
      name: "Pont néerlandais à 3 sauveteurs",
      pdf: "Pont à 3 sauveteurs.pdf",
      category: "SUAP",
    },
    {
      name: "Relevage d’une victime plat dos, cuisses fléchies",
      pdf: "Relevage d’une victime particuliere.pdf",
      category: "SUAP",
    },
    {
      name: "Relevage d’une victime en PLS",
      pdf: "Relevage d’une victime particuliere.pdf",
      category: "SUAP",
    },
    {
      name: "Relevage d’une victime assise sur une chaise de transport",
      pdf: "Relevage d’une victime particuliere.pdf",
      category: "SUAP",
    },
    {
      name: "Relevage d’une victime en position demi-assise",
      pdf: "Relevage d’une victime particuliere.pdf",
      category: "SUAP",
    },
    {
      name: "Transfert d’une victime à l’aide d’une alèse portoir",
      pdf: "Transfert d’une victime à l’aide d’une alèse portoir.pdf",
      category: "SUAP",
    },
    {
      name: "Repérage nombreuses victimes",
      pdf: "Repérage nombreuses victimes.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction latérale d'une victime en position assise",
      pdf: "Extraction latérale d'une victime en position assise.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction latérale d'une victime en position allongée",
      pdf: "Extraction latérale d'une victime en position allongée.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction axiale d'une victime",
      pdf: "Extraction axiale d'une victime.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction oblique d'une victime",
      pdf: "Extraction oblique d'une victime.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction d'une victime affalée sur le capot",
      pdf: "Extraction d'une victime affalée sur le capot.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction d’une victime dans un véhicule immobilisé sur le toit",
      pdf: "Extraction d’une victime dans un véhicule immobilisé sur le toit.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction d’une victime dans un véhicule immobilisé sur le côté",
      pdf: "Extraction d’une victime dans un véhicule immobilisé sur le côté.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction d’une victime ceinturée dans un véhicule sur le toit",
      pdf: "Extraction d’une victime ceinturée dans un véhicule sur le toit.pdf",
      category: "SUAP",
    },
    {
      name: "Extraction d’une victime dans un utilitaire ou sortie verticale",
      pdf: "Extraction d’une victime dans un utilitaire ou sortie verticale.pdf",
      category: "SUAP",
    },
    {
      name: "Balisage en virage",
      pdf: "Balisage en virage.pdf",
      category: "SR",
    },
    {
      name: "Balisage sur rond point",
      pdf: "Balisage sur rond point.pdf",
      category: "SR",
    },
    {
      name: "Balisage sur voies bidirectionnelles",
      pdf: "Balisage sur voies bidirectionnelles.pdf",
      category: "SR",
    },
    {
      name: "Balisage sur voies unidirectionnelles",
      pdf: "Balisage sur voies unidirectionnelles.pdf",
      category: "SR",
    },
    {
      name: "Utilisation des balises lumineuses",
      pdf: "Utilisation des balises lumineuses.pdf",
      category: "INC",
    },
    {
      name: "Utilisation des sangles rhinoevac",
      pdf: "Utilisation des sangles rhinoevac.pdf",
      category: "INC",
    },
    {
      name: "Utilisation de l'explosimètre Altair 4X",
      pdf: "Utilisation de l'explosimètre Altair 4X.pdf",
      category: "INC",
    },
    {
      name: "Utilisation de la pompe de l'explosimètre Altair 4X",
      pdf: "Utilisation de la pompe de l'explosimètre Altair 4X.pdf",
      category: "INC",
    },
    {
      name: "Utiisation du Rideau stoppeur de fumée",
      pdf: "Rideau stoppeur de fumée.pdf",
      category: "INC",
    },
    {
      name: "Utilisation des lances",
      pdf :"Utilisation des lances.pdf",
      category: "INC",
    },
    {
      name: "Utilisation du détécteur monoxyde de carbone",
      pdf: "Utilisation du détécteur monoxyde de carbone.pdf",
      category: "SUAP",
    },
    {
      name: "Secours éléctrique du CIS",
      pdf: "Secours éléctrique du CIS.pdf",
      category: "PPABE",
    },
    {
      name: "Mise en place du pédimat",
      pdf: "Mise en place du pédimat.pdf",
      category: "SUAP",
    },
    {
      name: "Echelle 1 plan téléscopique",
      updf: "Echelle 1 plan téléscopique.pdf",
      category: "INC",
    },
    {
      name: "Ceinturon d'intervention",
      pdf: "Ceinturon d'intervention.pdf",
      category: "INC",
    },
    {
      name: "Couteau à vêtement",
      pdf: "Couteau à vêtement.pdf",
      category: "SUAP",
    },
    {
      name: "Coussin de tête",
      pdf: "Coussin de tête.pdf",
      category: "SUAP",
    },
    {
      name: "Corde flottante",
      pdf: "Corde flottante.pdf",
      category: "SUAP",
    },
    {
      name: "Anti-vol VSAV",
      pdf: "Anti-vol VSAV.pdf",
      category: "SUAP",
    },
    {
      name: "Jalonnement dynamique",
      pdf: "Feux espaces naturels.pdf",
      category: "FDF",
    },
    {
      name: "Communication opérationnel-utilisation des radios",
      pdf: "Communication opérationnel-utilisation des radios.pdf",
      category: "PPABE",
    },
    {
      name: "Utilisation d'une tronçonneuse",
      pdf: "Utilisation d'une tronçonneuse.pdf",
      category: "PPABE",
    },
    {
      name: "habillage NRBC",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2088674/habillage-epi-nrbc?details=true",
      category: "RCH",
    },
    {
      name: "conductimetre",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048472/fiche-cond-315-i?details=true",
      category: "RCH",
    },
    {
      name: "Leve plaque et tampon d'égout",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048476/fit-leve-plaques-vap-37?details=true",
      category: "RCH",
    },
    {
      name: "Tenue GR Type1",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048477/fit-scaphandre-gr-iii-sol-3?details=true",
      category: "RCH",
    },
    {
      name: "Kit infectieux contagieux",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048478/fit-027-sap-utilisation-du-kit-risque-infectuex-contagieux?details=true",
      category: "RCH",
    },
    {
      name: "Mise en place de la douche",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048481/fit-094-rch-douche-individuelle?details=true",
      category: "RCH",
    },
    {
      name: "Utilisation de l'explosimètre Altair 4X",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2347135/fit-79-inc-explosimetre-toximetre-msa-altair-4x-4xr-ex-co-h2s?details=true",
      category: "RCH",
    },
    {
      name: "Utilisation de la pompe de l'explosimètre Altair 4X",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2347136/fit-80-inc-pompe-explosimetre-toximetre-msa-4x-4xr?details=true",
      category: "RCH",
    },
    {
      name: "Mise en place d'un SAS",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2068008/fit-14-bache-pour-sas-decontamination?details=true",
      category: "RCH",
    },
    {
      name: "Le zonage en rch",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2068009/fpo-13-mise-en-place-d-un-chantier-risque-chimique?details=true",
      category: "RCH",
    },
    {
      name: "Le lot PRV",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2373998/fit-caisse-prv?details=true",
      category: "RCH",
    },
    {
      name: "Utilisation de l'AP2C",
      documents: [
        { name: "Utilisation de l'appareil", url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048376/v1-ap2c?details=true" },
        { name: "Arbre de décision", url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048471/arbre-decision-toxique-de-guerre-format-excel?details=true" }
      ],
      category: "RCH",
    },
    {
      name: "Utilisation du detecteur CMS",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048377/v1-detecteur-cms?details=true",
      category: "RCH",
    },
    {
      name: "Utilisation des lances queue de paon",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048381/v1-lances-queue-de-paon?details=true",
      category: "RCH",
    },
    {
      name: "Utilisation de la pompe à membrane",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048385/v1-pompe-a-membrane?details=true",
      category: "RCH",
    },
    {
      name: "Procédure acétylene",
      url: "https://extranet.sdis37.fr/jcms/jcms/1480_DBFileDocument/fpo-027-rch-procedure-d-intervention-impliquant-une-bouteille-d-acetylene-v2?details=true",
      category: "RCH",
    },
    {
      name: "Obturation d'une citerne",
      url: "https://extranet.sdis37.fr/jcms/jcms/prod_2048376/v1-ap2c?details=true",
      category: "RCH",
    },
    { 
      name: "L’établissement d’une lance 500 /d’une prise d’eau jusqu’à 120 mètres", 
      pdf: "etablissement d’une lance 500 (FDF).pdf",
      category: "FDF", 
    },
    { 
      name: "Etablissement de la LDT", 
      pdf: "Etablissement de la LDT (FDF).pdf",
      category: "FDF", 
    },
    { 
      name: "La transformation d’une lance 500 en 2 lances 150 sans prolongement", 
      pdf: "La transformation d’une lance 500 en 2 lances 150 sans prolongement (FDF).pdf",
      category: "FDF", 
    },
    { 
      name: "Tuyaux avec réserve en spirale",
      pdf: "Tuyaux avec réserve en spirale.pdf",
      category: "INC", 
    },
    { 
      name: "Le repli d'urgence",
      pdf: "Le repli d'urgence (FDF).pdf",
      category: "FDF", 
    },
    {
      name: "Le prolongement d’une lance 500",
      pdf: "Le prolongement d’une lance 500 (FDF).pdf",
      category: "FDF",
    },
    { 
      name: "La transformation d’une lance 500 en 2 lances 150 après prolongement",
      pdf: "La transformation d’une lance 500 en 2 lances 150 après prolongement (FDF).pdf",
      category: "FDF",
    },
    { 
      name: "Déshabiller un sauveteur inconscient en tenue de feu", 
      pdf: "Déshabiller un sauveteur inconscient en tenue de feu.pdf",
      category: "INC",
    },
    { name: "Extinction d'un feu de VL nouvelle énergie", 
      pdf:"Extinction d'un feu de VL nouvelle énergie.pdf",
      documents: [{ name: "NDO IUV", url: "NDO IUV.pdf" }],
      category: "INC",
    },
    { 
      name: "Optimisation du dispositif de ventilation",
      pdf: "Optimisation du dispositif de ventilation.pdf",
      category: "INC",
    },
    { 
      name: "Ventilation par entraînement d'air aux lances",
      pdf: "Ventilation par entraînement d'air aux lances.pdf",
      category: "INC",
    },
    {
      name: "Usage de stoppeur de fumée",
      pdf: "Usage de stoppeur de fumée.pdf",
      category: "INC",
    },
    { 
      name: "Gestion d'un message de détresse",
      pdf: "Gestion d'un message de détresse.pdf",
      category: "PPABE",
    },
    { 
      name: "Technique de la voile",
      pdf: "Technique voile.pdf",
      iframe: "https://www.youtube.com/embed/8J2rKch35as?si=lS_15UsnDi0URn0Y",
      category: "SR",
    },
    { 
      name: "Le demi-pavillon latéral (ou charnière)",
      pdf: "charniere.pdf",
      iframe: "https://www.youtube.com/embed/ZnuzfLI_eac?si=tQMavRewSHu7qe4X",
      url: "https://www.youtube.com/embed/ZzenJFV_Hqw?si=dZ3b6_lb8tIPpkb2",
      category: "SR",
    },
    { 
      name: "Le pavillon",
      pdf: "pavillon.pdf",
      iframe: "https://www.youtube.com/embed/3YvsSsEJjoQ?si=CfxJwPYV0pahnPhS",
      category: "SR",
    },
    { 
      name: "Le demi-pavillon",
      pdf: "demi-pavillon.pdf",
      iframe: "https://www.youtube.com/embed/UNj0QyaSJ4A?si=Msvq_KO19SmzDy1S",
      category: "SR",
    },
    { 
      name: "Action sur les pédales",
      iframe: "https://www.youtube.com/embed/2KS1VGHs8Qo?si=hPQb5NVSyfJwxjuJ",
      category: "SR",
    },
    { 
      name: "Ouverture de porte",
      pdf: "ouverture de porte.pdf",
      iframe: "https://www.youtube.com/embed/5CjpaXkETCk?si=XBiluJ4XXFyODkW4",
      category: "SR",
    },
    { 
      name: "Ouverture de coffre et capot",
      pdf: "ouverture capot.pdf",
      iframe: "https://www.youtube.com/embed/5CjpaXkETCk?si=XBiluJ4XXFyODkW4",
      category: "SR",
    },
    { 
      name: "Reformation d'habitacle",
      pdf: "reformation habitacle.pdf",
      iframe: "https://www.youtube.com/embed/AF1nPsip3DI?si=vL8Ujy0IuAjgZz-D",
      category: "SR",
    },
    { 
      name: "Traverse du tableau de bord",
      pdf: "relevage tableau bord.pdf",
      iframe: "https://www.youtube.com/embed/xL61eO772Es?si=gVQFJf0SLAGe1c23",
      category: "SR",
    },
    { 
      name: "Dépose d'une porte d'un véhicule utilitaire",
      pdf: "ouverture porte coulissante.pdf",
      iframe: "https://www.youtube.com/embed/yGaLkCXSWMI?si=4Cq4Lnj7xUWfpPBZ",
      category: "SR",
    },
    { 
      name: "Entretien des outils de désincarcération après utilisation",
      iframe: "https://www.youtube.com/embed/N7tFoW7ktOE?si=Ty5VT8fYTyaqP8C1",
      category: "SR",
    },
    { 
      name: "Arrimage d'un véhicule",
      pdf: "arrimage dun vl.pdf",
      category: "SR",
    },
    { 
      name: "Immobilisation d'un véhicule sur ses 5 roues",
      pdf: "immobilisation dun vl sur 5 roues.pdf",
      category: "SR",
    },
    { 
      name: "immobilisation d'un véhicule sur le flanc",
      pdf: "immobilisation dun vl sur le flanc.pdf",
      category: "SR",
    },
    { 
      name: "immobilisation d'un véhicule sur le toit",
      pdf: "immobilisation dun vl sur le toit.pdf",
      category: "SR",
    },
    { 
      name: "gestion des vitrages",
      pdf: "gestion des vitrages.pdf",
      category: "SR",
    },
    { 
      name: "Troisième porte",
      pdf: "troisieme porte.pdf",
      category: "SR",
    },
    { 
      name: "Alerte évacuation générale",
      pdf: "Alerte évacuation générale.pdf",
      category: "INC",
    },
    { 
      name: "",
      pdf: "Alerte évacuation générale.pdf",
      category: "INC",
    },
    /*
{ name: "batfan", url: "https://extranet.sdis37.fr/jcms/jcms/mig_2411835/fit-189-inc-ventilateur-sur-batterie-batfan?details=true"},

{ name: "Pompe prélèvement", pdf: "Pompe prélèvement.pdf" },
{ name: "LSPCC-Progression horizontale", pdf: "LSPCC-Progression horizontale.pdf" },
{ name: "Ouverture de porte Halligan+masse", pdf: "Ouverture de porte Halligan+masse.pdf" },
{ name: "Utilisation TGR", pdf: "Utilisation TGR.pdf" },
{ name: "CCRM-Utilisation du chariot de balisage", pdf: "CCRM-Utilisation du chariot de balisage.pdf" },
{ name: "Utilisation d'un extincteur", pdf: "Utilisation d'un extincteur.pdf" },
{ name: "Accident d’exposition à un risque viral", pdf: "Accident d’exposition à un risque viral.pdf" },
{ name: "Évaluer la motricité et la sensibilité", pdf: "Évaluer la motricité et la sensibilité.pdf" },
{ name: "Examiner les pupilles", pdf: "Examiner les pupilles.pdf" },
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

  let categories = ["TOUTES", "INC", "SUAP", "PPABE", "SR", "FDF"];
  let selectedCategories: Array<string> = [];
  let result = null;

  function toggleCategory(category: string) {
    if (category === "TOUTES") {
      if (selectedCategories.find((elt) => elt === "TOUTES")) {
        selectedCategories = [];
      } else {
        selectedCategories = [...categories];
      }
    } else {
      if (selectedCategories.find((elt) => elt === category)) {
        selectedCategories = selectedCategories.filter(
          (elt) => elt !== category && elt !== "TOUTES"
        );
      } else {
        selectedCategories = [...selectedCategories, category];
      }
      if (selectedCategories.length === categories.length - 1) {
        selectedCategories = [...selectedCategories, "TOUTES"];
      }
    }
  }

  function genererNouvelleTechnique() {
    let selectedTechniques = techniques.filter((t) =>
      selectedCategories.find((elt) => elt === t.category)
    );
    if (selectedTechniques.length > 0) {
      result =
        selectedTechniques[
          Math.floor(Math.random() * selectedTechniques.length)
        ];
    } else {
      alert("Veuillez sélectionner au moins une catégorie avant de générer")
      result = null;
    }
  }
</script>

<main>
  <h1>Générateur de Technique</h1>
  <div class="container">
    <div class="text">
      <p>Sélectionnez les catégories de techniques :</p>
    </div>
    <div class="categories">
      {#each categories as category}
        <div class="category">
          <label>
            <input
              type="checkbox"
              checked={!!selectedCategories.find((elt) => elt === category)}
              on:change={() => toggleCategory(category)}
            />
            {category}
          </label>
        </div>
      {/each}
    </div>
    <button on:click={genererNouvelleTechnique}>Générer</button>
    <div class="result">
      {#if result}
        <h3>{result.name}</h3>
        {#if result.pdf}
          <a href={result.pdf} target="_blank">Voir le PDF</a>
        {/if}
        {#if result.image}
          <div class="image">
            <img src={result.image} alt={result.name} />
          </div>
        {/if}
        {#if result.video}
          <div class="video">
            <video controls>
              <source src={result.video} type="video/mp4" />
              Your browser does not support the video tag.
            </video>
          </div>
        {/if}
        {#if result.iframe}
          <div class="iframe">
            <iframe
              src={result.iframe}
              frameborder="0"
              allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
          </div>
        {/if}
        {#if result.url}
          <p>
            <a href={result.url} target="_blank">Plus d'infos</a>
          </p>
        {/if}
        {#if result.documents}
          <div class="documents">
            <h5>Documents supplémentaires :</h5>
            <ul>
              {#each result.documents as doc}
                <li><a href={doc.url} target="_blank">{doc.name}</a></li>
              {/each}
            </ul>
          </div>
        {/if}
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
