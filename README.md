# Clustering-Segmentation-marketing-BMO-Air-Miles-
Mandat appliqué : segmentation des membres **Air Miles** pour **BMO** afin d’améliorer l’engagement, la rétention et la valeur à vie client.

## Problème métier
Comment segmenter efficacement les membres pour adapter offres, communications et campagnes en fonction des comportements d’achat et d’utilisation des points. 

## Approche (résumé)
- **Données & nettoyage** : fusion `MEMBERS_DIM`, `TRANSACTION_FACT`, `REWARD_FACT`, gestion des manquants (imputation), conservation des valeurs négatives (annulations/remboursements).  
- **Périmètre** : exclusion des périodes non représentatives (pré-2023), **échantillon 20%** reproductible (seed).  
- **Features clés** : transactions & dépenses, accumulation/rédemption de points, préférences détaillants/récompenses, indicateurs d’engagement (ex. *Loyalty_Score*).  
- **Préparation** : winsorization/transformations log, standardisation robuste, **ACP** → **6 composantes** (~75% de variance).  
- **Clustering hybride** : K-Means (init) → hiérarchique (Ward) pour affiner → K-Means final (**k = 4**). 

## Segments (exemples)
- Clients **actifs** avec rédemptions régulières  
- Clients **fidèles** mais dépenses modérées  
- **Accumulateurs passifs** (points peu utilisés)  
- **Occasionnels** / opportunistes  
Variables sociodémographiques (âge, langue, province, préférences de contact) différencient significativement les groupes.
## Recos marketing (extraits)
- Bonus ciblés pour activer les accumulateurs passifs  
- Offres/communication **par segment** (région/langue/canal)  
- Programme dédié **PME** ; gamification & notifications personnalisées.

## Repo
- `notebooks/Air_Miles_Clustering.ipynb` : analyse & clustering en Python
- `rmd/Nettoyage_Transformation_Airmiles.Rmd` : preprocessing en R
- `reports/Clustering_BMO_AirMiles_Report.pdf` : rapport complet
- `data/datasets` : datasets de BMO-Airmiles

## Reproduire
```bash
pip install -r requirements.txt
jupyter notebook notebooks/Air_Miles_Clustering.ipynb
