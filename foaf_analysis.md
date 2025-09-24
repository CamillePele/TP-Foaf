# Analyse des données FOAF crawlé par ldspider

## Résumé du crawling

**Commande exécutée :**
```bash
java -jar ldspider-1.3-with-dependencies.jar -s seeds.txt -c 50 -o foaf_crawl_output.nq -accept "application/rdf+xml,text/turtle,application/ld+json" -t 2 -polite 1000
```

**Statistiques :**
- 2 profils FOAF crawlé avec succès
- 84 triples N-Quads générés
- Temps d'exécution : 52 secondes
- 2 threads utilisés

## Profils FOAF découverts

### 1. Camille Pelé (Mon profil)
- **URI** : `https://camillepele.github.io/TP-Foaf/#me`
- **Nom** : Camille Pelé
- **Type** : foaf:Person
- **Comptes** : GitHub, LinkedIn, ORCID
- **Email** : camille.pele@etudiant.univ-lr.fr

### 2. Andy Gueritz (Profil externe)
- **URI** : `http://sixhills-consulting.com/foaf/agueritz/foaf.rdf#me`
- **Nom** : Andy Gueritz
- **Titre** : Mr
- **Type** : foaf:Person
- **Homepage** : http://www.sixhills-consulting.com
- **Weblog** : http://www.sixhills-consulting.com/blog

## Relations découvertes (foaf:knows)

Andy Gueritz connaît 6 personnes :

1. **Tom Ilube**
   - mbox_sha1sum: a8084b745be5ca1d33f89025be2587f8f92d6d52

2. **Nigel Shadbolt**
   - mbox_sha1sum: 2ebb530ea567a0c57314db4ec2027f0ea9f6cfbb

3. **Steve Harris**
   - mbox_sha1sum: 26a374ad4de937252c044f7dd45aa48ecbdb4f16

4. **Mike Harris**
   - mbox_sha1sum: dddbc219d8b6e5cef9855f2af7ae8a0904d0c695

5. **Christian Davis**
   - mbox_sha1sum: 25dbb6085638bbc9203039d934b684a8144b7cd1

6. **Cottie Petrie-Norris**
   - mbox_sha1sum: 2786be6f544ac5ff31341fc8d40ae4932a18979d

## Métadonnées techniques

### Headers HTTP récupérés
- **Camille Pelé** : GitHub.com, application/rdf+xml, 587 bytes
- **Andy Gueritz** : openresty/1.27.1.2, application/rdf+xml, 2317 bytes

### Vocabulaires utilisés
- FOAF (Friend of a Friend)
- Dublin Core
- RDF Schema
- HTTP vocabulary

## Observations

1. **Sécurité** : Les emails sont protégés par des hash SHA1 dans le profil d'Andy Gueritz
2. **Relations** : Le profil d'Andy contient de nombreuses relations professionnelles
3. **Métadonnées** : Les deux profils incluent des métadonnées de génération (generatorAgent)
4. **Format** : Les deux profils utilisent le format RDF/XML
