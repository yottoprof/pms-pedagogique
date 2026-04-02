[README (5).md](https://github.com/user-attachments/files/26444353/README.5.md)
# 🏨 PMS Pédagogique — Novatel Sorgues

> Logiciel de réception hôtelière pédagogique pour lycée professionnel  
> **Bac Pro MCV Option B** — Compétences E33 (PFMP5 et PFMP6)

---

## 🌐 Accès en ligne

| Déploiement | URL |
|---|---|
| **Netlify (principal)** | [pms-pedagogique-vh.netlify.app](https://pms-pedagogique-vh.netlify.app) |
| **GitHub Pages** | [yottoprof.github.io/pms-pedagogique](https://yottoprof.github.io/pms-pedagogique) |

---

## 🎯 Objectif pédagogique

Simuler les opérations d'une réception hôtelière 4★ dans un cadre sécurisé et gamifié.  
Les élèves prennent en main les processus métier réels : réservation, accueil, fidélité, réclamations, facturation.

**Compétences E33 couvertes :**
- Accueillir et identifier les besoins du client
- Réaliser le check-in avec fiche de police (Art. R.611-42)
- Gérer la facturation et les acomptes
- Traiter les réclamations avec réponse écrite
- Réaliser le check-out et encaisser

---

## 🔑 Connexion

### Étape 1 — Authentification Firebase
Un écran sécurisé s'affiche en premier. L'enseignant fournit les identifiants email/mot de passe.

### Étape 2 — Choix du poste PMS

| Login | Mot de passe | Rôle | Accès |
|---|---|---|---|
| `reception1` | `hotel2024` | Réceptionniste | Opérations standard |
| `reception2` | `hotel2024` | Réceptionniste | Opérations standard |
| `concierge` | `hotel2024` | Réceptionniste | Opérations standard |
| `commercial` | `hotel2024` | Manager | + Statistiques, Clôture |
| `manager` | `hotel2024` | Manager | + Statistiques, Clôture |
| `direction` | `hotel2024` | Directeur | Tout + Paramétrage (masqué élèves) |

> Accès Directeur via le bouton **Mode Enseignant** (mot de passe : `prof2024`)

---

## 🛠️ Fonctionnalités

| Onglet | Description |
|---|---|
| ⊞ Tableau de bord | KPIs, arrivées/départs, plan des chambres, demandes spéciales |
| ◷ Réservations | Créer, consulter, annuler · Check-in / Check-out · Factures |
| ⊡ Chambres | Plan visuel, filtres, fiche détaillée |
| ◉ Clients | 25 clients pré-enregistrés · Profils · Besoins · Fidélité |
| 📅 Planning | Calendrier d'occupation 15 jours |
| 📢 Réclamations | Saisie manuelle + automatiques · Traitement avec réponse obligatoire |
| 🎓 Mode Examen | 3 scénarios · 20 min · Score sur 5 points · Rapport imprimable |
| ◈ Statistiques | CA, taux d'occupation, top clients (Manager/Directeur) |
| ⊟ Clôture du jour | Rapport journalier imprimable (Manager/Directeur) |
| ⚙ Paramétrage | Personnalisation complète (Directeur uniquement) |

### Points clés métier
- **Acompte obligatoire** : bouton Confirmer grisé sans sélection de taux (0/20/30/50/100%)
- **Fiche de police** : document légal obligatoire au check-in, avec signature
- **Badge fidélité** : Bronze / Argent / Or / Platine avec protocole adapté
- **Réclamations automatiques** : générées toutes les 10 min sur les séjours en cours
- **Mode Examen** : réclamation du scénario injectée automatiquement au démarrage

---

## 🏨 Données de l'établissement

### Hôtel : Novatel Sorgues — 4★
- TVA hôtellerie : **10%**
- Pensions : SA (0€) · PDJ (+15€/pers) · DP (+45€/pers) · PC (+75€/pers)

### Chambres — 21 au total

| Type | Nb | Étage | Prix/nuit |
|---|---|---|---|
| Standard | 5 | 1 | 85–95 € |
| PMR | 1 | 1 | 89 € |
| Communicante | 4 | 1–2 | 110 € |
| Supérieure | 5 | 2 | 135–149 € |
| Suite Junior | 3 | 3 | 199 € |
| Suite | 2 | 3 | 249 € |
| Suite Prestige | 2 | 3 | 299 € |

### Clients — 25 profils variés
Couple · Famille · Affaires · PMR · Senior · VIP · Romantique · Étranger · Monoparentale  
Niveaux : **Bronze · Argent · Or · Platine**

> Email, téléphone et ville sont intentionnellement vides pour être complétés par les élèves.

---

## 🎓 Mode Examen

**3 scénarios — 20 minutes — 5 points**

| Scénario | Client | Besoins |
|---|---|---|
| 1 — Famille | MOREAU (Argent) | 2 adultes + 2 enfants · lits jumeaux · étage bas · vue jardin · PDJ |
| 2 — Affaires | LAMBERT (Or) | Seul · calme · Wi-Fi fibre · check-in tardif · facture société |
| 3 — Romantique | LOPEZ (Bronze) | Couple · vue piscine · king size · décoration chambre |

**5 tâches dans l'ordre :**
1. Créer une réservation avec chambre adaptée
2. Saisir un acompte
3. Réaliser le check-in (fiche de police complète)
4. Traiter la réclamation générée automatiquement
5. Réaliser le check-out et valider la facture

---

## ⚙️ Paramétrage enseignant

Accessible via **Mode Enseignant** sur l'écran de connexion (mot de passe : `prof2024`).

Permet de modifier :
- Identité de l'hôtel (nom, ville, couleur, étoiles, coordonnées)
- Comptes du personnel (login, mot de passe, rôle, horaire affiché)
- Chambres (type, prix, équipements, statut initial)
- Fichier clients (profils, besoins, niveaux de fidélité)

---

## 🚀 Déploiement

**Fichier unique** — React/Babel CDN — aucun build requis.

```bash
# Modifier index.html puis :
git add index.html
git commit -m "Update PMS v2.2"
git push origin main
# → Netlify et GitHub Pages se mettent à jour automatiquement
```

---

## 🔧 Stack technique

| Technologie | Usage |
|---|---|
| React 18 (CDN) | Interface utilisateur |
| Babel Standalone | Transpilation JSX côté client |
| Firebase Auth | Authentification sécurisée (projet : crm-pedagogique-vh-a454a) |
| Chart.js 4 | Graphiques statistiques |
| CSS inline | Thème sombre complet — 0 dépendance CSS externe |

> 100% navigateur · Aucune installation · Aucun build · Aucun serveur

---

## 📄 Licence

© 2026 **Yannick Otto** — Lycée Victor Hugo, Carpentras  
Usage scolaire et pédagogique exclusif · Non affilié au groupe Accor
