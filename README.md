[README (3).md](https://github.com/user-attachments/files/26359446/README.3.md)
# 🏨 PMS Pédagogique — Logiciel de Réception Hôtelière

> Outil de simulation d'un Property Management System (PMS) hôtelier, conçu pour les classes de Bac Pro MCV, Commerce et filières hôtelières-restauration.

**Auteur :** Yannick Otto — Lycée Victor Hugo, Carpentras  
**Licence :** [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)  
**Version :** v2.2

---

## 🌐 Accès en ligne

| Plateforme | URL |
|---|---|
| GitHub Pages | https://yottoprof.github.io/pms-pedagogique/ |
| Netlify | https://pms-pedagogique-vh.netlify.app/ |

---

## 🔐 Accès sécurisé (Firebase Authentication)

L'accès au PMS est protégé par une authentification Firebase.

### Compte élèves
| Champ | Valeur |
|---|---|
| Email | `eleve@pms-novotel.fr` |
| Mot de passe | `Novotel2024` |

### Compte professeur
| Champ | Valeur |
|---|---|
| Email | `prof@pms-novotel.fr` |
| Mot de passe | *(défini par l'enseignant dans Firebase Console)* |

---

## 👤 Postes disponibles dans le PMS

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

## 👥 Base clients pédagogique (25 clients)

Les clients ont des **profils variés et des besoins exprimés** — l'élève doit analyser les besoins et attribuer la chambre adaptée. Les informations de contact (email, téléphone, ville, pays) sont volontairement vides pour être complétées par l'élève lors du check-in.

| Profil | Exemples de besoins |
|---|---|
| Couple | Vue piscine, king size, anniversaire |
| Famille avec enfants | Lits jumeaux, étage bas, grande capacité |
| Voyageur d'affaires | Calme, Wi-Fi, facture société |
| Client étranger | Non-fumeur, petit-déjeuner, barrière langue |
| VIP Platine | Suite, surclassement, champagne, butler |
| Senior | Étage bas, calme, long séjour |
| PMR | Chambre accessible, douche italienne |
| Couple romantique | Décoration chambre, demande en mariage |
| Famille monoparentale | Budget limité, vue jardin |
| Allergique | Literie hypoallergénique obligatoire |

---

## ✨ Fonctionnalités

### 🏠 Tableau de bord
- KPIs en temps réel (taux d'occupation, chambres libres, arrivées, départs)
- Plan des chambres coloré par statut
- Demandes spéciales signalées en orange

### 📋 Réservations
- Création avec vérification des disponibilités
- Calcul automatique HT / TVA / TTC
- **Acompte obligatoire** (0%, 20%, 30%, 50%, 100%)
- Affichage du solde restant dû sur la facture

### ✅ Check-in professionnel
- **Badge fidélité** (Bronze / Argent / Or / Platine) avec message adapté
- **Fiche de police numérique** obligatoire (Article R.611-42)
- Signature électronique obligatoire

### 💶 Check-out avec facture
- Facture détaillée avec acompte et solde restant
- **Validation du paiement obligatoire** avant libération chambre
- Impression possible

### 🛏 Gestion des chambres
- Plan visuel par statut
- Fiche détaillée par chambre

### 👥 Fichier clients
- 25 clients avec profils et besoins exprimés
- Informations de contact à compléter par l'élève
- Niveau de fidélité et historique des séjours

### 📅 Planning d'occupation
- Calendrier visuel sur 15 jours
- Initiales des clients dans les cases occupées

### 📢 Réclamations clients
- Saisie manuelle par type et niveau d'urgence
- **Réclamations automatiques** toutes les 10 minutes (chambres occupées uniquement)
- Notification rouge visible 15 secondes
- Suivi statut (en cours / résolue)

### 📊 Statistiques *(Manager/Directeur)*
- Revenus mensuels, taux d'occupation, top clients

### ⊟ Clôture du jour *(Manager/Directeur)*
- Rapport journalier complet imprimable

### ⚙ Paramétrage *(Directeur/Professeur)*
- Identité de l'hôtel, personnel, chambres, clients

---

## 🎓 Usage pédagogique

### Compétences travaillées
- Analyser les besoins d'un client et attribuer la chambre adaptée
- Réaliser un check-in professionnel avec fiche de police
- Encaisser un acompte et calculer le solde restant
- Générer et expliquer une facture HT/TVA/TTC
- Gérer une réclamation client en temps réel
- Consulter le planning d'occupation
- Rédiger un rapport de clôture journalière

### Scénario type (1h de cours)
1. Connexion Firebase + choix du poste
2. Consultation du tableau de bord et du planning
3. Analyse des besoins client → attribution de chambre
4. Traitement des arrivées (check-in + fiche de police)
5. Traitement des départs (check-out + facture)
6. Gestion des réclamations automatiques
7. Rapport de clôture *(manager)*

---

## 🏗 Architecture technique

- **Frontend :** React 18 (via CDN, sans build)
- **Authentification :** Firebase Authentication
- **Graphiques :** Chart.js
- **Hébergement :** GitHub Pages + Netlify
- **Stockage :** mémoire locale (session uniquement)

---

## ⚠️ Limitations

- Les données sont réinitialisées à chaque rechargement de page
- Ne pas rafraîchir le navigateur pendant une séance
- Usage pédagogique exclusif — non affilié au groupe Accor

---

## 🗺 Feuille de route

- [ ] Mode examen avec chronomètre et score
- [ ] Module gestion des séminaires
- [ ] Fiche client enrichie avec historique complet

---

## 📄 Licence

© 2026 Yannick Otto — Lycée Victor Hugo, Carpentras  
Outil pédagogique — Usage scolaire exclusif  
[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
