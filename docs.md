# Analisi delle feature

Le feature presenti nel dataset sono le seguenti 33:

| Feature  | Descrizione  |
|:---|:---|
| Id | Id dell'utente |
| name  | Nome dell'utente | 
| screen_name  | Username (alias) dell'utente |
| statuses_count  | Numero di "stati" (post) pubblicati dall'utente |
| followers_count  | Numero di follower | 
| friends_count  | Numero di amici |
| favourites_count  | Numero di profili/pagine segnati come preferiti |
| listed_count  | Numero di elencati | 
| created_at  | Data in cui l'account è stato creato |
| url  | Indirizzo url del profilo |
| lang  | Lingua impostata per il profilo | 
| time_zone  | Fuso orario impostato per il profilo |
| location  | Posizione geografica |
| default_profile  | Se 1 allora il profilo è impostato come default per l'utente | 
| default_profile_image | Se 1 allora l'immagine di profilo è quella di default |
| geo_enabled | Indica lo stato di attivazione della geolocalizzazione |
| profile_image_url | Indirizzo url dell'immagine del profilo | 
| profile_banner_url | Indirizzo url del banner del profilo  |
| profile_use_background_image | Se 1 allora viene usata un'immagine di background |
| profile_background_image_url_https  | Indirizzo url https dell'immagine di background  | 
| profile_text_color  | Colore utilizzato per il testo del profilo  |
| profile_image_url_https | Indirizzo url https dell'immagine del profilo  |
| profile_sidebar_border_color | Colore del bordo della barra laterale  | 
| profile_background_tile | Stato di tassellamento dello sfondo del profilo |
| profile_sidebar_fill_color | Colore del riempimento della barra laterale |
| profile_background_image_url | Indirizzo url https dell'immagine di sfondo  | 
| profile_background_color | Colore dello sfondo |
| profile_link_color  | Colore del link del profilo  |
| utc_offset  | Differenza tra il Coordinate Universal Time e l'orario locale impostato per il profilo | 
| protected  | Indica se il profilo è privato  |
| verified | Indica se il profilo è verificato dall'applicazione  |
| description | Testo della descrizione del profilo | 
| updated | Data di ultimo update |

Si nota subito che molte delle feature presenti non possano in alcun modo aiutare nel distinguere un profilo reale da uno fake. Per esempio potremmo già escludere tutte le feature che riguardano collegamenti url:
- url
- profile_image_url
- profile_banner_url
- profile_background_image_url_https
- profile_image_url_https
- profile_background_image_url

Inoltre, anche le seguenti feature probabilmente non andranno ad influire sulla previsione, data la loro scarsa correlazione concettuale:
- profile_text_color
- profile_sidebar_border_color
- profile_background_tile
- profile_sidebar_fill_color
- profile_background_color
- profile_link_color
- utc_offset
- geo_enabled
- default_profile
- Id
- name
- screen_name
- created_at
- updated
- listed_count

Alcune feature invece sono in "forse" in quanto potrebbero essere utili nel riconoscere un profilo fake, ma è anche vero che nel corso del tempo la creazione di bot sui social network si è evoluta molto, arrivando ad aggiungere molti dettagli che a prima vista potrebbero sembrare superflui ma che invece possono aiutare a mescolarsi meglio tra la moltitudine di profili reali presenti. Le seguenti feature infatti, almeno fino a qualche anno fa, potevano essere utili nel riconoscere un profilo fake, per esempio infatti solitamente i profili bot avevano l'immagine di profilo di default, non avevano un testo di descrizione, erano segnati come account privati e tipicamente appartevenavo a persone fittizie residenti in paesi del sud est asiatico o sudamericani. Sicuramente la fase di feature selection aiuterà per stabilire se possano essere ritenute utili oppure no:
- lang
- time_zone
- location
- default_profile_image
- protected
- description

Le feature che invece sicuramente potranno aiutare sono quelle relative all'attività nei profili all'interno del social network:
- statuses_count
- followers_count
- friends_count
- favourites_count