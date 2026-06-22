# Lancer le projet en local

## 1. Corriger les fichiers manquants
Cette version contient les corrections suivantes :

- ajout de `app/core/Security.php` ;
- ajout de `app/services/NutritionService.php` avec la bonne casse pour Linux ;
- ajout de `app/services/MealGeneratorService.php` avec namespace `App\\Services` ;
- correction de l'import `App\\Core\\Security` dans `AuthMiddleware`.

## 2. Préparer la base de données
Dans phpMyAdmin ou MySQL, importe le fichier :

```sql
database/schema.sql
```

La base créée s'appelle `meal_planner`.

## 3. Vérifier `config/config.php`
Par défaut :

```php
DB_HOST = localhost
DB_NAME = meal_planner
DB_USER = root
DB_PASS = ''
```

Si ton MySQL a un mot de passe, modifie `DB_PASS`.

## 4. Lancer le serveur PHP
Depuis le dossier racine du projet :

```bash
php -S localhost:8080 -t . public/index.php
```

Puis ouvre :

```text
http://localhost:8080
```

## 5. Points à vérifier pour la présentation

- `/` affiche la page d'accueil.
- `/login` affiche la connexion.
- `/register` affiche l'inscription.
- Après import SQL, l'inscription et la connexion doivent fonctionner.

Si tu vois `could not find driver`, ce n'est pas le code : il manque l'extension PHP `pdo_mysql`.
