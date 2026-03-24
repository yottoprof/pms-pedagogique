# 🏨 PMS Pédagogique — Logiciel de Réception Hôtelière

> Outil de simulation d'un Property Management System (PMS) hôtelier, conçu pour les classes de Bac Pro Commerce, MCV et filières hôtelières-restauration.

**Auteur :** Yannick Otto — Lycée Victor Hugo, Carpentras  
**Licence :** [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.fr)  
**Version :** 2.0  
**Accès en ligne :** _à compléter après déploiement Netlify_

---

## 📋 Présentation

Ce logiciel simule un vrai PMS hôtelier (Property Management System) tel qu'utilisé en entreprise — sans installation, sans serveur, sans base de données. Il fonctionne comme un **fichier HTML unique** à ouvrir dans n'importe quel navigateur.

Il a été conçu pour permettre aux élèves de **s'exercer aux gestes professionnels de la réception hôtelière** dans un environnement réaliste :

- Prise en charge d'une arrivée (check-in)
- Gestion des départs et facturation (check-out)
- Création et suivi de réservations
- Gestion des demandes spéciales
- Consultation du plan des chambres
- Lecture des statistiques de l'établissement (managers)

---

## ✨ Fonctionnalités

### Interface
- Écran de connexion avec comptes personnalisés (login / mot de passe)
- Horloge en temps réel et météo locale simulée
- Responsive — fonctionne sur PC, tablette, vidéoprojecteur

### Rôles et accès différenciés
| Rôle | Accès |
|---|---|
| **Réceptionniste** | Tableau de bord, Réservations, Chambres, Clients |
| **Manager / Chef de réception** | Tout + onglet Statistiques |
| **Directeur** | Tout + onglet Paramétrage |

### Modules
- **Tableau de bord** — KPIs, arrivées/départs du jour, plan des chambres, panneau demandes spéciales
- **Réservations** — liste complète, filtres, check-in/check-out, facturation, notes
- **Chambres** — plan interactif, fiche détaillée, changement de statut
- **Clients** — fichier clients avec niveaux de fidélité (Bronze / Argent / Or / Platine)
- **Statistiques** — revenus mensuels, taux d'occupation, top clients (accès Manager)
- **Paramétrage** — personnalisation complète sans toucher au code (accès Directeur)

### Facturation
- Calcul automatique HT / TVA / TTC
- Formules pension (SA, PDJ, DP, PC)
- Impression directe depuis le navigateur

---

## 🚀 Utilisation

### Démarrage immédiat
1. Télécharger le fichier `index.html`
2. L'ouvrir dans Chrome, Firefox ou Edge
3. Se connecter avec l'un des comptes préconfigurés

### Comptes par défaut
| Login | Mot de passe | Rôle |
|---|---|---|
| `blanc` | `1234` | Réceptionniste |
| `roux` | `1234` | Réceptionniste |
| `martin` | `9999` | Manager |
| `durand` | `0000` | Directeur |

### Mode Enseignant
Sur l'écran de connexion, cliquer sur **"⚙ Accéder au paramétrage"** (bouton vert) pour personnaliser l'établissement sans identifiant :
- Nom de l'hôtel, adresse, couleur, TVA
- Comptes du personnel (noms des élèves, logins, rôles)
- Plan des chambres (numéros, types, tarifs)
- Base clients de départ

---

## 🎓 Usages pédagogiques suggérés

### Simulation de réception (1 à 2h)
Les élèves se connectent en binôme avec un compte réceptionniste. L'enseignant joue le rôle du client. Les élèves réalisent les opérations : accueil, check-in, gestion d'une demande spéciale, check-out, facturation.

### Jeu de rôle multi-postes
Avec plusieurs postes connectés simultanément (réseau ou partage d'écran), simuler le travail en équipe : un réceptionniste gère les arrivées, un autre les départs, le manager consulte les statistiques.

### Analyse de données (Terminale MCV)
L'enseignant prépare une base de réservations fictives. Les élèves analysent les KPIs, le taux d'occupation, le CA, le top clients — en lien direct avec les compétences Pareto/ABC/RFM.

### Évaluation pratique
Distribuer un scénario écrit (ex : "M. Dupont arrive pour 3 nuits, chambre 201, anniversaire de mariage") — les élèves doivent réaliser toutes les opérations dans le logiciel. L'enseignant évalue la maîtrise des gestes professionnels.

---

## ⚙️ Personnalisation pour un autre établissement

Le bloc `CONFIG` en tête du fichier `index.html` regroupe **toutes les données personnalisables** :

```javascript
const CONFIG = {
  hotel: {
    nom:     "Ibis",                  // Nom de l'hôtel
    ville:   "Avignon",               // Ville
    etoiles: 3,                       // Nombre d'étoiles
    adresse: "12 rue de la Paix…",
    couleur: "#E2001A",               // Couleur principale (hex)
  },
  copyright: {
    auteur:  "Prénom NOM",            // Votre nom
    lycee:   "Lycée Paul Cézanne, Aix",
  },
  meteo: {
    ville: "Avignon",
    temperatures: [7,9,13,16,21,26,29,29,23,17,11,7],
  },
  staff:    [ /* comptes du personnel */ ],
  chambres: [ /* plan de l'hôtel */     ],
  clients:  [ /* base clients départ */ ],
};
```

Ou utiliser directement le **Mode Enseignant** (bouton vert sur l'écran de connexion) pour modifier tout cela via une interface visuelle.

---

## 🛠️ Technique

- **Technologie :** HTML5 / React 18 (CDN) / Chart.js — fichier unique autonome
- **Dépendances :** aucune installation requise (chargées via CDN)
- **Compatibilité :** Chrome 90+, Firefox 88+, Edge 90+, Safari 14+
- **Hébergement :** compatible Netlify Drop, GitHub Pages, tout serveur web statique
- **Données :** non persistantes (reset à chaque ouverture — voulu pour la simulation)

---

## 📁 Structure du dépôt

```
pms-pedagogique/
├── index.html          # Application complète (fichier unique)
├── README.md           # Ce fichier
└── LICENSE             # Licence CC BY-NC-SA 4.0
```

---

## 🤝 Contribuer

Les contributions sont les bienvenues, dans le respect de la licence CC BY-NC-SA :

- **Signaler un bug** → ouvrir une _Issue_ GitHub
- **Proposer une amélioration** → ouvrir une _Pull Request_
- **Adapter pour une autre filière** → forker le dépôt et citer l'auteur original

### Idées d'évolutions possibles
- [ ] Module Événements / Séminaires
- [ ] Gestion du spa / room service
- [ ] Scénarios d'exercice prédéfinis (fichiers JSON)
- [ ] Version avec base de données (Supabase) pour persistance entre sessions
- [ ] Mode évaluation avec grille de compétences automatique
- [ ] Traduction en anglais (DNL / BTS)

---

## 📄 Licence

Ce projet est distribué sous licence **Creative Commons Attribution - Pas d'Utilisation Commerciale - Partage dans les Mêmes Conditions 4.0 International (CC BY-NC-SA 4.0)**.

Vous êtes libre de :
- **Partager** — copier et redistribuer le logiciel
- **Adapter** — modifier, transformer et créer à partir du logiciel

Selon les conditions suivantes :
- **Attribution** — Vous devez créditer Yannick Otto, indiquer si des modifications ont été effectuées
- **Pas d'utilisation commerciale** — Vous n'avez pas le droit d'utiliser ce logiciel à des fins commerciales
- **Partage dans les mêmes conditions** — Si vous modifiez ce logiciel, vous devez distribuer vos contributions sous la même licence

---

## 📬 Contact

**Yannick Otto**  
Enseignant — Commerce / MCV  
Lycée Victor Hugo, Carpentras (84)  
_Via les Issues GitHub pour toute question liée au projet_

---

> *Outil conçu dans une démarche de partage de ressources pédagogiques libres pour l'enseignement professionnel.*
