# Qui mérite le Ballon d'Or 2026 ?

Le 26 octobre à Londres, France Football remet le Ballon d'Or 2026. Ici, on
prend les cinq attaquants les mieux cotés chez les bookmakers, les critères
officiels du règlement, et on regarde qui gagne selon ce qu'on décide de
peser. Verdict avant la cérémonie.

**La réponse courte : Ousmane Dembélé.** Il finit premier sous 54 % des
lectures possibles du règlement, Harry Kane sous 40 %. Tout se joue sur le
poids donné au palmarès : en dessous de 28 % environ, Kane passe devant.
Le marché des paris, lui, classe Dembélé dernier des cinq.

![sensibilité](figures/sensibilite.png)

## La méthode en deux minutes

Le règlement officiel (ballondor.com) fixe trois critères **par ordre
d'importance**, sans pondération chiffrée : 1. performances individuelles et
caractère décisif ; 2. performances collectives et palmarès ; 3. classe et
fair-play. La période d'éligibilité court du 3 août 2025 au 19 juillet 2026,
Coupe du monde et CAN incluses (article 3).

Puisque le règlement donne un ordre mais pas de poids, on ne choisit pas à
sa place : on calcule le classement sous **toutes les pondérations
compatibles avec la hiérarchie** (individuel > collectif > fair-play, par pas
de 5 %), soit 35 lectures possibles. Le scénario central présenté dans le
notebook (60/30/10) n'est qu'une illustration.

**Les candidats** : les cinq attaquants en tête des cotes bookmakers au
22/09/26 (capture dans `docs/`) — Kane, Yamal, Mbappé,
Kvaratskhelia, Dembélé. Sélection restreinte aux profils offensifs, car nos
indicateurs (buts, création) ne comparent pas équitablement un milieu ou un
défenseur. Messi, bien coté, est écarté : il joue en MLS, hors de nos
sources de données, on ne classe pas ce qu'on ne peut pas mesurer pareil.
Les cinq figurent parmi les 30 nommés officiels du 8 septembre 2026.

**Les données** : FBref : championnats, Coupe du monde et Ligue des Champions
Le palmarès et les distinctions sont saisis à la main depuis les palmarès publics.

**Ce qu'on mesure, critère par critère** :
- *Individuel* : buts hors penalty et passes décisives (en volume et par
  90 minutes, saison complète championnat + LdC + CDM), plus les
  distinctions individuelles (meilleur joueur de la LdC, soulier d'or...),
  qui traduisent le « caractère décisif et impressionnant » du règlement.
- *Collectif* : les trophées gagnés dans la fenêtre officielle, lecture à la
  lettre de l'article 3 — tout ce qui est gagné entre les deux dates compte,
  supercoupes incluses. Barème choisi : CDM 6, LdC 5, championnat 3, coupe
  nationale 1, supercoupe 0.5 (vainqueur = 1, finaliste = 0.5, 3e de CDM =
  0.25, 4e = 0.15).
- *Fair-play* : les cartons par 90 minutes, un rouge pesant trois jaunes.

Chaque indicateur est ramené entre 0 et 1 sur nos cinq candidats : le
meilleur du groupe vaut 1, le moins bon 0. Un 0 ne veut donc pas dire
« rien »

## Le profil de chaque candidat

![profils](figures/profils.png)

Trois façons de mériter un Ballon d'Or, incarnées : Mbappé écrase le critère
individuel et n'a rien d'autre ; Dembélé et Kvaratskhelia ont le palmarès
parisien, Dembélé y ajoute la production ; Kane est le seul complet partout —
et c'est pour ça qu'il gagne dès que le palmarès pèse peu.

## Le marché avait-il raison ?

Les cotes au 22/09/26 classaient : Kane, Yamal, Mbappé, Kvaratskhelia,
Dembélé. Notre score : Dembélé, Kane, Yamal, Mbappé, Kvaratskhelia. Sur
Kane, le marché et le règlement convergent. Sur Dembélé, tout les oppose :
dernier des 5 chez les bookmakers, premier sous une majorité de lectures du
règlement. Réponse le 26 octobre.

## Les limites

- Le fair-play réduit aux cartons : le règlement parle de « classe », les
  données publiques ne permettent de la mesurer ;)
- Pas de métriques attendues (xG) dans nos tableaux : on mesure la
  production réelle — comme le jury, qui vote sur ce qui s'est passé.
- La normalisation sur cinq joueurs amplifie les écarts : 0 = dernier des
  cinq, pas nul dans l'absolu.
- La CAN est dans la période officielle mais aucun de nos cinq n'y a joué.
- Barèmes du palmarès et des distinctions : des choix, affichés dans le
  notebook, faits pour être discutés — l'analyse de sensibilité montre que
  la conclusion principale y résiste.


## Reproduire

    python -m venv .venv
    source .venv/bin/activate
    pip install -r requirements.txt
    jupyter lab

Ouvrir `notebooks/01_ballon_dor.ipynb` et tout exécuter. Premier lancement :
la bibliothèque télécharge les pages via un navigateur piloté (quelques
minutes) ; ensuite tout vient du cache local.

## Sources

Stats : FBref (fbref.com), via la bibliothèque soccerdata — données mises en
cache localement, non redistribuées dans ce dépôt.
Règlement : ballondor.com, « Tous les critères et le règlement complet du
Ballon d'Or 2026 ».
Cotes : capture datée dans `docs/`.
