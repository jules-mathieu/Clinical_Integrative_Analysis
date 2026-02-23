# Genomique_Exploration


### Analyse des instabilités génomiques et prédiction de la survie en oncologie

Ce projet explore un jeu de données génomiques et cliniques issu d'une cohorte de 25 000 patients atteints de cancer. DOI : https://doi.org/10.1038/s41586-024-08167-5 

On propose une analyse en trois étapes :
 
- Exploration descriptive et visualisation des données

- Analyse des déterminants du TMB (Tumor Mutational Burden)

- Prédiction de la survie globale par modèles de Machine Learning

L’objectif est de mieux comprendre les relations entre caractéristiques génomiques et cliniques, tout en testant des approches prédictives.


### Partie 1 — Exploration des données

- Analyses :

Étude des proportions et distributions → variables bien équilibrées.

Fraction Genome Altered vs Mutation Count → oppose instabilité mutationnelle vs chromosomique (@smith_mutation_2023).

Courbe de Kaplan-Meier (KM plot) → survie globale des patients, impact de facteurs moléculaires et cliniques (@tang_srplot_2023).


- Résultats :

Relation inverse entre mutation count et fraction of genome altered → deux modes majeurs d’instabilité génomique.

La majorité des tumeurs restent stables (bas gauche du graphe).

Kaplan–Meier : à 60 mois (~5 ans), environ 45 % des patients sont encore en vie.


### Partie 2 — Déterminants du TMB (Tumor Mutational Burden)

- Analyses :

Modèle simple : TMB ~ fraction du génome altéré → significatif mais très faible variance expliquée (R² ≈ 0,0015).

Modèle multiple : ajout des variables cliniques (cancer type, sexe, âge, tabagisme, score MSI) → R² ajusté ≈ 0,34.

Sélection par AIC → l’âge apporte peu d’information supplémentaire.


- Résultats :

Le MSI score est le facteur le plus associé au TMB.

Le type de cancer est également fortement lié.

Conclusion : le TMB est multifactoriel, et ne peut pas être réduit à une seule mesure globale.


### Partie 3 — Prédiction de la survie globale

- Variable cible : survie globale (binaire : vivant/décédé).

- Cancers étudiés : poumon, colorectal, sein, prostate, pancréas.

- Variables explicatives :

Génomiques : TMB, fraction du génome altéré, score MSI

Cliniques : âge, sexe, stade tumoral, pureté tumorale

- Méthode

Trois algorithmes comparés : Régression logistique, Random Forest, KNN

Évaluation par AUC et balanced accuracy.


- Résultats :

Régression logistique et Random Forest ≈ meilleures performances (AUC ~0.70).

KNN moins performant.

Pouvoir prédictif modéré → les variables utilisées apportent une information utile mais insuffisante seules.

Variabilité entre types de cancer → reflète leur diversité biologique et clinique.


### Références 

Jee et al., 2024 — Automated analysis of clinical sequencing data (@jee_automated_2024)

Smith et al., 2023 — Mutation and genome instability (@smith_mutation_2023)

Tang et al., 2023 — SRPlot: survival analysis visualization (@tang_srplot_2023)

Di Mauro et al., 2024 — High-dimensional determinants of TMB (@di_mauro_high_2024)

Nature (2024) — DOI:10.1038/s41586-024-08167-5
