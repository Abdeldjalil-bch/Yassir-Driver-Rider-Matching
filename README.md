# ADC 4.0 — Yassir Driver-Rider Matching
 
Modèle de machine learning qui prédit la probabilité qu'un chauffeur assigné complète un trajet, afin de classer les chauffeurs candidats et optimiser le matching chauffeur-passager pour Yassir.
 
## Structure
 
- **Section A** — EDA (statuts des trajets, corrélations, distributions)
- **Section B** — Feature Engineering (variables agrégées par chauffeur : taux de complétion, note moyenne, expérience ; variables par trajet)
- **Section C** — Modeling (OOP) : classe `ML_model`, split `GroupShuffleSplit` par trajet, comparaison Random Forest / XGBoost / LightGBM, évaluation classification + **MRR** (métrique officielle du challenge)
- **Section D** — Interprétation (feature importance, recommandations)
## Résultats (jeu de validation)
 
| Modèle | Accuracy | F1 (macro) | ROC AUC | MRR |
|---|---|---|---|---|
| LightGBM | 0.853 | 0.716 | 0.833 | **0.834** |
| Random Forest | 0.853 | 0.707 | 0.816 | 0.820 |
| XGBoost | 0.831 | 0.725 | 0.815 | 0.817 |
 
**Variables clés :** expérience du chauffeur (`nb_trajets`), distance habituelle (`distance_moyenne`), fiabilité (`taux_completion`, `note_moyenne`).
 ## Auteur
 
Boucherite Ahmd Abdeldjalil — Master Data Science
