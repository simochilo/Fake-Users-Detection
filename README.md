# Fake Users Detection
Questa repository è relativa al progetto per il corso di Machine Learning dell'Università degli Studi di Roma Tre a.a. 2021/2022, l'obiettivo del progetto è quello di sviluppare dei modelli di Machine Learning per riconoscere ed identificare profili fake all'interno dei social network.

Progetto a cura di:

| Nome| Matricola | E-mail | Profilo Github | Profilo Linkedin |
|:---|:---|:---|:---|:---|
| Simone Chilosi|522155|sim.chilosi@stud.uniroma3.it|[https://github.com/simochilo](https://github.com/simochilo)| https://www.linkedin.com/in/simone-chilosi-575260239/|


Passo 1: due dataset di utenti facebook, aggiunta una colonna in entrambi i csv 'isFake', 1 per tutte le righe del dataset fake_users, 0 per tutte quelle del dataset users

Passo 2: uniti i due file csv in un unico dataset mediante il comando "cat fake_users.csv <(tail +2 users.csv) > dataset.csv"

Passo 3: mescolati i dati nel nuovo dataset completo utilizzando la funzione shuf della libreria sh di python
