# 📒 Mon carnet de bord

**Nom :** PARMENTIER   

**Prénom :** Victoria

**Adresse de mon site :** https://1toriisauvage.pythonanywhere.com/
> Modifiez ce fichier directement sur GitHub (icône crayon ✏️) pour répondre aux questions de chaque exercice.
> Écrivez avec vos propres mots : une réponse courte et juste vaut mieux qu'un long copier-coller ! 🙂

---

## 🟢 Exercice 1 — Mon premier déploiement

1. Où se trouve physiquement le code qui fabrique votre page : sur votre ordinateur, sur GitHub ou sur PythonAnywhere ?

   > _Ma réponse :_ Physiquement, le code se trouve sur PythonAnywhere. GitHub en stock juste une copie.

2. Pourquoi votre voisin(e) peut-il voir votre site, alors que vous n'avez rien installé sur son ordinateur ?

   > _Ma réponse :_ Parce que le site est stocké sur PythonAnywhere, donc en ligne, et il suffit d'avoir l'url pour accéder au site.

---

## 🟢 Exercice 2 — Les URL et les routes

1. Dans l'URL `https://www.google.com/maps`, quel est le nom de domaine ? Quel est le chemin ?

   > _Ma réponse :_ Domaine : www.google.com. Chemin : /maps

2. Que veut dire le message *Not Found* ? Qui l'a envoyé : votre navigateur ou le serveur ?

   > _Ma réponse :_ Erreur 404 : la page demandée n’existe pas. C’est le serveur qui l’envoie

3. Que se passe-t-il si deux fonctions portent le même nom dans `flask_app.py` ? (Indice : essayez, puis lisez l'Error log.)

   > _Ma réponse :_ L’application plante (AssertionError dans l’Error log), car Flask exige un nom unique pour chaque fonction de route

---

## 🔵 Exercice 3 — Le langage HTML

1. Quelle est la différence entre ce que le serveur **envoie** et ce que le navigateur **affiche** ?

   > _Ma réponse :_ Le serveur envoie du code HTML (du texte avec des balises). Le navigateur lit ce code et l’affiche mis en forme (titres en gros, listes à puces…).

2. À quoi servent les balises `<h1>`, `<p>`, `<ul>` et `<li>` ?

   > _Ma réponse :_ <h1> : un titre principal. <p> : un paragraphe. <ul> : une liste à puces. <li> : un élément de la liste.

3. Pourquoi l'image s'affiche-t-elle alors qu'elle n'est pas sur votre serveur ?

   > _Ma réponse :_ La balise <img> contient l’adresse d’une image hébergée sur un autre serveur. Le navigateur va la chercher directement là-bas.

---

## 🔵 Exercice 4 — Les templates

1. Pourquoi est-ce une bonne idée de séparer le code Python et le HTML ? (Pensez à une équipe avec un développeur et un graphiste.)

   > _Ma réponse :_ Chacun travaille sur son fichier sans gêner l’autre : le développeur s’occupe du Python, le graphiste du HTML. Le code est aussi plus clair et plus facile à modifier.

2. Les `{{ prenom }}` sont-ils remplacés par le serveur ou par le navigateur ? Comment l'avez-vous vérifié ?

   > _Ma réponse :_ Par le serveur (Flask). On le vérifie avec « Afficher le code source » dans le navigateur : on y voit directement le prénom, et non {{ prenom }}.

---

## 🔵 Exercice 5 — Le CSS et les liens

1. Quelle est la différence de rôle entre le HTML et le CSS ?

   > _Ma réponse :_ Le HTML définit le contenu et la structure (titres, paragraphes…). Le CSS définit l’apparence (couleurs, polices, tailles…).

2. Pour afficher votre page `/presentation`, combien de fichiers le navigateur doit-il télécharger ? (Vous pourrez le vérifier à l'exercice suivant !)

   > _Ma réponse :_ Au moins 2 : la page HTML et le fichier CSS. S’il y a une image, ça fait 3.

3. Pourquoi faut-il parfois faire **Ctrl + F5** pour voir les changements de CSS ?

   > _Ma réponse :_ Le navigateur garde l’ancien fichier CSS en mémoire (le cache). Ctrl + F5 l’oblige à retélécharger la nouvelle version

---

## 🟣 Exercice 6 — Espionner le navigateur

1. Que signifie HTTP ? Qui envoie la **requête** et qui envoie la **réponse** ?

   > _Ma réponse :_ HTTP = HyperText Transfer Protocol. Le navigateur envoie la requête, le serveur envoie la réponse.

2. Combien de requêtes votre page `/presentation` a-t-elle déclenchées ? Lesquelles ?

   > _Ma réponse :_ 7 requêtes : presentation (la page HTML), style.css, une requête par image, et favicon.ico

3. Que signifie le code `200` ? Et le code `404` de la favicon ?

   > _Ma réponse :_ 200 : tout s’est bien passé, le fichier a été envoyé. 404 : la favicon n’existe pas sur le serveur.

4. Pourquoi les modifications faites dans l'onglet Éléments ne sont-elles pas visibles par les autres visiteurs ?

   > _Ma réponse :_ Les modifications sont faites seulement dans mon navigateur, sur ma copie de la page. Le fichier sur le serveur ne change pas

---

## 🟣 Exercice 7 — Envoyer des informations dans l'URL

1. Dans l'URL `https://www.youtube.com/results?search_query=chat`, quel est le nom du paramètre ? Quelle est sa valeur ?

   > _Ma réponse :_ Le paramètre est search_query, sa valeur est chat

2. Pourquoi le serveur plante-t-il avec `a=bonjour` ? Que faudrait-il faire pour l'éviter ?

   > _Ma réponse :_ Le code essaie de transformer bonjour en nombre (avec int()), ce qui est impossible : erreur 500. Il faut vérifier que la valeur est bien un nombre avant de l’utiliser, ou indiquer type=int dans request.args.get(...).

3. Pourquoi est-il dangereux d'afficher **tel quel** ce que l'utilisateur envoie ?

   > _Ma réponse :_ L’utilisateur peut envoyer du code (HTML ou JavaScript) qui serait exécuté dans le navigateur des autres visiteurs. C’est une faille appelée XSS

---

## 🟣 Exercice 8 — Les formulaires

1. Quelle est la différence visible entre GET et POST ?

   > _Ma réponse :_ En GET, les données apparaissent dans l’URL (?nom=valeur). En POST, elles ne sont pas dans l’URL

2. Pour un formulaire de **recherche**, quelle méthode choisiriez-vous ? Et pour un formulaire de **connexion avec mot de passe** ? Pourquoi ?

   > _Ma réponse :_ Recherche : GET, pour pouvoir copier ou partager le lien des résultats. Connexion : POST, pour que le mot de passe ne s’affiche pas dans l’URL ni dans l’historique.

3. Les données envoyées en POST sont-elles vraiment « secrètes » ? (Pensez à ce que vous avez vu dans l'onglet Réseau.)

   > _Ma réponse :_ Non. Elles sont visibles dans l’onglet Réseau (rubrique Charge utile / Payload). Seul le HTTPS les chiffre pendant le trajet.

---

## 🔴 Exercice 9 — Les codes de statut

1. Quelle est la différence entre une erreur `4xx` et une erreur `5xx` ? Qui est « fautif » dans chaque cas ?

   > _Ma réponse :_ 4xx : erreur du client (navigateur ou utilisateur), par exemple une page qui n’existe pas (404). 5xx : erreur du serveur, par exemple un bug dans le code (500).

2. Comment fonctionne une redirection ? Qui fait la deuxième requête : le serveur ou le navigateur ?

   > _Ma réponse :_ Le serveur répond avec un code 302 et une nouvelle adresse. C’est le navigateur qui fait ensuite la deuxième requête vers cette adresse.

3. Donnez un exemple de situation où un vrai site utilise une redirection.

   > _Ma réponse :_ Après une connexion réussie, le site redirige vers la page d’accueil. Autre exemple : http:// redirige vers https://

---

## 🔴 Exercice 10 — Ce que le serveur sait de vous

1. Citez trois informations que le serveur connaît sur vous, sans que vous ayez rien rempli.

   > _Ma réponse :_ Mon adresse IP, mon navigateur et mon système (User-Agent), et ma langue (Accept-Language).

2. À quoi peut servir l'en-tête `Accept-Language` pour un site comme Wikipédia ?

   > _Ma réponse :_ À afficher automatiquement le site dans la langue de l’utilisateur (par exemple en français).

3. Dans l'Access log, retrouvez une requête qui a reçu un code `404`. Quelle page était demandée ?

   > _Ma réponse :_ /favicon.ico (à vérifier dans ton Access log : ça peut aussi être une page mal tapée).

4. Après cet exercice, que pensez-vous de la notion de « navigation anonyme » ?

   > _Ma réponse :_ Elle n’est pas vraiment anonyme : elle efface seulement l’historique et les cookies sur mon ordinateur. Le serveur voit toujours mon IP, mon navigateur et ma langue.

---

## 🔴 Exercice 11 — Le Web des machines : API et JSON

1. Quelle est la différence entre une page HTML et une réponse JSON ? À qui chacune est-elle destinée ?

   > _Ma réponse :_ Une page HTML est destinée à un humain : le navigateur l’affiche mise en forme. Une réponse JSON est destinée à un programme : ce sont des données brutes, faciles à lire par une machine.

2. Dans la page `/horloge`, quel code s'exécute sur le **serveur** et quel code s'exécute dans le **navigateur** ?

   > _Ma réponse :_ Le Python (Flask) s’exécute sur le serveur : il envoie l’heure en JSON. Le JavaScript s’exécute dans le navigateur : il demande l’heure au serveur et met la page à jour.

3. Citez une application de votre téléphone qui, selon vous, utilise une API. Quelles données échange-t-elle ?

   > _Ma réponse :_ Une application météo : elle envoie ma position à une API et reçoit la température et les prévisions en JSON

---

## 🏁 Pour conclure

En quelques phrases, expliquez à un ami ce qui se passe entre le moment où il tape une adresse dans son navigateur et celui où la page s'affiche :

> _Ma réponse :_ 
