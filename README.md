# opensourcefinal

tumor dataset을 학습시켜 가장 높은 정확도로 분석할 수 있는 모델 작성.

Scikit Learn 사용.

tumor dataset을 7:3의 비율로 분리하여 training 및 test 진행.

## (pre-code) 4가지 최적화기법 사용.

  ### perceptron

ppn = sklearn.linear_model.Perceptron(max_iter=4000, eta0=100, random_state=1)

-> Accuracy_ppn: 0.77
    
### logistic regression
log = sklearn.linear_model.LogisticRegression(max_iter=4000, C=5.0, random_state=1, class_weight='balanced')

-> Accuracy_log: 1.00
    
### decision tree classifier
decisiontree_classifier = sklearn.tree.DecisionTreeClassifier()

-> Accuracy_tree: 0.81

### random forest classifier
rfc = ensemble.RandomForestClassifier()

-> Accuracy_rfc: 0.87

## (final-code) logistic regression 기법 사용.

log = sklearn.linear_model.LogisticRegression(max_iter=4000, C=5.0, random_state=1, class_weight='balanced')
log.fit(X,y)
y_pred_log = np.zeros_like(y_test)
y_pred_log = log.predict(X_test)
