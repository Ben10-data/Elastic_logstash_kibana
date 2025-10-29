Voici un exemple complet et bien structuré de **README.md** pour ton projet Docker ELK d’archivage de livres 👇

---

# 📚 Books Archiver — Projet ELK sous Docker

## 🧩 Description du projet

Le projet **Books Archiver** est une application Docker qui utilise la **stack ELK (Elasticsearch, Logstash, Kibana)** pour **collecter, indexer et archiver des données de livres**.
Son objectif principal est de **centraliser les données provenant d’un fichier JSON** (`books_data.json`), de les **enregistrer dans Elasticsearch** pour la recherche et la visualisation, tout en **créant une copie d’archive** lisible et bien formatée sur le disque.

---

## ⚙️ Fonctionnement général

Le cœur du projet repose sur **Logstash**, qui lit les données de livres depuis un fichier, applique un **filtrage Ruby** pour reformater le contenu en JSON structuré, puis les envoie vers :

1. **Elasticsearch** → pour l’indexation et la recherche.
2. **Un fichier local d’archivage** → pour la sauvegarde formatée.
3. **stdout** → pour l’affichage en console (debug).

---

## 🧱 Architecture Docker

Le projet repose sur trois principaux services Docker :

* **Elasticsearch** → Stocke et indexe les données.
* **Logstash** → Ingestion, transformation et exportation des données.
* **Kibana** → Visualisation et exploration des livres indexés.



## 🚀 Démarrage du projet



1. **Cloner le dépôt**

   ```bash
   git clone https://github.com/Ben10-data/Books_ELK_Project.git
   cd Books_ELK_Project
   ```

2. **Lancer les services Docker**

   ```bash
   docker-compose up -d
   ```

3. **Vérifier le bon fonctionnement**

   * Elasticsearch → [http://localhost:9200](http://localhost:9200)
   * Kibana → [http://localhost:5601](http://localhost:5601)
   * Logstash → Affiche les événements en console.

---

## 🧾 Résultat attendu

* Les livres du fichier `books_data.json` sont :

  * **Indexés** dans Elasticsearch sous l’index `books`.
  * **Archivés** dans `/archivages/books/books_archivage.json`.
  * **Affichés** dans la console au format lisible.

---

## 📊 Visualisation

Une fois Kibana lancé, tu peux :

1. Créer un **index pattern** `books*`.
2. Visualiser les données des livres sous forme de tableaux ou de graphiques.

---

## 🧑‍💻 Auteur

**Ben10-data**
Projet d’intégration ELK pour la gestion et l’archivage de livres sous Docker.