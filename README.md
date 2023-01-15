# Task
Есть данные о том, кто из клиентов именно тот, кто без СМС не купит, а с СМС - купит!

Вам предстоит из всех test-клиентов указать вероятность того, что клиент купит только при коммуникации (не купит без нее)


Оценка модели будет делаться по метрике Gini:

Gini = 2 * AUC - 1 где AUC - это ROC AUC.

Для построения модели, участникам предоставляется обучающий набор клиентов train.csv с информацией о наличии коммуникации (treatment_flg) и совершение покупки (purchased).

Необходимо для каждого клиента из тестовой выборки test.csv предсказать target, который равен 1 если после коммуникации покупка совершена и если без коммуникации покупка не совершена, 0 в других случаях.

Результат должен быть представлен в виде CSV-файла с колонками client_id и pred:

client_id,pred
008fb49e3a,0.1149912020897228
0095340acc,0.8353208872466903
015c0b4d79,0.3085840952650095
...
ff70c360ad,0.0809048695228205
ff86a1311b,0.4815832858531034
ffcccc2cc4,0.10523347182011245


# Решение
По заданию нужно были решить классическую задачу uplift скоринга. Для решения задачи был применён метод Class Transformation, заключающийся в преобразовании таргета в новую величину Z.

Private score: 0.05903
Public score: 0.04166
