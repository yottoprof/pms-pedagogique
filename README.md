[README (1).md](https://github.com/user-attachments/files/26333668/README.1.md)
# 🏨 PMS Pédagogique — Logiciel de Réception Hôtelière

> Outil de simulation d'un Property Management System (PMS) hôtelier, conçu pour les classes de Bac Pro MCV, Commerce et filières hôtelières-restauration.

**Auteur :** Yannick Otto — Lycée Victor Hugo, Carpentras  
**Licence :** [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)  
**Version :** v2.0

---

## 🌐 Accès en ligne

| Plateforme | URL |
|---|---|
| GitHub Pages | https://yottoprof.github.io/pms-pedagogique/ |
| Netlify | https://pms-pedagogique-vh.netlify.app/ |

---

## 🔐 Accès sécurisé (Firebase)

L'accès au PMS est protégé par une authentification Firebase.  
Les élèves doivent se connecter avec les identifiants fournis par l'enseignant.

### Compte élèves
| Champ | Valeur |
|---|---|
| Email | `eleve@pms-novotel.fr` |
| Mot de passe | `Novotel2024` |

### Compte professeur
| Champ | Valeur |
|---|---|
| Email | `prof@pms-novotel.fr` |
| Mot de passe | *(défini par l'enseignant)* |

---

## 👤 Postes disponibles dans le PMS

Une fois connecté via Firebase, l'élève choisit son poste :

| Login | Poste | Rôle | Shift | Accès |
|---|---|---|---|---|
| `reception1` | Réceptionniste A | Réceptionniste | Matin (6h–14h) | Opérations |
| `reception2` | Réceptionniste B | Réceptionniste | Soir (14h–22h) | Opérations |
| `concierge` | Concierge | Réceptionniste | Journée (9h–18h) | Opérations |
| `commercial` | Commercial Séminaires | Manager | Journée (9h–18h) | Opérations + Statistiques |
| `manager` | Chef de réception | Manager | Journée (9h–18h) | Opérations + Statistiques + Clôture |
| `direction` | Directeur | Directeur | Direction | Accès complet *(réservé prof)* |

**Mot de passe commun :** `hotel2024`

---

## ✨ Fonctionnalités

### 🏠 Tableau de bord
- KPIs en temps réel (taux d'occupation, chambres libres, arrivées, départs)
- Plan des chambres coloré par statut
- Demandes spéciales signalées

### 📋 Réservations
- Création de réservation avec vérification des disponibilités
- Calcul automatique du total HT/TVA/TTC
- Filtres par statut

### ✅ Check-in professionnel
- Fiche de police numérique obligatoire
- Vérification identité client
- Attribution de la chambre
- Signature électronique

### 💶 Check-out avec facture
- Facture détaillée générée automatiquement
- Validation du paiement obligatoire avant libération de la chambre
- Impression possible

### 🛏 Gestion des chambres
- Plan visuel par statut (libre, occupée, réservée, maintenance)
- Fiche détaillée par chambre
- Changement de statut

### 👥 Fichier clients
- Base clients avec niveau de fidélité
- Historique des séjours

### 📊 Statistiques *(Manager/Directeur)*
- Revenus mensuels
- Taux d'occupation sur 12 mois
- Top clients par CA
- Répartition par type de chambre

### ⊟ Clôture du jour *(Manager/Directeur)*
- Rapport journalier complet
- Arrivées et départs traités
- CA encaissé du jour
- État des chambres
- Impression possible

### ⚙ Paramétrage *(Directeur/Professeur uniquement)*
- Modification de l'identité de l'hôtel
- Gestion du personnel
- Configuration des chambres
- Base clients de départ

---

## 🎓 Usage pédagogique

Ce logiciel permet aux élèves de :

- Simuler les opérations d'une réception hôtelière
- Pratiquer les procédures de check-in et check-out
- Remplir une fiche de police numérique
- Générer et expliquer une facture hôtelière
- Analyser les statistiques d'occupation et de revenue
- Rédiger un rapport de clôture journalière

### Scénario type (1h de cours)
1. Connexion Firebase + choix du poste
2. Consultation du tableau de bord
3. Traitement des arrivées (check-in + fiche de police)
4. Traitement des départs (check-out + facture)
5. Rapport de clôture *(manager)*

---

## 🏗 Architecture technique

- **Frontend :** React 18 (via CDN, sans build)
- **Authentification :** Firebase Authentication
- **Graphiques :** Chart.js
- **Hébergement :** GitHub Pages + Netlify
- **Stockage :** localStorage (session uniquement)

---

## ⚠️ Limitations

- Les données sont réinitialisées à chaque rechargement de page
- Le logiciel est conçu pour un usage pédagogique uniquement
- Non affilié au groupe Accor ou à la marque Novotel

---

## 📄 Licence

© 2026 Yannick Otto — Lycée Victor Hugo, Carpentras  
Outil pédagogique — Usage scolaire exclusif  
[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
