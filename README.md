Descrizione:
Create un nuovo progetto utilizzando Vite e Vue 3 e definite i componenti necessari per strutturare il layout come da screenshot allegato.
Al caricamento della pagina, effettuate una chiama ajax all'API di Yu Gi Oh: https://db.ygoprodeck.com/api/v7/cardinfo.php e con i dati restituiti, stampate una card per ogni carta.

ATTENZIONE:l’api restituisce tutti i risultati in un colpo solo.

Per evitare attese e/o rallentamenti nelle richieste, potete diminuire il numero di risultati sfruttando i parametri num e offset
https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0

Bonus:Creare un componente loader da visualizzare fintantoché i risultati non sono pronti.

Esercizio Yu gi oh 

1) Creiamo il nostro progetto tramite vite in Vue 3 
2) aggiungiamo Sass tramite terminale 
3) creiamoci il nostro scaffolding per lo style con gli elementi in formato .scss (aggiungiamo pure Boostrap tramite npm in caso vogliamo utilizzarlo)
4) Iniziamo a riflettere su quanti components abbiamo bisogno di creare in base al layout richiesto
    - li creiamo e facciamo in modo di gestire come vengono importati prima di scrivere del codice
5) Dopo aver preparato il tutto iniziamo a scrivere la struttura in cui vogliamo immettere i nostri dati
6) Avendo la struttura possiamo scegliere dove fare la chiamata API per ottenere i dati e li gestiamo di conseguenza( tramite props oppure tramite uno store che ci permette di condividere i dati anche quando si tratta di componenti senza una parentela diretta)
