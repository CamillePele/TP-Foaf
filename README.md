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
