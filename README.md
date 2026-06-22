# Analyse et Optimisation de Portefeuille — S&P 500 (2015–2025)

> Analyse quantitative complète des 503 entreprises du S&P 500 sur une décennie : sélection des actifs les plus performants, évaluation multi-dimensionnelle du risque, optimisation de portefeuille par la frontière efficiente de Markowitz et projection Monte Carlo sur 3 ans.

## Aperçu du projet

Ce projet a été conçu pour répondre à une problématique concrète en finance quantitative : parmi les 503 entreprises constituant le S&P 500, lesquelles ont généré la création de valeur la plus significative sur dix ans — et comment construire un portefeuille capable de capturer cette surperformance tout en maîtrisant le risque de manière rationnelle ?

L'analyse s'appuie sur des données récupérées dynamiquement (Wikipedia + yfinance), couvre la période janvier 2015 à janvier 2025, et mobilise un spectre complet d'outils de finance quantitative : statistiques descriptives, métriques de risque avancées, optimisation par simulation Monte Carlo et visualisations interactives Plotly.


## Structure du notebook

Le notebook est organisé en 5 parties logiques, chacune avec ses propres cellules de code, visualisations et interprétations analytiques en prose.

```
Partie I   — Introduction & Contexte
             Problématique, résumé exécutif, note sur le biais de survie

Partie II  — Collecte et exploration des données
             Récupération dynamique Wikipedia + yfinance
             Exploration qualité données (503 entreprises × 8 variables)
             Analyse sectorielle GICS

Partie III — Analyse individuelle des actifs (Top 10)
             Sélection objective par rendement total
             Prix bruts et normalisés (Base 100)
             Distribution des rendements journaliers
             Risk vs Return — Matrice de corrélation

Partie IV  — Métriques de risque et performance ajustée
             Comparaison au benchmark S&P 500
             CAGR — Maximum Drawdown — Ratio de Sharpe
             Bêta (β) — Calmar Ratio
             Rolling Volatility (30j) — Rolling Sharpe (63j)
             Value at Risk (VaR 95%/99%) & CVaR
             Tableau synthèse multi-critères (score composite)

Partie V   — Optimisation de portefeuille & Projection Monte Carlo
             Portefeuille équipondéré — effet de base
             Frontière efficiente de Markowitz (50 000 simulations)
             Composition des portefeuilles Max Sharpe et Min Volatilité
             Simulation Monte Carlo forward (1 000 scénarios, 3 ans)
             Dashboard interactif Plotly (4 métriques en un coup d'œil)
```

<br>

## Top 10 des actifs sélectionnés

| Rang | Symbole | Entreprise | Secteur | CAGR | Sharpe | MDD | Calmar |
|------|---------|-----------|---------|------|--------|-----|--------|
| 1 | **NVDA** | NVIDIA | Information Technology | 75.55% | 1.36 | — | 1.139 |
| 2 | **AMD** | Advanced Micro Devices | Information Technology | 46.40% | 0.90 | — | 0.709 |
| 3 | **TTD** | The Trade Desk | Information Technology | 44.26% | 0.95 | — | 0.689 |
| 4 | **TPL** | Texas Pacific Land | Energy | 41.28% | 0.95 | — | 0.636 |
| 5 | **AVGO** | Broadcom | Information Technology | 40.69% | 1.05 | — | 0.843 |
| 6 | **ANET** | Arista Networks | Information Technology | 39.65% | 0.96 | — | 0.760 |
| 7 | **FICO** | Fair Isaac Corporation | Information Technology | 39.36% | 1.07 | — | 0.773 |
| 8 | **TSLA** | Tesla | Consumer Discretionary | 39.36% | 0.83 | — | 0.534 |
| 9 | **FIX** | Comfort Systems USA | Industrials | 39.05% | 1.00 | — | 0.786 |
| 10 | **AXON** | Axon Enterprise | Industrials | 36.48% | 0.84 | — | 0.622 |

*Tous les actifs surpassent le benchmark S&P 500 (CAGR 11.07%, Sharpe 0.57)*

<br>

## Visualisations produites

- Répartition sectorielle des 503 constituants du S&P 500
- Top 10 — Rendement total et CAGR vs. benchmark
- Évolution des prix (bruts et normalisés base 100)
- Boxplot des rendements journaliers
- Scatter Risk vs Return (coloré par Sharpe)
- Matrice de corrélation des rendements
- CAGR, MDD, Sharpe, Bêta, Calmar — graphiques comparatifs
- Rolling Volatility 30j et Rolling Sharpe 63j (10 sous-graphiques)
- VaR & CVaR — distributions des rendements (10 sous-graphiques)
- Tableau synthèse multi-critères avec score composite
- Frontière efficiente de Markowitz (50 000 points)
- Composition portefeuilles Max Sharpe et Min Volatilité
- Simulation Monte Carlo — 1 000 trajectoires sur 3 ans
- Dashboard interactif Plotly (performance, risk/return, drawdown, synthèse)

## Limites et perspectives

**Limites méthodologiques**

- **Biais de survie** : seules les entreprises *actuellement* dans l'indice sont analysées. Les sociétés sorties (faillites, rachats) ne sont pas incluses, ce qui surestime les performances historiques moyennes.
- **Stationnarité du Monte Carlo** : la simulation suppose que les paramètres 2015–2025 se reproduisent à l'identique. La probabilité de gain à 99.7% est conditionnelle à cette hypothèse — pas une garantie.
- **Coûts non intégrés** : frais de transaction, fiscalité des plus-values et frais de gestion ne sont pas pris en compte dans les calculs de rendement.
- **Sensibilité de Markowitz** : les pondérations optimales sont sensibles aux estimations de rendements espérés et de la matrice de covariance — de petites variations peuvent produire des allocations significativement différentes.

**Extensions possibles**

- Analyse multi-facteurs (value, momentum, quality, low volatility)
- Intégration de contraintes réalistes dans l'optimisation (bornes par actif, contraintes sectorielles)
- Approche risk parity pour la gestion dynamique des pondérations
- Extension de l'univers au-delà du Top 10 pour tester la robustesse
- Backtesting out-of-sample des portefeuilles optimaux

<br>


## Auteure

**Oumaima Cheour**
