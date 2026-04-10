# Stratégie Patrimoniale — Simulation Maison Familiale

> Document interactif de décision patrimoniale · Usage familial · Avril 2026

---

## À quoi sert ce projet ?

Ce projet est une micro-application web mono-fichier (`index.html`) conçue pour aider une famille à arbitrer une décision patrimoniale concrète : **vendre une maison familiale maintenant, la mettre en location, ou attendre un meilleur prix**.

Il ne s'agit pas d'un outil générique. Il a été construit pour une situation réelle, avec les chiffres réels de la famille, pour permettre à chacun — maman, les frères, Alexandre — de comprendre l'impact de chaque option en quelques minutes, sans expertise financière préalable.

---

## Contexte de la situation

- **Bien** : Maison familiale, ~200 m², Ouest parisien, résidence arborée, construction années 50–60
- **État** : Bien dégradé, travaux cave estimés à ~40 000 €
- **Estimation** : 870 000 €, en vente depuis janvier 2026 (4 mois sans offre ferme)
- **Prix net vendeur réaliste** : ~800 000 € (après commission agence ~5–6%)
- **Propriétaire** : Retraitée, bientôt 70 ans (15 janvier 2027)
- **Enjeu fiscal critique** : Les versements en assurance-vie réalisés **avant** les 70 ans bénéficient d'un abattement successoral de 152 500 € par bénéficiaire. Après 70 ans, seul 30 500 € global s'applique.

---

## Trois scénarios simulés

| Scénario | Revenu net annuel | Charge mentale | Fenêtre AV 70 ans |
|---|---|---|---|
| ✓ Vendre maintenant (~800 k€) | ~26 000 €/an | Minimale | Sécurisée |
| ⚠ Conserver et louer | ~18–22 000 €/an | Forte | À risque |
| ✕ Attendre 850 k€ | 0 € pendant l'attente | Maximum | Très à risque |

**Conclusion du simulateur aux hypothèses par défaut** : vendre maintenant domine les deux autres scénarios. Chaque mois d'attente coûte ~2 000 € de rente non perçue.

---

## Fonctionnalités de l'application

### Verdict dynamique
Un bandeau en haut de page recalcule instantanément la recommandation selon les paramètres choisis. Il change de couleur et de message selon le scénario dominant.

### Simulateur interactif à 6 curseurs
Chaque curseur est accompagné d'une explication en langage simple pour les non-initiés :

| Curseur | Défaut | Ce qu'il représente |
|---|---|---|
| Capital net vendeur | 800 000 € | Ce que maman touche après commission agence |
| Taux de placement | 3,25% | Rendement annuel d'un placement sécurisé (AV fonds euros) |
| Loyer brut mensuel | 2 700 € | Ce qu'un locataire paierait si on garde la maison |
| Part perdue en charges + impôts | 35% | Fiscalité foncière + charges sur les loyers |
| Délai avant une vente à 850 k€ | 24 mois | Combien de temps attendre pour espérer 50 k€ de plus |
| Surcoût fiscal si vente après 70 ans | 40 000 € | Impact en droits supplémentaires pour les héritiers |

### Graphique comparatif
Évolution des revenus cumulés sur 3 ans selon les trois scénarios — mis à jour en temps réel avec les curseurs.

### Bilan consolidé
Tableau synthétique qui présente ce que chaque scénario signifie concrètement pour maman : rente mensuelle, dépendance à Alexandre, travaux, fenêtre assurance-vie.

### 6 arguments rationnels
Section d'argumentation structurée, rédigée en langage accessible, pour étayer la décision et faciliter la discussion en famille.

---

## Structure du projet

```
strategie-patrimoniale/
├── index.html      ← Application complète (mono-fichier)
└── README.md       ← Ce fichier
```

L'application est un fichier HTML unique, sans dépendance externe autre que :
- [Google Fonts](https://fonts.google.com/) — Cormorant Garamond + DM Sans
- [Chart.js 4.4.1](https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js) — graphique comparatif

Aucun framework, aucun build, aucune configuration. Ouvrez `index.html` dans un navigateur — c'est tout.

---

## Déploiement sur GitHub Pages

```bash
# 1. Créer un nouveau dépôt sur GitHub
# 2. Cloner et ajouter les fichiers
git clone https://github.com/votre-compte/strategie-patrimoniale.git
cd strategie-patrimoniale
cp /chemin/vers/strategie-patrimoniale.html index.html
git add .
git commit -m "Initial commit — simulation patrimoniale"
git push origin main

# 3. Activer GitHub Pages dans les Settings du dépôt
# Settings → Pages → Source : Deploy from branch → main → / (root)
```

L'application sera disponible à l'adresse :  
`https://noah-consultant.github.io/maison-saintFrancois/`

---

## Important — avertissement

Ce document est un **outil d'aide à la décision familiale**. Il ne constitue pas un conseil juridique, fiscal ou patrimonial. Les chiffres sont des estimations fondées sur les données partagées en famille et des hypothèses de marché raisonnables.

**Avant toute décision engageant le patrimoine, consultez ensemble un notaire et un conseiller en gestion de patrimoine indépendant.** En particulier pour la validation précise de l'impact fiscal de la date des 70 ans et des stratégies d'assurance-vie.

---

*Document préparé pour usage familial · Maison familiale, Ouest parisien · Avril 2026*
