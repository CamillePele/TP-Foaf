# Master 2 ICONE WEB 3.0 TD-TP

## FOAF — *Friend of a Friend*

**Objectif :** manipulation de données du Web Sémantique avec le cas d’usage FOAF.

### Ressources
- <http://xmlns.com/foaf/spec/>
- <https://orcid.org/>
- <https://github.com/ldspider/ldspider>
- <https://github.com/berezovskyi/ldspider-runner>
- <http://www.infowebmaster.fr/hebergeur_gratuit_sans_pub.php>
- <https://solidproject.org/>
- <https://solidproject.org/apps>

Faire un dépôt avec un compte rendu.

---

## Exercice 1
Créer son fichier `foaf.rdf` et l’associer à sa page « homepage » web (page de présentation).

Déposer sur GitHub (cf. annexe).

*(Cerise sur le gâteau : valider sa homepage par le validateur du W3C : <https://www.w3.org/RDF/Validator/>)*

---

## Exercice 2
Créer un compte sur **ORCID** et utiliser `curl` pour récupérer les éléments de votre compte  
(en particulier avec les éléments FOAF).

---

## Exercice 3
Créer un compte sur <https://solidweb.org/>. Compléter son profil et inclure la description sous forme de triple dans votre rapport.  

On va utiliser une application (il faut être raisonnable dans les volumes de données) pour gérer une liste de films *Media Kraken*.  

Vous allez utiliser votre profil sur solidweb.org pour votre liste. Inclure votre liste sous forme de triple dans votre rapport.

---

## Exercice 4
Utiliser le moteur **ldspider** pour « crawler » vos pages et/ou  
<http://sixhills-consulting.com/foaf/agueritz/foaf.rdf> pour découvrir d’autres personnes FOAF.  

Conserver le résultat du crawling pour la suite.  
(On pourra utiliser **tinyproxy** pour simplifier l’utilisation du web sur les VM en salle réseau MSI.)

---

Université de La Rochelle — 2025/2026  
**Alain BOUJU**

---

## Annexe 1 — Création si nécessaire d’un compte GitHub

```bash
git config --global user.email ...
git config --global user.name ...
````

La politique de sécurité de GitHub a évolué : il faut maintenant un **token** comme mot de passe.
Pour le générer, se connecter sur :
[https://github.com/settings/tokens](https://github.com/settings/tokens)

Dans **Personal access tokens**, utiliser *Generate new token*.
Il faut sélectionner au moins le scope **repo**.

La méthode pour mettre en place des pages est décrite ici :
[https://pages.github.com/](https://pages.github.com/)

---

### Liens utiles

* [http://xmlns.com/foaf/spec/](http://xmlns.com/foaf/spec/)
* [https://orcid.org/](https://orcid.org/)
* [https://github.com/ldspider/ldspider](https://github.com/ldspider/ldspider)
* [https://github.com/berezovskyi/ldspider-runner](https://github.com/berezovskyi/ldspider-runner)
* [http://www.infowebmaster.fr/hebergeur\_gratuit\_sans\_pub.php](http://www.infowebmaster.fr/hebergeur_gratuit_sans_pub.php)
* [https://solidproject.org/](https://solidproject.org/)
* [https://solidproject.org/apps](https://solidproject.org/apps)
* [https://github.com/settings/tokens](https://github.com/settings/tokens)
* [https://pages.github.com/](https://pages.github.com/)