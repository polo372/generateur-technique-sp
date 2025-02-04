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
      name: "Aspiration du bache à incendie",
      iframe: "https://www.youtube.com/embed/WI0d4eRLuxM?si=SdvN1LFSw5SDQSKq",
      category: "INC",
    },
    { name: "ETB1-Ldt", pdf: "ETB1-Ldt.pdf", category: "INC" },
    { name: "ETB2-Prise d'eau", pdf: "ETB2-Prise d'eau.pdf", category: "INC" },
    { name: "ETB3-Lance", pdf: "ETB3-Lance.pdf", category: "INC" },
    {
      name: "ETB4-Alimentation",
      pdf: "ETB4-Alimentation.pdf",
      category: "INC",
    },
    {
      name: "ETB5-Etablissement particuliers",
      pdf: "ETB5-Etablissement particuliers.pdf",
      category: "INC",
    },
    {
      name: "ETB6-Prolongement/remplacement",
      pdf: "ETB6-Prolongement/remplacement.pdf",
      category: "INC",
    },
    {
      name: "TDE1-Refroidissement des fumées",
      pdf: "TDE1-Refroidissement des fumées.pdf",
      category: "INC",
    },
    {
      name: "TDE2-Extinction directe",
      pdf: "TDE2-Extinction directe.pdf",
      category: "INC",
    },
    {
      name: "TDE3-Extinction indirecte",
      pdf: "TDE3-Extinction indirecte.pdf",
      category: "INC",
    },
    {
      name: "TDE4-Extinction combinée/massive",
      pdf: "TDE4-Extinction combinée/massive.pdf",
      category: "INC",
    },
    {
      name: "TDE5-Situation pre-backdraft",
      pdf: "TDE5-Situation pre-backdraft.pdf",
      category: "INC",
    },
    {
      name: "TDE6-Repli sous protection hydraulique",
      pdf: "TDE6-Repli sous protection hydraulique.pdf",
      category: "INC",
    },
    {
      name: "TDE7-Feu soumis aux effets du vent et effet chalumeau",
      pdf: "TDE7-Feu soumis aux effets du vent et effet chalumeau.pdf",
      category: "INC",
    },
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
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444223/retournement-en-urgence-d-une-victime-a-1?details=true",
      category: "SAP",
    },
    {
      name: "Retournement en urgence d’une victime à 1",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444445/retournement-en-urgence-d-une-victime-a-1?details=true",
      category: "SAP",
    },
    {
      name: "Evaluer la respiration",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444395/evaluer-la-respiration?details=true",
      category: "SAP",
    },
    {
      name: "Evaluer la circulation",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444393/evaluer-la-circulation?details=true",
      category: "SAP",
    },
    {
      name: "Mesurer la glycémie capillaire",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444419/mesurer-la-glycemie-capillaire?details=true",
      category: "SAP",
    },
    {
      name: "Mesurer la pression artérielle (auto-tensiomètre)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444420/mesurer-la-pression-arterielle-auto-tensiometre?details=true",
      category: "SAP",
    },
    {
      name: "Mesure de la saturation en oxygène",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444418/mesure-de-la-saturation-en-oxygene?details=true",
      category: "SAP",
    },
    {
      name: "Mesurer la température de la victime",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444421/mesurer-la-temperature-de-la-victime?details=true",
      category: "SAP",
    },
    {
      name: "Evaluer la fonction neurologique",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444394/evaluer-la-fonction-neurologique?details=true",
      category: "SAP",
    },
    {
      name: "Recherche de lésions",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444222/recherche-de-lesions?details=true",
      category: "SAP",
    },
    {
      name: "Équipement de protection risques infectieux",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444390/equipement-de-protection-risques-infectieux?details=true",
      category: "SAP",
    },
    {
      name: "Friction des mains",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444405/friction-des-mains?details=true",
      category: "SAP",
    },
    {
      name: "Lavage des mains",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444410/lavage-des-mains?details=true",
      category: "SAP",
    },
    {
      name: "Mise en place de gants stériles",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444423/mise-en-place-de-gants-steriles?details=true",
      category: "SAP",
    },
    {
      name: "Nettoyage et désinfection d’un véhicule ou d’un local",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444424/nettoyage-et-desinfection-d-un-vehicule-ou-d-un-local?details=true",
      category: "SAP",
    },
    {
      name: "Nettoyage et désinfection du matériel",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444425/nettoyage-et-desinfection-du-materiel?details=true",
      category: "SAP",
    },
    {
      name: "Retrait des gants à usage unique",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444448/retrait-des-gants-a-usage-unique?details=true",
      category: "SAP",
    },
    {
      name: "Lavage occulaire",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444411/lavage-occulaire?details=true",
      category: "SAP",
    },
    {
      name: "Aspiration de mucosités",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444370/aspiration-de-mucosites?details=true",
      category: "SAP",
    },
    {
      name: "Compression manuelle",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444375/compression-manuelle?details=true",
      category: "SAP",
    },
    {
      name: "Compressions thoraciques (adultes)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444376/compressions-thoraciques?details=true",
      category: "SAP",
    },
    {
      name: "Compressions thoraciques (enfant)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444376/compressions-thoraciques?details=true",
      category: "SAP",
    },
    {
      name: "Compressions thoraciques (nourrisson, nouveau-né)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444376/compressions-thoraciques?details=true",
      category: "SAP",
    },
    {
      name: "Claques dans le dos (adulte et enfant)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444374/claques-dans-le-dos?details=true",
      category: "SAP",
    },
    {
      name: "Claques dans le dos (nourrisson)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444374/claques-dans-le-dos?details=true",
      category: "SAP",
    },
    {
      name: "Désostruction par compressions abdominales (adulte et enfant)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444386/desostruction-par-compressions-abdominale?details=true",
      category: "SAP",
    },
    {
      name: "Désostruction par compressions thoraciques (femme enceinte et obèse)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444387/desostruction-par-compressions?details=true",
      category: "SAP",
    },
    {
      name: "Désostruction par compressions thoraciques (nourrisson)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444387/desostruction-par-compressions?details=true",
      category: "SAP",
    },
    {
      name: "Pose d’un garrot",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444433/pose-d-un-garrot?details=true",
      category: "SAP",
    },
    {
      name: "LVA victime assise",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444412/lva-victime-assise?details=true",
      category: "SAP",
    },
    {
      name: "LVA victime non traumatisée",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444413/lva-victime-non-traumatisee?details=true",
      category: "SAP",
    },
    {
      name: "LVA victime traumatisée",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444414/lva-victime-traumatisee?details=true",
      category: "SAP",
    },
    {
      name: "Mise en place d’une canule oropharyngée",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444422/mise-en-place-d-une-canule-oropharyngee?details=true",
      category: "SAP",
    },
    {
      name: "Pose d’un pansement compressif (israélien)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444435/pose-d-un-pansement-compressif-israelien?details=true",
      iframe: "https://www.youtube.com/embed/7G0jN--29bI?si=omYHBr3C3bKfA5pP",
      category: "SAP",
    },
    {
      name: "Utilisation du DAE",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444454/utilisation-du-dae?details=true",
      category: "SAP",
    },
    {
      name: "Ventilation artificielle orale (adulte, enfant)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444456/ventilation-artificielle-orale?details=true",
      category: "SAP",
    },
    {
      name: "Ventilation artificielle orale (nourrisson, nouveau-né)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444456/ventilation-artificielle-orale?details=true",
      category: "SAP",
    },
    {
      name: "Ventilation artificielle avec insufflateur (1 secouriste)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444455/ventilation-artificielle-avec-insufflateur?details=true",
      category: "SAP",
    },
    {
      name: "Ventilation artificielle avec insufflateur (2 secouristes)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444455/ventilation-artificielle-avec-insufflateur?details=true",
      category: "SAP",
    },
    {
      name: "PLS à 1 secouriste",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444426/pls-a-1-secouriste?details=true",
      category: "SAP",
    },
    {
      name: "PLS à 2 secouristes",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444428/pls-a-2-secouristes?details=true",
      category: "SAP",
    },
    {
      name: "Inhalation d’oxygène (masque haute concentration)",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444458/administration-d-oxygene-par-inhalation?details=true",
      category: "SAP",
    },
    {
      name: "Utilisation d’une bouteille d’oxygène",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444453/utilisation-d-une-bouteille-d-oxygene?details=true",
      category: "SAP",
    },
    {
      name: "Réchauffement d'une victime",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444441/rechauffement-d-une-victime?details=true",
      category: "SAP",
    },
    {
      name: "Les différentes positions d'attente",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444436/position-d-attente?details=true",
      category: "SAP",
    },
    {
      name: "Aide à la prise de médicaments",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444461/aide-a-la-prise-de-medicaments?details=true",
      category: "SAP",
    },
    {
      name: "Manoeuvres physiques",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444417/manoeuvres-physiques?details=true",
      category: "SAP",
    },
    {
      name: "Soin au cordon",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444452/soin-au-cordon?details=true",
      category: "SAP",
    },
    {
      name: "Réaliser un pansement non-occlusif",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444439/realiser-un-pansement-non-occlusif?details=true",
      category: "SAP",
    },
    {
      name: "Contention pelvienne",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444377/contention-pelvienne?details=true",
      category: "SAP",
    },
    {
      name: "Immobilisation d’un membre avec une attelle à dépression",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444431/pose-d-attelle-a-depression?details=true",
      category: "SAP",
    },
    {
      name: "Immobilisation de l'épaule avec une attelle à dépression",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444431/pose-d-attelle-a-depression?details=true",
      category: "SAP",
    },
    {
      name: "Écharpe simple",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444388/echarpe?details=true",
      category: "SAP",
    },
    {
      name: "Contre-écharpe",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444388/echarpe?details=true",
      category: "SAP",
    },
    {
      name: "Écharpe oblique",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444388/echarpe?details=true",
      category: "SAP",
    },
    {
      name: "Immobilisation victime plat dos sur plan dur",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444408/immobilisation-sur-plan-dur?details=true",
      category: "SAP",
    },
    {
      name: "Immobilisation victime allongée sur le ventre sur plan dur",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444408/immobilisation-sur-plan-dur?details=true",
      category: "SAP",
    },
    {
      name: "Immobilisation victime debout sur plan dur",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444408/immobilisation-sur-plan-dur?details=true",
      category: "SAP",
    },
    {
      name: "Immobilisation au moyen du MID",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444406/immobilisation-au-moyen-du-mid?details=true",
      category: "SAP",
    },
    {
      name: "Maintien de la tête à 2 mains victime debout ou assise",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444415/maintien-de-la-tete?details=true",
      category: "SAP",
    },
    {
      name: "Maintien de la tête à 2 mains victime plat dos",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444415/maintien-de-la-tete?details=true",
      category: "SAP",
    },
    {
      name: "Pose d’une attelle cervico-thoracique",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444434/pose-d-une-attelle-cervico-thoracique?details=true",
      category: "SAP",
    },
    {
      name: "Pose d’un collier cervical",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444432/pose-d-un-collier-cervical?details=true",
      category: "SAP",
    },
    {
      name: "Réalignement de membre",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444438/realignement-de-membre?details=true",
      category: "SAP",
    },
    {
      name: "Retrait d’un casque de protection en secouriste isolé",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444447/retrait-d-un-casque?details=true",
      category: "SAP",
    },
    {
      name: "Retrait d’un casque de protection à 2",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444447/retrait-d-un-casque?details=true",
      category: "SAP",
    },
    {
      name: "Application de froid",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444368/application-de-froid?details=true",
      category: "SAP",
    },
    {
      name: "Emballage au moyen d’un pansement stérile",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444389/emballage-au-moyen-d-un-pansement-sterile?details=true",
      category: "SAP",
    },
    {
      name: "Réaliser un pansement",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444440/realiser-un-pansement?details=true",
      category: "SAP",
    },
    {
      name: "Maintien d'un pansement",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444416/maintien-d-un-pansement?details=true",
      category: "SAP",
    },
    {
      name: "Utilisation d’un lot membre sectionné",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444451/utilisation-d-un-lot-membre-sectionne?details=true",
      category: "SAP",
    },
    {
      name: "Aide à la marche",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444460/aide-a-la-marche?details=true",
      category: "SAP",
    },
    {
      name: "Arrimage d’une victime sur un dispositif de transport",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444369/arrimage-d-une-victime-sur-un-dispositif-de-transport?details=true",
      category: "SAP",
    },
    {
      name: "Brancardage à 4 sauveteurs : passage étroit",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444373/brancardage-a-4-sauveteurs?details=true",
      category: "SAP",
    },
    {
      name: "Brancardage à 4 sauveteurs : en pente ou dans un escalier",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444373/brancardage-a-4-sauveteurs?details=true",
      category: "SAP",
    },
    {
      name: "Brancardage à 3 sauveteurs : en terrain plat",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444372/brancardage-a-3-sauveteurs?details=true",
      category: "SAP",
    },
    {
      name: "Brancardage à 3 sauveteurs : franchissement d’obstacle",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444372/brancardage-a-3-sauveteurs?details=true",
      category: "SAP",
    },
    {
      name: "Brancardage à 3 sauveteurs : passage étroit",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444372/brancardage-a-3-sauveteurs?details=true",
      category: "SAP",
    },
    {
      name: "Brancardage à 3 sauveteurs : en pente ou dans un escalier",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444372/brancardage-a-3-sauveteurs?details=true",
      category: "SAP",
    },
    {
      name: "Déplacement par une chaise à « mains »",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444385/deplacement-par-une-chaise-a-mains?details=true",
      category: "SAP",
    },
    {
      name: "Déplacement d'une victime non-valide",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444383/deplacement-d-une-victime-non-valide?details=true",
      category: "SAP",
    },
    {
      name: "Installation d’une victime dans un VSAV",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444409/installation-d-une-victime-dans-un-vsav?details=true",
      category: "SAP",
    },
    {
      name: "Préparation d'un dispositif de portage",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444437/preparation-d-un-dispositif-de-portage?details=true",
      category: "SAP",
    },
    {
      name: "Relevage au moyen d’un brancard cuillère",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444442/relevage-au-moyen-d-un-brancard-cuillere?details=true",
      category: "SAP",
    },
    {
      name: "Pont amélioré",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444430/pont-a-4-sauveteurs?details=true",
      iframe: "https://www.youtube.com/embed/-5hCOq5GEm4?si=eVsSGpHKqmA6K0V4",
      category: "SAP",
    },
    {
      name: "Pont néerlandais à 4 sauveteurs",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444430/pont-a-4-sauveteurs?details=true",
      category: "SAP",
    },
    {
      name: "Pont simple",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444429/pont-a-3-sauveteurs?details=true",
      iframe: "https://www.youtube.com/embed/dGmoJ9KGauA?si=S0-_Zhx5VPBhgvze",
      category: "SAP",
    },
    {
      name: "Pont néerlandais à 3 sauveteurs",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444429/pont-a-3-sauveteurs?details=true",
      category: "SAP",
    },
    {
      name: "Relevage d’une victime plat dos, cuisses fléchies",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444443/relevage-d-une-victime-particuliere?details=true",
      category: "SAP",
    },
    {
      name: "Relevage d’une victime en PLS",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444443/relevage-d-une-victime-particuliere?details=true",
      category: "SAP",
    },
    {
      name: "Relevage d’une victime assise sur une chaise de transport",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444443/relevage-d-une-victime-particuliere?details=true",
      category: "SAP",
    },
    {
      name: "Relevage d’une victime en position demi-assise",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444443/relevage-d-une-victime-particuliere?details=true",
      category: "SAP",
    },
    {
      name: "Transfert d’une victime à l’aide d’une alèse portoir",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444450/transfert-d-une-victime-a-l-aide-d-une-alese-portoir?details=true",
      category: "SAP",
    },
    {
      name: "Repérage nombreuses victimes",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444444/reperage-nombreuses-victimes?details=true",
      category: "SAP",
    },
    {
      name: "Extraction latérale d'une victime en position assise",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444403/extraction-laterale-d-une-victime-en-position-assise?details=true",
      category: "SAP",
    },
    {
      name: "Extraction latérale d'une victime en position allongée",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444402/extraction-laterale-d-une-victime-en-position-allongee?details=true",
      category: "SAP",
    },
    {
      name: "Extraction axiale d'une victime",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444396/extraction-axiale-d-une-victime?details=true",
      category: "SAP",
    },
    {
      name: "Extraction oblique d'une victime",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444404/extraction-oblique-d-une-victime?details=true",
      category: "SAP",
    },
    {
      name: "Extraction d'une victime affalée sur le capot",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444401/extraction-d-une-victime-affalee-sur-le-capot?details=true",
      category: "SAP",
    },
    {
      name: "Extraction d’une victime dans un véhicule immobilisé sur le toit",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444400/extraction-d-une-victime-dans-un-vehicule-immobilise-sur-le-toit?details=true",
      category: "SAP",
    },
    {
      name: "Extraction d’une victime dans un véhicule immobilisé sur le côté",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444399/extraction-d-une-victime-dans-un-vehicule-immobilise-sur-le-cote?details=true",
      category: "SAP",
    },
    {
      name: "Extraction d’une victime ceinturée dans un véhicule sur le toit",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444218/extraction-d-une-victime-ceinturee-dans-un-vehicule-sur-le-toit?details=true",
      category: "SAP",
    },
    {
      name: "Extraction d’une victime dans un utilitaire ou sortie verticale",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444398/extraction-d-une-victime-dans-un-utilitaire-ou-sortie-verticale?details=true",
      category: "SAP",
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
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2420850/fit-180-inc-balises-de-signalisation-lumineuses-flashcodes?details=true",
      category: "INC",
    },
    {
      name: "Utilisation des sangles rhinoevac",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2419175/fit-188-inc-sangle-multifonction-rhino-evac?details=true",
      category: "INC",
    },
    {
      name: "Utilisation de l'explosimètre Altair 4X",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2347135/fit-79-inc-explosimetre-toximetre-msa-altair-4x-4xr-ex-co-h2s?details=true",
      category: "INC",
    },
    {
      name: "Utilisation de la pompe de l'explosimètre Altair 4X",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2347136/fit-80-inc-pompe-explosimetre-toximetre-msa-4x-4xr?details=true",
      category: "INC",
    },
    {
      name: "Rideau stoppeur de fumée",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2337590/fit-149-inc-rideau-stoppeur-de-fumees-v2-rsf?details=true",
      category: "INC",
    },
    {
      name: "Utilisation des lances",
      url: "https://extranet.sdis37.fr/jcms/jcms/1397_DBFileDocument/fit-042-inc-lance-slide-o-matic?details=true",
      category: "INC",
    },
    {
      name: "Utilisation du détécteur monoxyde de carbone",
      url: "https://extranet.sdis37.fr/jcms/jcms/1370_DBFileDocument/fit-88-inc-msa-detecteur-co?details=true",
    },
    {
      name: "Secours éléctrique du CIS",
      url: "https://extranet.sdis37.fr/jcms/jcms/1580_DBFileDocument/fit-142-div-secours-electrique-cis?details=true",
      category: "PPABE",
    },
    {
      name: "Mise en place du pédimat",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444427/pedimat?details=true",
      category: "SAP",
    },
    {
      name: "Echelle 1 plan téléscopique",
      url: "https://extranet.sdis37.fr/jcms/jcms/1402_DBFileDocument/fit-058-inc-echelle-1-plan-telescopique?details=true",
      category: "INC",
    },
    {
      name: "Ceinturon d'intervention",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2288450/fit-69-top-ceinturons-d-intervention-v2?details=true",
      category: "INC",
    },
    {
      name: "Couteau à vêtement",
      url: "https://extranet.sdis37.fr/jcms/jcms/1413_DBFileDocument/fit-051-sap-couteau-a-vetement?details=true",
      category: "SAP",
    },
    {
      name: "Coussin de tête",
      url: "https://extranet.sdis37.fr/jcms/jcms/1417_DBFileDocument/fit-111-sap-coussin-de-tete-pour-pls?details=true",
      category: "SAP",
    },
    {
      name: "Corde flottante",
      url: "https://extranet.sdis37.fr/jcms/jcms/1406_DBFileDocument/fit-026-sap-corde-de-securite-flottante?details=true",
      category: "SAP",
    },
    {
      name: "Anti-vol VSAV",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2444371/anti-vol-vsav?details=true",
      category: "SAP",
    },
    {
      name: "Jalonnement dynamique",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2273210/fpo-037-fdf-feux-espaces-naturels-cas-particuliers-feux-recoltes-sur-pied-ou-chaumes-v3?details=true",
      category: "FDF",
    },
    {
      name: "Communication opérationnel-utilisation des radios",
      url: "https://extranet.sdis37.fr/jcms/jcms/mig_2276244/fpo-61-div-communication-radio-chef-d-agres-et-binomes?details=true",
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
      iframe: "https://www.youtube.com/embed/8J2rKch35as?si=lS_15UsnDi0URn0Y",
      category: "SR",
    },
    { 
      name: "Le demi-pavillon latéral (ou charnière)",
      iframe: "https://www.youtube.com/embed/ZnuzfLI_eac?si=tQMavRewSHu7qe4X",
      url: "https://www.youtube.com/embed/ZzenJFV_Hqw?si=dZ3b6_lb8tIPpkb2",
      category: "SR",
    },
    { 
      name: "Le pavillon",
      iframe: "https://www.youtube.com/embed/3YvsSsEJjoQ?si=CfxJwPYV0pahnPhS",
      category: "SR",
    },
    { 
      name: "Le demi-pavillon",
      iframe: "https://www.youtube.com/embed/UNj0QyaSJ4A?si=Msvq_KO19SmzDy1S",
      category: "SR",
    },
    { 
      name: "Action sur les pédales",
      iframe: "https://www.youtube.com/embed/2KS1VGHs8Qo?si=hPQb5NVSyfJwxjuJ",
      category: "SR",
    },
    { 
      name: "Ouverture coffre et capot",
      iframe: "https://www.youtube.com/embed/5CjpaXkETCk?si=XBiluJ4XXFyODkW4",
      category: "SR",
    },
    { 
      name: "Reformation d'habitacle",
      iframe: "https://www.youtube.com/embed/AF1nPsip3DI?si=vL8Ujy0IuAjgZz-D",
      category: "SR",
    },
    { 
      name: "Traverse du tableau de bord",
      iframe: "https://www.youtube.com/embed/xL61eO772Es?si=gVQFJf0SLAGe1c23",
      category: "SR",
    },
    { 
      name: "Dépose d'une porte d'un véhucule utilitaire",
      iframe: "https://www.youtube.com/embed/yGaLkCXSWMI?si=4Cq4Lnj7xUWfpPBZ",
      category: "SR",
    },
    { 
      name: "Entretien des outils de désincarcération après utilisation",
      iframe: "https://www.youtube.com/embed/N7tFoW7ktOE?si=Ty5VT8fYTyaqP8C1",
      category: "SR",
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
