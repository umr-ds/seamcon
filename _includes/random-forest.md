## Random Forest

### RSSI only
```
10 Trees
             precision    recall  f1-score   support
       loss       0.90      0.97      0.93     49260
    no loss       1.00      0.99      0.99    457966
avg / total       0.99      0.99      0.99    507226
    
20 Trees
             precision    recall  f1-score   support
       loss       0.91      0.97      0.94     49260
    no loss       1.00      0.99      0.99    457966
avg / total       0.99      0.99      0.99    507226
    
25 Trees
             precision    recall  f1-score   support
       loss       0.92      0.97      0.94     49260
    no loss       1.00      0.99      0.99    457966
avg / total       0.99      0.99      0.99    507226
```

### Reduced Feature Vector
```
10 Trees
             precision    recall  f1-score   support
       loss       0.88      0.98      0.93     42334
    no loss       1.00      0.98      0.99    345799
avg / total       0.98      0.98      0.98    388133
    
20 Trees
             precision    recall  f1-score   support
       loss       0.90      0.98      0.94     42334
    no loss       1.00      0.99      0.99    345799
avg / total       0.99      0.99      0.99    388133
    
25 Trees
             precision    recall  f1-score   support
       loss       0.92      0.98      0.95     42334
    no loss       1.00      0.99      0.99    345799
avg / total       0.99      0.99      0.99    388133
```

### Full Feature Vector
```
10 Trees
             precision    recall  f1-score   support
       loss       0.89      0.99      0.94     42107
    no loss       1.00      0.98      0.99    343073
avg / total       0.99      0.99      0.99    385180
    
20 Trees
             precision    recall  f1-score   support
       loss       0.91      0.99      0.95     42107
    no loss       1.00      0.99      0.99    343073
avg / total       0.99      0.99      0.99    385180
    
25 Trees
             precision    recall  f1-score   support
       loss       0.92      0.99      0.96     42107
    no loss       1.00      0.99      0.99    343073
avg / total       0.99      0.99      0.99    385180
```