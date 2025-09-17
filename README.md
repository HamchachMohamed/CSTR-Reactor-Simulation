# Simulation CSTR - Processus d'Isomérisation

## Aperçu

Ce dépôt contient une simulation de processus d'un Réacteur Continu Parfaitement Agité (CSTR) pour l'isomérisation du cis-2-pentène en trans-2-pentène. La simulation a été développée en utilisant DWSIM avec le modèle thermodynamique de Peng-Robinson.

## Description du Processus

### Réaction
- **Composant d'alimentation** : Cis-2-pentène
- **Produit** : Trans-2-pentène  
- **Type de réaction** : Isomérisation
- **Conversion** : 90%

### Conditions Opératoires
- **Température** : 25°C
- **Pression** : 10 bar
- **Débit massique** : 7 013,29 kg/h
- **Débit molaire** : 100 kmol/h
- **Débit volumétrique** : 10 751 m³/h

### Spécifications de l'Équipement
- **Type de réacteur** : CSTR-1 (Réacteur Continu Parfaitement Agité)
- **Volume du réacteur** : 6,47358 m³
- **Mode de calcul** : Isotherme
- **Système de contrôle** : Contrôle de température avec surveillance de la conversion

## Résultats de Simulation

### Bilan Matière
- **Composition de l'alimentation** : 100% Cis-2-pentène
- **Composition du produit** : 
  - Cis-2-pentène : 10% (0,1 fraction molaire)
  - Trans-2-pentène : 90% (0,9 fraction molaire)

### Bilan Énergétique
- **Charge thermique** : -114,98 kW (réaction exothermique)
- **Différence de température** : 0°C (fonctionnement isotherme)
- **Temps de séjour** : 0,59524 heures

### Propriétés des Flux
| Propriété | Alimentation | Sortie-Réaction |
|-----------|--------------|-----------------|
| Température | 25°C | 25°C |
| Pression | 10 bar | 10 bar |
| Débit massique | 7 013,29 kg/h | 7 013,29 kg/h |
| Enthalpie spécifique | -385,373 kJ/kg | -382,796 kJ/kg |
| Entropie spécifique | -1,24279 kJ/(kg·K) | -1,19836 kJ/(kg·K) |

## Système de Contrôle

Le système utilise un bloc contrôleur (C-1) qui ajuste dynamiquement le volume du réacteur CSTR-1 pour maintenir précisément une conversion de 90% du cis-2-pentène. Cette approche permet d'optimiser automatiquement les performances du processus en fonction des conditions opératoires.

### Configuration du Contrôleur (C-1)
- **Variable manipulée** : Volume CSTR-1
- **Variable contrôlée** : Conversion du Cis-2-pentène
- **Point de consigne** : 90%
- **Valeur actuelle** : 90%
- **Algorithme de contrôle** : Intégration avec solveur de flowsheet
- **Fonction** : Le bloc contrôleur ajuste automatiquement le volume du réacteur pour maintenir une conversion de 90% du cis-2-pentène
- **Tolérance** : 5E-05 (erreur maximale)

## Modèle Thermodynamique

- **Package de propriétés** : Peng-Robinson (PR)
- **Spécification flash** : Température et Pression (TP)
- **Fraction molaire en phase vapeur** : 0 (réaction en phase liquide)

## Structure des Fichiers

```
├── README.md
├── simulation/
│   ├── flowsheet_processus.pdf
│   ├── proprietes_flux.xlsx
│   └── parametres_controle.txt
├── resultats/
│   ├── bilan_matiere.csv
│   ├── bilan_energie.csv
│   └── analyse_conversion.pdf
└── documentation/
    ├── description_processus.md
    ├── dimensionnement_equipement.md
    └── considerations_securite.md
```

## Fonctionnalités Principales

- ✅ Fonctionnement isotherme du réacteur
- ✅ Système de contrôle avancé avec ajustement automatique du volume
- ✅ Contrôle précis de la conversion à 90%
- ✅ Bilans matière et énergie complets
- ✅ Calculs thermodynamiques rigoureux
- ✅ Atteinte de 90% de conversion
- ✅ Analyse d'intégration thermique

## Utilisation

1. **Prérequis** : DWSIM (logiciel open-source) avec package de propriétés Peng-Robinson
2. **Configuration** : Charger le fichier de simulation DWSIM et vérifier la base de données des composants
3. **Exécution** : Lancer le solveur de flowsheet DWSIM avec tolérance de convergence de 5E-05
4. **Analyse** : Examiner les bilans matière, énergie et performance du contrôle dans l'interface DWSIM

## Métriques de Performance du Processus

- **Efficacité de conversion** : 90%
- **Efficacité énergétique** : Potentiel de récupération de chaleur de 114,98 kW
- **Temps de séjour** : 35,7 minutes
- **Rendement espace-temps** : Productivité élevée grâce au mélange parfait

## Considérations de Sécurité

- Pression de fonctionnement : 10 bar (pression modérée)
- Réaction exothermique nécessite un système de refroidissement
- Protocoles de manipulation d'hydrocarbures requis
- Contrôle de température critique pour la sécurité

## Améliorations Futures

-  Optimisation du réseau d'échangeurs de chaleur
-  Implémentation de contrôle avancé de processus
-  Étude d'optimisation multi-objectifs
-  Intégration d'analyse économique
-  Évaluation de l'impact environnemental

## Contact

Pour toute question concernant cette simulation, veuillez ouvrir une issue ou me contacter.

---

**Dernière mise à jour** : 17 Septembre 2025  
**Logiciel de simulation** : DWSIM (Dynamic Web Simulation)  
**Package thermodynamique** : Équation d'État de Peng-Robinson
