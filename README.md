# Referat: Bewertung der Feature Importance

Dieses Repository dokumentiert und implementiert verschiedene Machine-Learning-Ansätze zur Analyse der Feature Importance im Datensatz "AI4I 2020 Predictive Maintenance". Ziel des Projekts ist es, zu untersuchen, welche Merkmale am stärksten zur Vorhersage von Maschinenausfällen beitragen, sowie die Eignung der verschiedenen Modelle für den Anwendungsfall zu untersuchen.

## Inhalt des Projekts

- `AI_maschine.ipynb`  
  Neuronales Netz (MLP) für die Klassifikation von Maschinenausfällen.

- `CART_Modell.ipynb`  
  Entscheidungsbaum (CART) mit Hyperparameteroptimierung und Feature-Importance-Analyse.

- `RandomForest.ipynb`  
  Erweiterte Analyse mit Random Forest, inklusive Feature-Importance und Modellbewertung.

- `RandomForestModell.ipynb`  
  Random-Forest-Modell mit verschiedenen Methoden zur Ermittlung der Wichtigkeit von Features (MDI, Permutation Importance, SHAP).

- `ai4i2020.csv`  
  Datensatz für Predictive Maintenance, der die Maschinenzustände und mögliche Ausfälle beschreibt.

- `README.md`  
  Projektbeschreibung und Nutzungshinweise.

## Zielsetzung

Das Projekt untersucht, wie verschiedene Modelle mit einem industriellen Wartungsdatensatz umgehen und welche Variablen für die Vorhersage von Maschinenfehlern am relevantesten sind. Dabei werden unter anderem folgende Fragen betrachtet:

- Welche Features beeinflussen den Ausfall einer Maschine am stärksten?
- Wie unterscheiden sich Entscheidungsbaum, Random Forest und neuronales Netz in ihrer Interpretierbarkeit?
- Welche Modellarchitektur liefert die beste Vorhersageleistung?
- Welche Merkmale sind in der Praxis für die Prognose besonders relevant?

## Datensatz

Der verwendete Datensatz ist das "AI4I 2020 Predictive Maintenance Dataset". Er enthält Informationen zu:

- Lufttemperatur
- Prozesstemperatur
- Drehzahl
- Drehmoment
- Werkzeugverschleiß
- Maschinentyp
- verschiedenen Fehlerkategorien
- Zielvariable: Maschinenfehler (`Machine failure`)

Der Datensatz ist im Projekt als `ai4i2020.csv` enthalten.

## Methoden und Modelle

### 1. CART (Decision Tree)

Ein Entscheidungsbaum dient als leicht interpretierbares Modell. Es ermöglicht eine verständliche Analyse der wichtigsten Merkmale anhand von Splits im Baum.

- Hyperparameteroptimierung mit `GridSearchCV`
- Bewertung mittels Accuracy, Precision, Recall und F1-Score
- Feature Importance mit:
  - Mean Decrease in Impurity (MDI)
  - Permutation Importance

### 2. Random Forest

Random Forest ist ein Ensemble aus mehreren Entscheidungsbäumen und eignet sich besonders gut für robuste Vorhersagen mit hoher Genauigkeit.

- Modelltraining mit mehreren Bäumen
- Evaluation der Klassifikationsleistung
- Vergleich verschiedener Verfahren zur Bestimmung der Feature Importance
- SHAP-Analyse zur erklärbaren KI

### 3. Neuronales Netzwerk (MLP)

Ein Multilayer-Perceptron wird zur Klassifikation von Maschinenausfällen eingesetzt. Hierbei werden zudem Datenvorverarbeitung sowie Klassenungleichgewichte berücksichtigt.

- Standardisierung numerischer Features
- One-Hot-Encoding kategorialer Variablen
- Klassengewichtung zur Verbesserung der Sensitivität auf seltene Ausfälle
- SHAP zur Modellinterpretation

## Feature-Importance-Analyse

Ein zentraler Teil des Projekts ist die Bewertung der Wichtigkeit einzelner Merkmale. Dazu wurden verschiedene Interpretationsmethoden verwendet:

- Mean Decrease in Impurity (MDI)
- Permutation Importance
- SHAP Values

Diese Techniken helfen dabei, die Einflussfaktoren auf Maschinenfehler zu identifizieren und die Modelle nachvollziehbar zu machen.

## Projektstruktur

```text
Referat-BewertungDerFeatureImportance/
├── AI_maschine.ipynb
├── CART_Modell.ipynb
├── RandomForest.ipynb
├── RandomForestModell.ipynb
├── ai4i2020.csv
├── README.md
└── .gitignore
```


Die  durchgeführten Experimente zeigen, dass die Modelle in der Lage sind, Ausfälle mit hoher Genauigkeit zu erkennen. Besonders relevante Features sind typischerweise:

- Drehmoment
- Drehzahl
- Werkzeugverschleiß
- Luft- und Prozesstemperatur

Je nach Modell variieren die exakten Werte leicht, aber die generellen Muster zeigen konsistent, dass technische Betriebsparameter einen starken Einfluss auf Maschinenfehler haben.

## Fazit

Dieses Projekt veranschaulicht, wie Machine Learning und Explainable AI eingesetzt werden können, um maschinelle Ausfälle zu erkennen und die zugrundeliegenden Einflussfaktoren zu verstehen. Die Kombination aus Modellleistung und Feature-Importance-Analyse ist besonders hilfreich für industrielle Anwendungen im Bereich Predictive Maintenance.


Dieses Projekt wurde im Rahmen eines Referats zur Bewertung der Feature Importance entwickelt.

