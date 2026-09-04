# Page publique de suivi — Taxi DZ

Page consultée par un tiers à qui un passager a envoyé son lien de suivi. Elle affiche la position
du véhicule, l'état de la course, la plaque et le prénom du chauffeur. Rien d'autre.

## ⚠️ Ne pas éditer ici

La source est `apps/trip-share/index.html` dans le monorepo privé `ttokkee/taxi-dz`. Ce dépôt en
reçoit une copie, publiée par `scripts/publier-page-suivi.sh`. Une modification faite directement
ici serait écrasée à la publication suivante — et, pire, elle rendrait faux ce que le monorepo
donne à relire.

## Pourquoi ce dépôt est public

Pour une seule raison : GitHub Pages n'est pas disponible sur un dépôt privé sans plan payant, et
cette page doit être atteignable par quelqu'un qui n'a pas de compte — c'est toute sa fonction.

Rien ici n'est sensible. La page ne porte **aucune clé** : ni clé publiable, ni jeton d'API. Elle
appelle un point d'entrée public dont le seul contrôle d'accès est un jeton de 32 octets d'aléa,
transmis dans le **fragment** de l'URL — donc jamais envoyé à un serveur, jamais journalisé, jamais
présent dans un en-tête `Referer`. Le code du produit, lui, reste privé.

## Ce qu'elle ne montre jamais

Ni le téléphone du passager, ni son nom, ni le nom de famille du chauffeur, ni l'adresse écrite de
la destination, ni l'historique, ni le montant. La liste de ce qui sort est fixée **côté serveur**,
colonne par colonne ; cette page ne peut pas en demander davantage.

Trente minutes après la fin de la course, le lien se ferme et la page n'affiche plus rien.
