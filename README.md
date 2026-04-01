[README (4).md](https://github.com/user-attachments/files/26417542/README.4.md)# 🏨 PMS Pédagogique — Simulateur de réception hôtelière

> Outil pédagogique interactif simulant un Property Management System (PMS) d'hôtel, destiné aux élèves et enseignants en formation hôtelière.

**Auteur :** Yannick Otto  
**Établissement :** Lycée Victor Hugo, Carpentras  
**Version :** v2.0  
**Usage :** Scolaire exclusif — non affilié au groupe Accor

---

## 📋 Présentation

Ce simulateur reproduit fidèlement l'interface et les fonctionnalités d'un vrai logiciel de gestion hôtelière (PMS). Il est entièrement paramétrable par l'enseignant pour s'adapter à n'importe quel établissement fictif ou réel utilisé en formation.

L'application tourne **100 % dans le navigateur**, sans serveur ni base de données : un simple fichier `index.html` suffit.

---

## ✨ Fonctionnalités

### Pour les élèves (rôles Réceptionniste / Manager)

| Module | Description |
|--------|-------------|
| **Tableau de bord** | KPIs en temps réel (taux d'occupation, arrivées, départs, clients en séjour), plan des chambres, demandes spéciales actives |
| **Réservations** | Création, filtrage, annulation, gestion des acomptes, notes de réception |
| **Check-in** | Fiche de police obligatoire (Art. R.611-42), profil fidélité client, attribution de chambre |
| **Check-out** | Génération de facture, encaissement, libération automatique de la chambre |
| **Chambres** | Visualisation des statuts (libre, occupée, réservée, maintenance), fiche détaillée par chambre |
| **Clients** | Base clientèle avec profils, fidélité (Bronze / Argent / Or / Platine), historique de séjours |
| **Planning** | Vue calendrier 15 jours de l'occupation par chambre |
| **Réclamations** | Gestion des réclamations avec niveau d'urgence, génération automatique aléatoire toutes les 10 min |
| **Clôture du jour** | Rapport quotidien imprimable (arrivées, départs, CA, état des chambres) |
| **Statistiques** | Tableaux de bord analytiques (accès Manager / Directeur uniquement) |

### Pour l'enseignant (Mode Paramétrage)

Accessible via un mot de passe dédié, le mode enseignant permet de personnaliser :

- **L'hôtel** : nom, ville, étoiles, adresse, contact, TVA
- **La couleur** de l'interface (adaptable à chaque enseigne : Novotel, Ibis, Mercure…)
- **Le personnel** : comptes de connexion, rôles, postes, horaires
- **Les chambres** : types, tarifs, équipements, statuts initiaux
- **La base clients** : 25 profils pré-remplis avec besoins spécifiques variés

### Mode Examen

Chronomètre intégré avec suivi automatique des tâches validées :
- ✓ Création de réservation
- ✓ Encaissement d'acompte
- ✓ Check-in (fiche de police)
- ✓ Traitement d'une réclamation
- ✓ Check-out et facturation

---

## 👥 Comptes utilisateurs par défaut

| Login | Mot de passe | Rôle | Poste |
|-------|-------------|------|-------|
| `reception1` | `hotel2024` | Réceptionniste | Réceptionniste A (6h–14h) |
| `reception2` | `hotel2024` | Réceptionniste | Réceptionniste B (14h–22h) |
| `concierge` | `hotel2024` | Réceptionniste | Concierge (9h–18h) |
| `commercial` | `hotel2024` | Manager | Commercial Séminaires |
| `manager` | `hotel2024` | Manager | Chef de réception |
| `direction` | `hotel2024` | Directeur | Directeur *(caché)* |

> Le compte `direction` est masqué sur l'écran de connexion. Il est accessible uniquement via le mode enseignant.  
> **Mot de passe enseignant :** `prof2024` *(modifiable dans le code)*

---

## 🏗️ Configuration de l'hôtel par défaut

L'application est pré-configurée avec un hôtel fictif **Novotel Sorgues 4★** à titre d'exemple :

- **27 chambres** réparties sur 3 étages (Standard, Supérieure, Suite Junior, Suite, Suite Prestige, PMR, Communicantes)
- **25 profils clients** variés (couples, familles, PMR, VIP, étrangers, voyageurs d'affaires…)
- **5 réservations initiales** dont 2 séjours en cours
- **Météo locale** basée sur les températures moyennes mensuelles de Sorgues

---

## 🚀 Installation et utilisation

### Utilisation simple

```bash
# Cloner le dépôt
git clone https://github.com/yottoprof/pms-pedagogique.git

# Ouvrir directement dans un navigateur
open index.html
```

Aucune installation, aucune dépendance à installer. Le fichier `index.html` est autonome.

### Librairies utilisées (CDN)

- **React 18** — Interface utilisateur
- **Babel Standalone** — Transpilation JSX côté navigateur
- **Chart.js 4.4** — Graphiques statistiques
- **Firebase Auth** — Authentification (optionnelle / pré-configurée)
- **Google Fonts (Inter)** — Typographie

> ⚠️ Une connexion internet est nécessaire au premier chargement pour récupérer les librairies CDN.

---

## ⚙️ Personnalisation pour l'enseignant

Toute la configuration se trouve dans le bloc `CONFIG` en haut du fichier `index.html`. Il suffit de modifier ce seul bloc, bien délimité par des commentaires :

```javascript
const CONFIG = {
  hotel: {
    nom: "Mon Hôtel",        // Nom affiché dans toute l'interface
    ville: "Ma Ville",
    etoiles: 4,
    // ...
  },
  couleur: "#D4213D",        // Couleur principale (boutons, accents)
  staff: [ /* ... */ ],      // Comptes élèves
  chambres: [ /* ... */ ],   // Plan de l'hôtel
  clients: [ /* ... */ ],    // Base clients
};
```

**Exemples de couleurs par enseigne :**

| Enseigne | Couleur |
|----------|---------|
| Novotel | `#D4213D` |
| Ibis | `#E2001A` |
| Mercure | `#003473` |
| Marriott | `#8B0000` |
| Hilton | `#003580` |

---

## 📐 Architecture technique

```
index.html
├── CONFIG {}              ← Zone enseignant (seul bloc à modifier)
├── Utilitaires            ← Fonctions de calcul, formatage dates/euros
├── Composants React
│   ├── LoginScreen        ← Écran de connexion + mode enseignant
│   ├── App                ← Composant principal, gestion d'état global
│   ├── Dashboard          ← Tableau de bord opérationnel
│   ├── Reservations       ← CRUD réservations
│   ├── Chambres           ← Plan et fiches chambres
│   ├── ClientsTab         ← Base clients
│   ├── Stats              ← Statistiques (Manager+)
│   ├── Planning           ← Calendrier d'occupation
│   ├── Reclamations       ← Gestion des incidents
│   ├── ModeExamen         ← Évaluation chronométrée
│   ├── Parametrage        ← Configuration enseignant
│   └── Modals             ← Fiche police, factures, notes…
└── Styles inline (S.*)    ← Système de design tokens
```

---

## 🎓 Scénarios pédagogiques suggérés

1. **Accueil simple** — Check-in d'un client confirmé, attribution de chambre, remise de clé
2. **Gestion d'un VIP** — Client Platine avec surclassement obligatoire et panier bienvenue
3. **Situation d'urgence** — Réclamation urgente + chambre en maintenance + liste d'attente
4. **Clôture de shift** — Rapport de fin de journée, vérification des encaissements
5. **Examen complet** — Toute la procédure de A à Z, chronométrée, avec score automatique
6. **Client PMR** — Procédure d'accueil adaptée, chambre accessible, besoins spécifiques

---

## 📄 Licence

Usage **scolaire exclusif**. Ce logiciel est un outil pédagogique non commercial.  
Toute utilisation commerciale est interdite.

© 2024–2025 Yannick Otto — Lycée Victor Hugo, Carpentras

