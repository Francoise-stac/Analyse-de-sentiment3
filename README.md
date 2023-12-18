# Analyse-de-sentiment3
Le but de ce brief est de s'approprier les techniques les plus abouties aujourd'hui autour du "Transfer Learning" dans le domaine de la NLP avec une application en analyse de sentiments.
Le brief précédent a illustré les fondamentaux de la vectorisation de mots (Word Embedding) dans le contexte du traitement du langage naturel et plus particulièrement en l'appliquant à l'analyse de sentiment sur la BDD IMDb. Toutefois, l'impact sur la performance reste assez minime. En effet, avant notamment la publication de l'article "Universal Language Model Fine-Tuning ULMFiT", le pré-entrainement en NLP était limité à l'utilisation de "Word Embeddings". Ce papier a induit le début d'une nouvelle ère : l'utilisation de modèle de langage préentrainés en tant que norme du "Transfer Learning" en NLP. Ainsi, l'idée de ce brief va être de coupler des couches de type "embedding" préentrainées de modèles de langages à un perceptron multicouches et d'effectuer le "fine-tuning" sur la BDD IMDb. Pour cela l'idée va être plus précisément de coupler le modèle de langage "Universal Sentence Encoder" mis à disposition par Google sur le dépôt TensorFlow Hub avec un perceptron multicouche pour effectuer l'analyse de sentiment.

Quelques tips pour vous aider :
Entrainer le modèle sur les données au format textuel fournies par exemple par la librairie "tensorflow_datasets" ;
Préférer le minibatch (pour une fois ;) ) ;
Limiter le nombre d'epoch à 10 ;
Utiliser l'instruction " _os.environ["TFHUB_CACHE_DIR"] = "my_tfhub_cache" _" afin de sauvegarder le modèle en local ; en effet, le modèle de langage a une taille approximative d'environ 1 Go, la sauvegarde en local vous évitera de le télécharger à chaque relance de votre notebook.
