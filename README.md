# E1 : Intégration et Analyse des Données Littéraires

## Description
Ce projet vise à collecter, centraliser, et analyser des données littéraires provenant de trois sources principales : 
- Une **API externe** (Google Books).
- Des **pages Wikipédia** (scraping).
- Une base de données existante pour les **distinctions littéraires**.

Les données collectées sont structurées dans une base de données relationnelle MySQL et exposées via une API REST développée avec **FastAPI**. Ce projet met en œuvre des techniques modernes pour la gestion, la sécurisation et l'analyse des données.

---

## Fonctionnalités principales
- **Extraction de données** :
  - Récupération des livres via Google Books API.
  - Scraping des données biographiques des auteurs depuis Wikipédia.
  - Importation des données de distinctions littéraires existantes.

- **Stockage des données** :
  - Organisation des données dans une base relationnelle MySQL comprenant trois tables :
    - `authors_date_table` : Informations biographiques sur les auteurs.
    - `authors_top5_table` : Informations sur les œuvres principales des auteurs.
    - `authors_awards_table` : Distinctions reçues par les auteurs.

- **API REST** :
  - Endpoint pour obtenir le nombre de livres par catégorie.
  - Endpoint pour récupérer les distinctions reçues par chaque auteur, avec leurs dates de naissance.

- **Sécurisation** :
  - Les informations sensibles comme les clés API et les identifiants de connexion à la base de données sont stockées dans un fichier `.env`.

---

## Technologies utilisées
- **Langage** : Python
- **Framework API** : FastAPI
- **Base de données** : MySQL
- **Scraping** : BeautifulSoup
- **Gestion des dépendances** : `dotenv`, `SQLAlchemy`
- **Interface de gestion MySQL** : DBeaver
- **Versionnement** : Git & GitHub

---

## Installation et configuration

### Prérequis
- Python 3.8 ou plus récent
- MySQL
- Git
- Un éditeur de texte ou un IDE (par exemple VS Code)

### Étapes

1. **Cloner le dépôt** :
   ```bash
   git clone https://github.com/votre-utilisateur/E1_Litterary_Data_Integration.git
   cd E1_Litterary_Data_Integration

2. **Créer un environnement virtuel** :
    python -m venv venv
    source venv/bin/activate   # Sur macOS/Linux
    venv\Scripts\activate      # Sur Windows

3. **Installer les dépendancest** :
    pip install -r requirements.txt

4. **Configurer les variables d'environnement** :
    créer un fichier .env
    DATABASE_URL=mysql+pymysql://<username>:<password>@localhost/<database_name>
    API_KEY=<votre_clé_API_Google_Books>

4. **Lancer l'API** :
    uvicorn main:app --reload

## API Endpoints
    GET / : Message de bienvenue.
    GET /books/categories/ : Retourne le nombre de livres par catégorie.
    GET /authors/awards/ : Retourne les distinctions reçues par les auteurs.