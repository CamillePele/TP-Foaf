# TP FOAF - Camille Pelé

## Exercice 1 — Création du profil FOAF

### Contexte & objectifs (Ex. 1)

L'objectif de cet exercice est de créer un profil FOAF (Friend of a Friend) en RDF/XML et de l'associer à une page homepage web. Le profil FOAF permet de décrire de manière structurée mon identité numérique, mes comptes en ligne et mes relations, dans le respect des standards du Web Sémantique.

### Choix techniques

**Format RDF/XML :** J'ai choisi le format RDF/XML pour le fichier `foaf.rdf` car c'est le format standard recommandé par la spécification FOAF et il offre une excellente compatibilité avec les outils de validation et les parseurs RDF.

**Liaison homepage-FOAF :** J'utilise la balise `<link rel="meta" type="application/rdf+xml" href="foaf.rdf" title="FOAF" />` dans le `<head>` de `index.html` pour établir la relation sémantique entre ma homepage et mon profil FOAF.

**Structure GitHub Pages :** J'ai configuré les chemins pour fonctionner avec GitHub Pages en mode "project pages" (username.github.io/nom-du-repo), ce qui permet une flexibilité maximale pour l'organisation des dépôts.

### Étapes réalisées — journal de bord

#### a. Initialisation du dépôt et arborescence
- Création du fichier `.gitignore` avec les exclusions standards (Node.js, IDE, OS)
- Mise en place de la structure minimale : `index.html`, `foaf.rdf`, `README.md`

#### b. Génération du modèle FOAF avec mes données
J'ai créé le fichier `foaf.rdf` en incluant les éléments suivants :

**Données personnelles :**
- `foaf:name` : "Camille Pelé"
- `foaf:givenName` : "Camille" 
- `foaf:familyName` : "Pelé"
- `foaf:mbox` : "mailto:camille.pele@etudiant.univ-lr.fr"

**Identité numérique :**
- `foaf:homepage` : "https://github.com/CamillePele"
- `foaf:img` : "https://avatars.githubusercontent.com/u/52352789"

**Comptes en ligne (foaf:account) :**
- GitHub : CamillePele
- LinkedIn : camille-pelé-818822214  
- ORCID : 0009-0001-8056-7503

**Structure RDF :**
- `foaf:PersonalProfileDocument` avec `foaf:maker` et `foaf:primaryTopic` pointant vers `#me`
- `foaf:Person` avec l'identifiant `#me` contenant toutes les propriétés

#### c. Ajout du lien FOAF dans index.html
- Création d'une homepage minimale mais sémantique
- Intégration de la balise `<link>` pour la liaison FOAF
- Ajout d'un lien visible "Voir mon profil FOAF" vers `foaf.rdf`
- Stylisation CSS basique pour une présentation claire
- Encodage UTF-8 pour la compatibilité des caractères spéciaux

#### d. Test local de validité RDF
- Vérification de la syntaxe XML (balises fermées, attributs corrects)
- Validation de la structure RDF (namespaces, propriétés FOAF)
- Test de l'encodage UTF-8

#### e. Préparation à la publication GitHub Pages
Pour publier sur GitHub Pages, je devrai :
1. Pousser le code sur GitHub dans un dépôt public
2. Aller dans Settings → Pages
3. Sélectionner "Deploy from a branch" → "main"
4. Le site sera accessible à l'URL : `https://camillepele.github.io/TP-Foaf/`

### Vérifications

**Validation W3C RDF :** Une fois le site déployé, je validerai le fichier FOAF avec le validateur W3C à l'adresse : https://www.w3.org/RDF/Validator/

**Checks à effectuer :**
- [ ] Fichier `foaf.rdf` accessible publiquement
- [ ] Content-Type correct (`application/rdf+xml`)
- [ ] Résolution correcte de l'URI `#me`
- [ ] Validation W3C sans erreurs
- [ ] Lien homepage → FOAF fonctionnel

### Problèmes & contournements

**Aucun problème majeur rencontré.** La structure FOAF est standard et les données fournies étaient complètes.

**Note :** Les contacts `foaf:knows` seront ajoutés plus tard selon les instructions de l'utilisateur.

### Prochaines étapes

Pour l'Exercice 2, je devrai :
1. Créer un compte ORCID (déjà existant : 0009-0001-8056-7503)
2. Utiliser `curl` pour récupérer les données de mon profil ORCID
3. Analyser les éléments FOAF présents dans la réponse
4. Documenter les résultats dans le compte-rendu

---

**Fichiers créés :**
- `foaf.rdf` : Profil FOAF en RDF/XML
- `index.html` : Homepage avec liaison FOAF
- `.gitignore` : Exclusions Git
- `README.md` : Ce compte-rendu

**URLs de référence :**
- Homepage : https://camillepele.github.io/TP-Foaf/
- Profil FOAF : https://camillepele.github.io/TP-Foaf/foaf.rdf

---

## Exercice 2 — ORCID et curl

### Contexte & objectifs (Ex. 2)

L'objectif de cet exercice est d'utiliser `curl` pour récupérer les données de mon profil ORCID et d'analyser les éléments FOAF présents dans la réponse. ORCID fournit des données structurées en RDF/XML qui peuvent être intégrées dans un profil FOAF.

### Choix techniques

**Commande curl :** J'ai utilisé `Invoke-WebRequest` (équivalent PowerShell de curl) avec l'en-tête `Accept: application/rdf+xml` pour récupérer les données ORCID au format RDF.

**Formats récupérés :** 
- RDF/XML : `https://orcid.org/0009-0001-8056-7503` (format FOAF)
- JSON : `https://pub.orcid.org/v3.0/0009-0001-8056-7503` (API complète)

### Étapes réalisées — journal de bord

#### a. Récupération des données ORCID
```powershell
# Récupération en RDF/XML
Invoke-WebRequest -Uri "https://orcid.org/0009-0001-8056-7503" -Headers @{"Accept"="application/rdf+xml"} -OutFile "orcid_profile.rdf"

# Récupération en JSON (API complète)
Invoke-WebRequest -Uri "https://pub.orcid.org/v3.0/0009-0001-8056-7503" -Headers @{"Accept"="application/json"} -OutFile "orcid_profile.json"
```

#### b. Analyse des éléments FOAF dans la réponse RDF

**Structure FOAF identifiée :**

1. **foaf:PersonalProfileDocument** (ligne 10)
   - URI : `https://pub.orcid.org/orcid-pub-web/experimental_rdf_v1/0009-0001-8056-7503`
   - `foaf:maker` et `foaf:primaryTopic` pointent vers l'URI ORCID

2. **foaf:Person** (lignes 19-34)
   - URI : `https://orcid.org/0009-0001-8056-7503`
   - `foaf:familyName` : "Pelé"
   - `foaf:givenName` : "Camille"
   - `rdfs:label` : "Camille Pelé"
   - `rdf:type` : `http://xmlns.com/foaf/0.1/Person`

3. **foaf:OnlineAccount** (lignes 21-26)
   - `foaf:accountName` : "0009-0001-8056-7503"
   - `foaf:accountServiceHomepage` : "https://orcid.org"

4. **foaf:publications** (lignes 27-29)
   - Référence vers un workspace de publications

#### c. Données supplémentaires du JSON

**Informations personnelles :**
- Nom : "Camille Pelé" (given-names: "Camille", family-name: "Pelé")
- Profil créé le : 24 septembre 2025
- Email vérifié : false
- Profil revendiqué : true

**Affiliation actuelle :**
- Organisation : "Université de La Rochelle"
- Département : "Master Informatique"
- Début : septembre 2024
- Ville : "La Rochelle", Région : "Nouvelle-Aquitaine", Pays : "FR"
- Identifiant ROR : "https://ror.org/04mv1z119"

### Vérifications

**Données récupérées avec succès :**
- ✅ Fichier RDF/XML : `orcid_profile.rdf` (40 lignes)
- ✅ Fichier JSON : `orcid_profile.json` (203 lignes)
- ✅ Structure FOAF valide dans le RDF
- ✅ Données personnelles cohérentes avec mon profil

**Éléments FOAF identifiés :**
- ✅ foaf:PersonalProfileDocument
- ✅ foaf:Person avec nom complet
- ✅ foaf:OnlineAccount pour ORCID
- ✅ foaf:publications (workspace)
- ✅ Métadonnées de provenance (pav:, prov:)

### Problèmes & contournements

**Aucun problème majeur.** La récupération s'est faite sans erreur. Les données ORCID sont bien structurées et compatibles FOAF.

**Note :** Le profil ORCID est récent (créé en septembre 2025) et ne contient pas encore de publications ou d'autres activités académiques.

### Prochaines étapes

Pour l'Exercice 3, je devrai :
1. Créer un compte sur solidweb.org
2. Compléter mon profil Solid
3. Utiliser une application pour gérer une liste de films
4. Inclure les données sous forme de triples dans le rapport

---

**Fichiers créés :**
- `orcid_profile.rdf` : Données ORCID en RDF/XML
- `orcid_profile.json` : Données ORCID en JSON (API complète)

**URLs de référence :**
- Profil ORCID : https://orcid.org/0009-0001-8056-7503
- API ORCID : https://pub.orcid.org/v3.0/0009-0001-8056-7503
