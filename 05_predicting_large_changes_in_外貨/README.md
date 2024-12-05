# AVILEN Threshold Analysis Project: Predicting Large Currency Price Changes

## Project Overview
This project focused on determining the optimal threshold for predicting significant changes in foreign currency prices (外貨) by analyzing anomaly scores computed from multiple economic indicators. The analysis aimed to balance precision and recall to provide actionable insights for business stakeholders.

## Task Description
The client needed to identify when large changes in foreign currency prices were likely to occur. Their hypothesis was that aggregated anomaly scores from various economic indicators could predict these significant price movements. My task was to analyze different threshold values for the sum of anomaly scores to determine the most effective threshold for prediction.

## Technical Approach
1. Created binary indicator columns for various thresholds (0.5, 1.0, 1.5, 2.0, 2.5, 3.0) based on the "sum of anomaly" variable
2. Calculated precision, recall, F1 score, and accuracy metrics using the "外貨_diff_big_change_dummy" column as actual values
3. Analyzed performance metrics to determine the optimal threshold balancing precision and recall

## Results 

The analysis yielded the following performance metrics across different thresholds:

| Threshold | Precision | Recall | F1 Score | Accuracy |
|-----------|-----------|---------|-----------|-----------|
| 0.5       | 0.6667    | 0.3784  | 0.4828    | 0.7000    |
| 1.0       | 0.7778    | 0.1892  | 0.3043    | 0.6800    |
| 1.5       | 0.6667    | 0.1081  | 0.1860    | 0.6500    |
| 2.0       | 1.0000    | 0.0541  | 0.1026    | 0.6500    |
| 2.5       | 1.0000    | 0.0270  | 0.0526    | 0.6400    |
| 3.0       | 1.0000    | 0.0270  | 0.0526    | 0.6400    |

Key metrics explained:
- Precision: Proportion of true positive predictions among all positive predictions
- Recall: Proportion of true positive predictions among all actual positive instances
- F1 score: Harmonic mean of precision and recall
- Accuracy: Overall correctness of predictions

## Conclusions

The analysis identified 0.5 as the optimal threshold for predicting large changes in foreign currency prices. This threshold achieved:
- Highest F1 score (0.4828)
- Precision of 0.6667 (66.67% of predicted "big changes" were actual "big changes")
- Recall of 0.3784 (37.84% of actual "big changes" captured)

While higher thresholds (2.0+) achieved perfect precision, their significantly lower recall made them less practical for real-world application. The 0.5 threshold provided the best balance between identifying true price changes while minimizing false positives.

## Impact
The analysis received positive feedback from stakeholders, with the project lead commenting "Wow this output is fantastic!" The results provided actionable insights for predicting currency price changes while accounting for both precision and comprehensiveness of predictions.

## Technical Skills Demonstrated
- Statistical analysis
- Performance metrics calculation
- Threshold optimization
- Business metric development
- Technical documentation
