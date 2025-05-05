# Site Web d'Hôtel

Un système de gestion d'hôtel complet avec interface publique pour les réservations et panneau d'administration pour la gestion des chambres, réservations et paramètres.

## 🚀 Fonctionnalités

### Interface Publique
- 🏨 Présentation de l'hôtel et de ses installations
- 🛏️ Affichage des chambres disponibles avec détails (prix, description, images)
- 📅 Système de réservation avec sélection de dates
- 💳 Paiement en ligne intégré
- 👤 Espace utilisateur avec historique des réservations
- 📧 Vérification par email désactivée pour le développement

### Panel d'Administration
- 📊 Dashboard avec statistiques
- 🔧 Gestion des chambres (ajout, modification, suppression)
- 📋 Gestion des réservations
- 🖼️ Gestion des médias (images, carousel)
- ⚙️ Configuration générale du site
- 👥 Gestion des utilisateurs
- 📈 Rapports et statistiques

## 📋 Prérequis

- PHP 7.4+
- MySQL 5.7+
- Serveur web (Apache/Nginx)
- Composer pour les dépendances
- Une clé API SendGrid pour les emails

## 📦 Installation

1. **Clonez le dépôt**
```bash
git clone https://github.com/Groinkb/Portfolio-project-Hotel.git
cd Portfolio-project-Hotel
```

2. **Configurez l'environnement**

Copiez le fichier `.env.example` vers `.env` et configurez vos variables :
```bash
cp .env.example .env
```

Éditez le fichier `.env` avec vos informations :
```env
SENDGRID_API_KEY=votre_clé_api_sendgrid
SENDGRID_EMAIL=votre.email@domaine.com
SENDGRID_NAME=Nom de votre hôtel
```

3. **Configurez la base de données**

Créez une base de données MySQL et importez le schéma :
```sql
CREATE DATABASE hotel_booking;
USE hotel_booking;
SOURCE database/schema.sql;
```

4. **Configurez Apache**

Assurez-vous que votre document root pointe vers le projet :
```apache
DocumentRoot "C:/xampp/htdocs/hbwebsitedisabledemailverification/hbwebsite/"
```

5. **Configuration des URLs**

Modifiez `admin/inc/essentials.php` pour adapter les chemins :
```php
define('SITE_URL', 'http://votre-domaine.com/');
```

## 💻 Utilisation

### Accès à l'interface publique
Visitez `http://localhost:8080/` pour accéder à l'interface utilisateur.

### Accès au panel d'administration
Connectez-vous à `http://localhost:8080/admin/` avec vos identifiants administrateur.

## 🛠️ Technologies Utilisées

- **Frontend** : HTML5, CSS3, JavaScript, Bootstrap 5
- **Backend** : PHP
- **Base de données** : MySQL
- **Services externes** : 
  - SendGrid pour les emails
  - PayTM pour les paiements

## 📁 Structure du Projet

```
/
├── admin/              # Interface d'administration
│   ├── inc/
│   ├── settings/
│   ├── rooms.php
│   ├── bookings.php
│   └── ...
├── inc/               # Fichiers d'inclusion communs
├── images/            # Images uploadées
│   ├── about/
│   ├── carousel/
│   ├── facilities/
│   ├── rooms/
│   └── users/
├── index.php          # Page d'accueil
├── rooms.php          # Page des chambres
├── booking.php        # Page de réservation
└── .env.example       # Configuration exemple
```

## 🔒 Sécurité

- Les informations sensibles sont stockées dans `.env`
- Les mots de passe sont hashés
- Protection contre les injections SQL
- Vérification des types de fichiers uploadés

## 📝 Configuration

### Configuration d'Email
Le projet utilise SendGrid pour l'envoi d'emails. Assurez-vous d'avoir configuré correctement :
- `SENDGRID_API_KEY` : Votre clé API SendGrid
- `SENDGRID_EMAIL` : Email expéditeur
- `SENDGRID_NAME` : Nom de l'expéditeur

### Configuration des Paiements
Le projet est configuré pour utiliser PayTM. Consultez le fichier `inc/paytm/config_paytm.php` pour la configuration.

## 🐛 Dépannage

### Problèmes courants :

1. **Erreur 404** : Vérifiez que le document root est correctement configuré
2. **Erreur de base de données** : Vérifiez les credentials de connexion
3. **Problème d'upload** : Vérifiez les permissions du dossier `images/`
4. **Email non reçu** : Vérifiez la configuration SendGrid

## 👥 Auteurs

- [Groinkb](https://github.com/Groinkb)

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

## 🙏 Remerciements

- Bootstrap pour le framework CSS
- SendGrid pour le service email
- Tous les contributeurs qui ont participé à ce projet

## 📞 Contact

Pour toute question ou suggestion, n'hésitez pas à ouvrir une issue ou à me contacter directement.

---

Fait avec ❤️ pour la gestion hôtelière