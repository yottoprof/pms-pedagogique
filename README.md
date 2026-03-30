[README (2).md](https://github.com/user-attachments/files/26357876/README.2.md)
# 🏨 PMS Pédagogique — Logiciel de Réception Hôtelière

> Outil de simulation d'un Property Management System (PMS) hôtelier, conçu pour les classes de Bac Pro MCV, Commerce et filières hôtelières-restauration.

**Auteur :** Yannick Otto — Lycée Victor Hugo, Carpentras  
**Licence :** [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)  
**Version :** v2.1

---

## 🌐 Accès en ligne

| Plateforme | URL |
|---|---|
| GitHub Pages | https://yottoprof.github.io/pms-pedagogique/ |
| Netlify | https://pms-pedagogique-vh.netlify.app/ |

---

## 🔐 Accès sécurisé (Firebase Authentication)

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
| Mot de passe | *(défini par l'enseignant dans Firebase Console)* |

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
- Demandes spéciales signalées en orange

### 📋 Réservations
- Création de réservation avec vérification des disponibilités
- Calcul automatique HT / TVA / TTC
- **Acompte obligatoire** à choisir avant confirmation (0%, 20%, 30%, 50%, 100%)
- Affichage du solde restant dû sur la facture
- Filtres par statut

### ✅ Check-in professionnel
- **Badge fidélité** affiché (Bronze / Argent / Or / Platine) avec message personnalisé
- **Fiche de police numérique** obligatoire (Article R.611-42)
- Vérification identité client
- Attribution de la chambre
- Signature électronique obligatoire

### 💶 Check-out avec facture
- Facture détaillée générée automatiquement
- Affichage de l'acompte versé et du solde restant
- **Validation du paiement obligatoire** avant libération de la chambre
- Impression possible

### 🛏 Gestion des chambres
- Plan visuel par statut (libre, occupée, réservée, maintenance)
- Fiche détaillée par chambre
- Changement de statut

### 👥 Fichier clients
- Base clients avec niveau de fidélité
- Historique des séjours

### 📅 Planning d'occupation
- **Calendrier visuel sur 15 jours**
- Initiales des clients dans les cases occupées
- Colonne du jour mise en évidence
- Légende des statuts

### 📢 Réclamations clients
- Saisie par type (propreté, bruit, facturation, équipements...)
- Niveau d'urgence (faible, moyenne, haute)
- Suivi statut (en cours / résolue)
- Persistance pendant toute la session

### 📊 Statistiques *(Manager/Directeur)*
- Revenus mensuels
- Taux d'occupation sur 12 mois
- Top clients par CA
- Répartition par type de chambre

### ⊟ Clôture du jour *(Manager/Directeur)*
- Rapport journalier complet imprimable
- Arrivées et départs traités
- CA encaissé du jour
- État des chambres

### ⚙ Paramétrage *(Directeur/Professeur uniquement)*
- Modification de l'identité de l'hôtel
- Gestion du personnel
- Configuration des chambres
- Base clients de départ

---

## 🎓 Usage pédagogique

### Scénario type (1h de cours)
1. Connexion Firebase + choix du poste
2. Consultation du tableau de bord et du planning
3. Traitement des arrivées (check-in + fiche de police)
4. Traitement des départs (check-out + facture)
5. Gestion d'une réclamation client
6. Rapport de clôture *(manager)*

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
- Ne pas rafraîchir le navigateur pendant une séance de travail
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
