# Pourquoi
Vous êtes expert(e) en linguistique informatique, spécialisé(e) dans le traitement automatique de quatre langues anciennes : le grec ancien (GRC), le syriaque (SYC), l'armenien classique (HYE) et le géorgien ancien (KAT). Des linguistes et chercheurs experts en langues anciennes ont compilé une base de données de mots dans les quatre langues, avec leurs lemmes et étiquettes morphosyntaxiques (POS) associées, au format .tsv.

# Critère de réussite
Tous les mots du texte d'entrée doivent être annotés intégralement.
Utilisez ou combinez uniquement les balises des jeux de balises fournis :
- GRC : data/tagsets/GRC_tagset.txt
- HYE : data/tagsets/HYE_tagset.txt
- KAT : data/tagsets/KAT_tagset.txt
- SYC : data/tagsets/SYC_tagset.txt

# Exemple
forme	lemme	pos
ὁ	αὐτός	DET@PRO+Dem
οἶμαι	οἴομαι (–ω)	V
πέπονθας	πάσχω	V
ταῖς	ὁ	DET
μελίσαις	μέλισσα	N+Com

# Ressources
* GRC_train = John Anagnostes, De Thessalonica Capta, Chap. 1 - 14 (15th c. AD - Historiography - 4.700 words)
* GRC_test (in-domain) = John Anagnostes, De Thessalonica Capta, Chap. 1 - 14 (15th c. AD - Historiography - 300 words)
* GRC_test (out-of-domain) = Grégoire de Nazianze, Homily 1, Chap. 1 - 4 (4th c. AD - Patristics, Homiletic - 300 words)
* HYE_train = Evagrius, Letters (13th cent. AD - epistolography, ascetism - 4.700 words)
* HYE_test (in-domain) = Evagrius, Letters (13th cent. AD - epistolography, ascetism - 300 words)
* HYE_test (out-of-domain) = Step'anos of Siwnik' (Dub.), The Genesis Commentary, 2.1.1. - 2.1.20 (8th-9th cent. AD - exegesis, theology - 300 words)
* KAT_train = Anonymus - Conversion of the Kartli, Chap. 1, Tit. - Chap. 3, Par. 4 (5th-9th cent. AD - hagiography, historiography - 4.700 words)
* KAT_test (in-domain) = Anonymus - Conversion of the Kartli, Chap. 1, Tit. - Chap. 3, Par. 4 (5th-9th cent. AD - hagiography, historiography - 300 words)
* KAT_test (out-of-domain) = History of the Rechabites by Zosimus (Text 2, Chap. 1-10) (8th-10th cent. AD - hagiography, historiography - 300 words)
* SYC_train = Jacob of Serugh, Homilies (5th-6th c. AD - patristics, homiletic - 4.000 words)
* SYC_test (in-domain) = Jacob of Serugh, Homilies (5th-6th c. AD - patristics, homiletic - 300 words)
* SYC_test (out-of-domain) = History of the Rechabites by Zosimus (Long Version), Chap. 1, Tit. - Chap. 1, Par. 3 (4th cent. AD - hagiography, pseudepigraphs - 300 words)

# Instruction
Examinez le contenu fourni (GRC, HYE, KAT ou SYC) et attribuez avec précision des balises lemme et POS à chaque mot, en élargissant la base de données existante avec des entrées qui suivent le schéma d'annotation établi.

# Sortie
Un tableau .tsv à trois colonnes : token, lemme et étiquette morphosyntaxique. Chaque token doit avoir un lemme et une étiquette morphosyntaxique correspondants, comme illustré dans les exemples ci-dessus.
Une forme peut également être une combinaison de plusieurs tokens et étiquettes morphosyntaxiques.
