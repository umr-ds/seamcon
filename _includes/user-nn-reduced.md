#### *RSSI-only Feature Vector*

```
Training rssi_user1_nn-3...
             precision    recall  f1-score   support

        0.0       0.98      0.97      0.97     25982
        1.0       1.00      1.00      1.00    653387

avg / total       1.00      1.00      1.00    679369

Training rssi_user2_nn-3...
             precision    recall  f1-score   support

        0.0       0.93      0.75      0.83     26192
        1.0       0.98      1.00      0.99    354533

avg / total       0.98      0.98      0.98    380725

Training rssi_user3_nn-3...
             precision    recall  f1-score   support

        0.0       0.97      0.88      0.92    124228
        1.0       0.98      1.00      0.99    764701

avg / total       0.98      0.98      0.98    888929
```

#### *Reduced Feature Vector*
```
Training reduced_user1_nn-3...
             precision    recall  f1-score   support

        0.0       0.92      0.96      0.94     25772
        1.0       1.00      1.00      1.00    439487

avg / total       0.99      0.99      0.99    465259

Training reduced_user2_nn-3...
             precision    recall  f1-score   support

        0.0       0.79      0.73      0.76     23801
        1.0       0.98      0.98      0.98    306163

avg / total       0.97      0.97      0.97    329964

Training reduced_user3_nn-3...
             precision    recall  f1-score   support

        0.0       0.93      0.89      0.91    104565
        1.0       0.98      0.99      0.99    646044

avg / total       0.98      0.98      0.98    750609
```

#### *Full Feature Vector*

```
Training full_user1_nn-3...
             precision    recall  f1-score   support

        0.0       0.91      0.69      0.78     25772
        1.0       0.98      1.00      0.99    439487

avg / total       0.98      0.98      0.98    465259

Training full_user2_nn-3...
             precision    recall  f1-score   support

        0.0       0.72      0.54      0.62     23492
        1.0       0.96      0.98      0.97    302383

avg / total       0.95      0.95      0.95    325875

Training full_user3_nn-3...
             precision    recall  f1-score   support

        0.0       0.68      0.69      0.68    103850
        1.0       0.95      0.95      0.95    638116

avg / total       0.91      0.91      0.91    741966
```