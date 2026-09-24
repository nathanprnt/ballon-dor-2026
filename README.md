# Qui mérite le Ballon d'Or 2026 ?

Le 26 octobre à Londres, France Football remet le Ballon d'Or 2026. En
attendant, on a pris les cinq attaquants les mieux cotés chez les
bookmakers et les critères officiels du règlement, et on a regardé qui
gagne selon ce qu'on décide de peser.

La réponse courte : Ousmane Dembélé. Il finit premier sous 54 % des
lectures possibles du règlement, contre 40 % pour Harry Kane. Tout se joue
sur le poids qu'on donne au palmarès : en dessous de 28 % environ, Kane
repasse devant. Le marché des paris, lui, classe Dembélé dernier des cinq.

![sensibilité](figures/sensibilite.png)

## La méthode en deux minutes

Le règlement officiel (ballondor.com) fixe trois critères par ordre
d'importance, sans pondération chiffrée : 1. performances individuelles et
caractère décisif ; 2. performances collectives et palmarès ; 3. classe et
fair-play. La période d'éligibilité court du 3 août 2025 au 19 juillet
2026, Coupe du monde et CAN incluses (article 3).

Le règlement donne un ordre mais pas de poids. Plutôt que d'en choisir un
à sa place, on calcule le classement sous toutes les pondérations qui
respectent la hiérarchie (individuel > collectif > fair-play, par pas de
5 %), soit 35 lectures possibles. Le scénario central du notebook (60/30/10)
n'est qu'une illustration parmi elles.

Les candidats : les cinq attaquants en tête des cotes bookmakers au
22/09/26 (capture dans `docs/`), à savoir Kane, Yamal, Mbappé,
Kvaratskhelia et Dembélé. On reste entre profils offensifs, parce que nos
indicateurs (buts, création) ne permettent pas de comparer équitablement
un milieu ou un défenseur. Messi, bien coté, est écarté : il joue en MLS,
hors de nos sources de données, et on ne classe pas ce qu'on ne peut pas
mesurer
