> WIP

# Intro

Se una codebase sembra completamente da buttare vanno fatti prima dei piccoli refactor per orientarsi nei refactor reali.
Questi micro-refactor potrebbero anche essere definiti come un semplice "riordinare". In questo post vedremo il metodo che Kent Beck usa nel suo libro: Tidy First? Che non tratteremo nella sua interezza e quindi consigliamo assolutamente!

## Guard Clauses

Cercare di fare delle guardi al posto che inscatolare il codice in mille condizioni, stando comunque sotto alle 8 guardie, se si iniziano a mettere troppe guardie il codice è comunque difficile da digerire sarebbe quindi meglio scomporre quella funzione in più parti.

## Dead Code

Rimuovere sempre il codice che non è più necesario. Non serve neanche tenerlo commentato, tanto è versionato o al massimo verrà riscritto meglio in base a delle evoluzioni future. Il codice non raggiungibile rende solo più criptico il codice e a volte a causa della reflection non è così ovvio da individuare!

## Normalize Symmetries

Scegliere il modo più semplice per ottenere un risultato e convertire tutti gli algoritmi in modo che utilizzino quella maniera precisa per il raggiungimento del risultato, più standard ci auto imponiamo più il codice sarà leggibile senza doverci ragionare su.

## Reading Order & Cohesion Order

Stando attenti alle limitazioni del linguaggio (alcune volte non può essere chiamata una funzione se è definita più sotto ecc).
è molto utile organizzare i files in modo da fornire le informazioni in ordine, dobbiamo immaginare di doverli spiegare ad una persona estranea e rendere la ricerca facile.
è importante anche mettere tutto quello che è accoppiato (se non è immediato e banale disaccoppiarlo) il più vicino possibile alle altre componenti, che siano funzioni dentro lo stesso file, che siano files nella stessa cartella e così via!
Non esiste uno standard scolpito su pietra ma esiste il buon senso.

## Move Declaration and initialization together

Le variabili vanno inizializzate il prima possibile una volta dichiarate, una buona norma spesso è di metterle sempre in cima, ma può essere sensato anche metterle in fasi intermedie, l'importante è metterle dove servono, subito prima che vengano usate e non in punti casuali.

## Explaining Variables & Constants

Se la funzione è troppo elaborata e con espressioni lunghe è un ottima occasione per usare delle variabili parlanti, per semplificare la lettura ed allo stesso tempo aiutare gli altri dev. Lo stesso discorso può essere fatto con i "magic numbers" se hanno un significato preciso interno alla logica creare una costante rende più facili i refactor e ne chiariscono il significato.

## Chunk Statements

Se la funzione o il file sono molto grossi naturalmente sarebbe meno confusionario dividerli in sezioni, è la fix più semplice di tutte ma può dare enormi soddisfazioni per orientarsi, soprattutto nei widget di flutter!

## Explicit Parameters

Se possibile è sempre meglio fare funzioni pure, ovvero che modificano l'esterno solo tramite il loro output, inoltre è sempre meglio fare in modo che i dati in input siano specificati esplicitamente nei parametri. Esempio da non fare: usare le variabili d'ambiente richiamandole dentro il corpo al posto di chiederle come parametri.

## Extract Helper

Crea dei metodi/mixins/files helper per la risoluzione di problemi comuni.
