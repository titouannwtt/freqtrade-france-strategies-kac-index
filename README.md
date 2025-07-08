![image](https://github.com/user-attachments/assets/12539f4b-a241-45d6-b9eb-dbb117a51946)

# KAC-Index Strategies - Freqtrade

[🇫🇷 Version française](#stratégies-kac-index---freqtrade)

## Overview

KAC-Index strategies introduce a revolutionary concept to crypto trading: **TOTAL3 indexation**. Instead of analyzing absolute prices, these strategies evaluate each asset's performance relative to the entire altcoin market (TOTAL3).

### Two Versions Available

- **v1**: Original discovery version with conservative parameters
- **v2**: Optimized version with simplified logic and more trading opportunities

## Key Innovation: TOTAL3 Indexation

Traditional strategies analyze prices in USDT/USDC, which can be misleading when the entire market moves. KAC-Index strategies solve this by:

- Dividing each price by the TOTAL3 market cap (smoothed over 24-28h)
- Calculating indicators on these indexed values
- Detecting assets that outperform or underperform the altcoin market

Example: If an asset rises 10% while TOTAL3 rises 10%, the indexed price remains flat - no signal. But if the asset rises 15% while TOTAL3 rises 5%, that's a strong relative performance signal.

## Technical Setup

### Indicators
- **ATR** (Average True Range): Measures volatility on indexed prices
- **CCI** (Commodity Channel Index): Identifies overbought/oversold conditions

### Requirements
```bash
# Install tvdatafeed dependency
pip install requests websockets
git clone https://github.com/rongardF/tvdatafeed
cd tvdatafeed
pip install .
```

## Performance Highlights

### v1 (Conservative)
- **Timeframe**: 1h
- **Total return**: +972% (2021-2025)
- **Win rate**: 48.2%
- **Max drawdown**: 31.35%
- **Average trade duration**: 8 days

### v2 (Optimized)
- **More trades**: Simplified entry logic (ATR > 2.75 only)
- **Higher Sharpe ratio**: Smoother equity curve
- **Tighter stop loss**: -40% vs -90%

## Quick Start

```bash
# Download data
freqtrade download-data --config config.json --timerange 20210101- --timeframe 1h

# Backtest v1
freqtrade backtesting --strategy kac_index_v1 --config config.json --timerange 20210101- --timeframe 1h --max-open-trades -1

# Backtest v2
freqtrade backtesting --strategy kac_index_v2 --config config.json --timerange 20210101- --timeframe 1h --max-open-trades -1
```

## Learn More

For detailed explanations, optimization guides, and complete setup instructions:

- **[📖 KAC-Index v1 - Original Strategy](https://buymeacoffee.com/freqtrade_france/stratgie-kac-index-utilisation-d-indexation-sur-le-total3-keltner-atr-et-cci)**
- **[📖 KAC-Index v2 - Optimized Version](https://buymeacoffee.com/freqtrade_france/kac-index-v2-stratgie-atr-cci-indexe-total3-optimise)**

---

# Stratégies KAC-Index - Freqtrade

## Présentation

Les stratégies KAC-Index introduisent un concept révolutionnaire dans le trading crypto : **l'indexation sur le TOTAL3**. Au lieu d'analyser les prix absolus, ces stratégies évaluent la performance de chaque actif par rapport à l'ensemble du marché altcoin (TOTAL3).

### Deux versions disponibles

- **v1** : Version découverte originale avec paramètres conservateurs
- **v2** : Version optimisée avec logique simplifiée et plus d'opportunités

## Innovation clé : l'indexation TOTAL3

Les stratégies traditionnelles analysent les prix en USDT/USDC, ce qui peut être trompeur quand tout le marché bouge. Les stratégies KAC-Index résolvent ce problème en :

- Divisant chaque prix par la capitalisation TOTAL3 (lissée sur 24-28h)
- Calculant les indicateurs sur ces valeurs indexées
- Détectant les actifs qui surperforment ou sous-performent le marché altcoin

Exemple : Si un actif monte de 10% alors que le TOTAL3 monte de 10%, le prix indexé reste stable - pas de signal. Mais si l'actif monte de 15% alors que le TOTAL3 monte de 5%, c'est un signal de forte performance relative.

## Configuration technique

### Indicateurs
- **ATR** (Average True Range) : Mesure la volatilité sur les prix indexés
- **CCI** (Commodity Channel Index) : Identifie les conditions de surachat/survente

### Prérequis
```bash
# Installer la dépendance tvdatafeed
pip install requests websockets
git clone https://github.com/rongardF/tvdatafeed
cd tvdatafeed
pip install .
```

## Performances clés

### v1 (Conservative)
- **Timeframe** : 1h
- **Rendement total** : +972% (2021-2025)
- **Taux de réussite** : 48,2%
- **Drawdown max** : 31,35%
- **Durée moyenne** : 8 jours

### v2 (Optimisée)
- **Plus de trades** : Logique d'entrée simplifiée (ATR > 2.75 seulement)
- **Sharpe ratio supérieur** : Courbe de capital plus lisse
- **Stop loss resserré** : -40% contre -90%

## Démarrage rapide

```bash
# Télécharger les données
freqtrade download-data --config config.json --timerange 20210101- --timeframe 1h

# Backtest v1
freqtrade backtesting --strategy kac_index_v1 --config config.json --timerange 20210101- --timeframe 1h --max-open-trades -1

# Backtest v2
freqtrade backtesting --strategy kac_index_v2 --config config.json --timerange 20210101- --timeframe 1h --max-open-trades -1
```

## En savoir plus

Pour des explications détaillées, guides d'optimisation et instructions complètes :

- **[📖 KAC-Index v1 - Stratégie originale](https://buymeacoffee.com/freqtrade_france/stratgie-kac-index-utilisation-d-indexation-sur-le-total3-keltner-atr-et-cci)**
- **[📖 KAC-Index v2 - Version optimisée](https://buymeacoffee.com/freqtrade_france/kac-index-v2-stratgie-atr-cci-indexe-total3-optimise)**

---

## ⚠️ Disclaimer / Avertissement

**EN**: These strategies are provided for educational purposes only. The TOTAL3 indexation concept is experimental. Always test thoroughly with small amounts before scaling up.

**FR**: Ces stratégies sont fournies à des fins éducatives uniquement. Le concept d'indexation TOTAL3 est expérimental. Testez toujours minutieusement avec de petits montants avant d'augmenter.

## 📝 License

These strategies are provided by Freqtrade France. Please respect the usage terms and support the community.

## 🤝 Support

If these strategies help you, consider supporting the development of more innovative strategies:

**[☕ Support Freqtrade France](https://buymeacoffee.com/freqtrade_france)**
