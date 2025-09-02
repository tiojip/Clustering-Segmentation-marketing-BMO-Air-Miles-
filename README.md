# Clustering-Segmentation-marketing-BMO-Air-Miles-
Mandat appliqué : segmentation des membres **Air Miles** pour **BMO** afin d’améliorer l’engagement, la rétention et la valeur à vie client.

## Problème métier
Comment segmenter efficacement les membres pour adapter offres, communications et campagnes en fonction des comportements d’achat et d’utilisation des points. :contentReference[oaicite:0]{index=0}

## Approche (résumé)
- **Données & nettoyage** : fusion `MEMBERS_DIM`, `TRANSACTION_FACT`, `REWARD_FACT`, gestion des manquants (imputation), conservation des valeurs négatives (annulations/remboursements).  
- **Périmètre** : exclusion des périodes non représentatives (pré-2023), **échantillon 20%** reproductible (seed).  
- **Features clés** : transactions & dépenses, accumulation/rédemption de points, préférences détaillants/récompenses, indicateurs d’engagement (ex. *Loyalty_Score*).  
- **Préparation** : winsorization/transformations log, standardisation robuste, **ACP** → **6 composantes** (~75% de variance).  
- **Clustering hybride** : K-Means (init) → hiérarchique (Ward) pour affiner → K-Means final (**k = 4**). :contentReference[oaicite:1]{index=1}

## Segments (exemples)
- Clients **actifs** avec rédemptions régulières  
- Clients **fidèles** mais dépenses modérées  
- **Accumulateurs passifs** (points peu utilisés)  
- **Occasionnels** / opportunistes  
Variables sociodémographiques (âge, langue, province, préférences de contact) différencient significativement les groupes. :contentReference[oaicite:2]{index=2}

## Recos marketing (extraits)
- Bonus ciblés pour activer les accumulateurs passifs  
- Offres/communication **par segment** (région/langue/canal)  
- Programme dédié **PME** ; gamification & notifications personnalisées. :contentReference[oaicite:3]{index=3}

## Repo
