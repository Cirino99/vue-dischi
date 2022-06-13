# vue-dischi

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## Descrizione esercizio
### prima parte
Create un nuovo progetto utilizzando Vue CLI
e definite i componenti necessari per strutturare il layout come da screenshot allegato.
Al caricamento della pagina, effettuate una chiama ajax all’API di boolean: https://flynn.boolean.careers/exercises/api/array/music
e con i dati restituiti, stampate una card per ogni disco musicale.
- NOTE:
mi raccomando provate ad usare le props
- Bonus:
Creare un componente loader da visualizzare fintantoché i risultati non sono pronti.

### seconda parte
Continuate a lavorare nella stessa repo di ieri e aggiungete una select per filtrare i dischi in base al genere:
quando l’utente seleziona un genere dalla lista, vengono visualizzati solamente i dischi con il genere corrispondente.
- Bonus:
Aggiungere un ulteriore select che filtra gli album per artista
varie altre tipo popolazione select di cui abbiam parlato, se volete provare

### pacchetti installati
- npm install axios
- npm install bootstrap