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

max_iter(최대 반복횟수)를 4000번으로 늘려 더 정확도를 높이고자 함.

C값이 클수록 overfitting의 위험이 있지만, real test set에 대한 정확도를 확인할 수 없는 상황이므로 practice data set에 대하여 정확도가 높은 방법을 찾고자 C를 5.0으로 늘림.

randon_state를 1로 지정함. 이는 랜덤변수의 시드값을 1로 지정해줌.

class_weight를 balanced로 지정해주어 클래스에 대한 가중치값을 고르게 사용하고자 함.

-> real test set accyracy = 0.7386
