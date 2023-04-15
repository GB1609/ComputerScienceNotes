**Tag Obsidian:** #gcp #cloud #ml #machinelearning

Questa pagina contiene note fondamentali sul machine learning e come alcuni concetti e casi d'uso vengono applicati in ambiente Google Cloud Platform.
1. Una rete neurale si addestra (**ALLENA**) tramite il corretto settaggio di **WEIGHTS** & **BIASES**
2. Per poc o analisi di ML su testi si usa **CLOUD NATURAL LANGUAGE API.**
3. Per poc o analisi di ML su Immagini si usa **CLOUD VISION API**
4. Per poc o analisi di ML sui video si può usare **VIDEO AI**
5. Per analizzare i video si può usare **CLOUD VIDEO INTELLIGENCE**
6. Per convertire Audio a testo si sua **CLOUD SPEECH-TO-TEXT API**
	1. SINCRONO -> audio < 1 min
	2. ASINCRONO -> audio > 1 min
7. BigQuery ML supporta:
	1. **Linear Regression**
	2. **Binary Logistic**
	3. **Multiclass Logistic**
8. Per analisi semplici e di cui si richiede una risposta veloce si può usare **Online Predictions**
9. Per Predizioni semplici si può usare **Linear Regression**
10. **Reinforcement Learning** viene utilizzato per disegnare modelli basati sul **REWARD**
11. Tecniche di Machine Learning:
	1. **Classification** → Bisogna assegnare un classe (1 ad N)
	2. **Regression** → Bisogna predire valori numerici
	3. **Clustering** → Bisogna raggruppare
	4. **Association** → Inferire associazioni attraverso dei pattern
	5. **StructuredOutput** → Creare output complessi (Image Recognition, NP problem,…)
	6. **Ranking** → Identificare una posizione all’interno di una scala
12. Tecniche **SUPERVISED**:
	1. Classification
	2. Regression
13. Tecniche UNSUPERVISED:
	1. Clustering
	2. Association
	3. Dimensionality Reduction
14. Tecniche di Evaluation:
	1. **Dropout Regularization** → Quando vanno rimosse selezioni random da un livello di rete neurale
	2. **Precision** → Per verificare quando è accurato un modello se la maggior parte dell’output è positivo
	3. Recall → Per verificare quando è accurato un modello se la maggior parte dell’output è negativo
	4. Gradient Descent → Per trovare il minimo in una funzione
15. Per **hyperparameter** tuning si intendono numero dei nodi e di hidden layers
16. Per eseguire **modelli già pronti** si usa Google Machine Learning Engine
17. **Google ML Deep Learning** permette di avere VM preconfigurate per applicazioni di Deep Learning
18. Per **Tensorflow** è indicato utilizzare **TPU**
19. Per adattarsi all’incremento della complessità bisogna utilizzare **Neurons** e **Hidden Layer**
20. Si utilizzano **Wide** model per **memorizzare** mentre **deep** per **generalizzare**
21. TensorFlow è supportato da Google Cloud Machine Learning
22. In TesorFlow se si conoscono i valori di una colonna categorica si usa **categorical_columns_with_vocabulary_list**, se invece non si conoscono si usa categorical_with_hash_bucket
23. È possibile lanciare job di Cloud Machine Learning anche localmente
24. Uno **sparse vector** è un array con tutti 0 e solamente un 1 [0 0 0 0 1 0]
25. La **Bucketizzation** e la **crossed feature** sono **Feature Engineering**
26. Quando **AutoML** overfitta bisogna prendere le immagini da più angoli
27. Se c’è **underfitting** bisogna migliorare il modello, con **overfitting** bisogna migliorare la fase di
training
---
