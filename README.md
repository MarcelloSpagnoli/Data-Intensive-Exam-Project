# Spotify Track Genre Classification

Progetto per il corso di **Programmazione di Applicazioni Data Intensive**  
Laurea in Ingegneria e Scienze Informatiche — DISI, Università di Bologna (Cesena)

Il notebook realizza un modello di classificazione del genere musicale a partire dalle feature audio estratte dall'API Spotify (energia, danceability, valence, acousticness, ecc.), senza usare metadati come artista o album.

Il dataset utilizzato è [`maharshipandya/spotify-tracks-dataset`](https://huggingface.co/datasets/maharshipandya/spotify-tracks-dataset), che contiene 114.000 tracce distribuite su 114 generi. I sottogeneri vengono raggruppati in 8 macrogeneri (Rock, Metal, Pop, Electronic, Hip-Hop, Jazz, Folk, Classical) per rendere il problema più trattabile.

Dopo un'analisi esplorativa dei dati e una fase di feature engineering, vengono addestrati e confrontati tre modelli: Logistic Regression, Random Forest e LightGBM. La robustezza dell'approccio viene verificata tramite nested cross validation, seguita da una ricerca degli iperparametri con RandomizedSearchCV. I risultati finali vengono valutati con intervalli di confidenza di Wilson e un test statistico sulle proporzioni per verificare che le differenze tra i modelli non siano dovute al caso.
