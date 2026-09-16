# TP ITIL 5 — Amélioration du service helpdesk interne

## Ticket de demande de service GLPI (Service Request Management)

Export GLPI de la file en cours au moment de la clôture du cas :

| ID | Titre | Statut | Dernière modification | Date d'ouverture | Priorité | Demandeur | Attribué à | Catégorie |
|---|---|---|---|---|---|---|---|---|
| 1 | problème de connexion au vpn | En cours (Attribué) | 2026-09-14 12:00 | 2026-09-14 07:58 | Haute | glpi | glpi | — |
| 2 | problème imprimante | En cours (Attribué) | 2026-09-14 12:00 | 2026-09-14 09:25 | Moyenne | glpi | glpi | — |
| 3 | problème boite mail | En cours (Attribué) | 2026-09-14 09:26 | 2026-09-14 09:26 | Moyenne | glpi | glpi | — |
| 4 | problème Logiciel Compta | En cours (Attribué) | 2026-09-14 10:02 | 2026-09-14 10:02 | Moyenne | glpi | glpi | — |

**Ticket traité : #1 — problème de connexion au vpn**

C'est le ticket le plus ancien encore ouvert et celui en priorité Haute : il illustre directement le symptôme diagnostiqué en Partie 1 (délai entre l'ouverture à 07:58 et la dernière prise en charge à 12:00, soit plus de 4h sans clôture, alors que le SLA critique/haute priorité défini en Partie 2 impose une première réponse sous 4h). Son traitement dans le nouveau workflow centralisé (amélioration n°1 du CSI Register) consiste à confirmer l'assignation, résoudre la connexion VPN, puis clôturer uniquement après confirmation de l'utilisateur — étape qui manquait dans l'ancien fonctionnement.

Cette demande relève de la pratique **Service Request Management** dès lors qu'elle est traitée comme une action planifiée et suivie dans l'outil, et non comme un appel non tracé résolu "à la volée" sans trace ni confirmation — c'est précisément ce changement de traitement que la RFC-2026-0912-001 vise à généraliser.

## Synthèse par partie

| Partie | Pratique(s) ITIL 5 mobilisée(s) |
|---|---|
| Partie 1 — Diagnostic | Analyse des 4 dimensions du service, Continual Improvement (CSI Register), Principes directeurs |
| Partie 2 — Pilotage | Service Level Management (SLA/SLO), Event Management |
| Partie 3 — Changement | Change Enablement (RFC), Knowledge Management, Product and Service Lifecycle |
| Partie 4 — Clôture | Service Request Management |

## Principe directeur le plus structurant

Sur l'ensemble du cas, **"Progresser de manière itérative avec du feedback"** reste le principe le plus structurant : le CSI Register priorise d'abord la centralisation des tickets (Partie 1), le changement associé est déployé avec une phase de communication et un suivi du taux d'adoption avant d'être jugé définitif (Partie 3), et le ticket GLPI de clôture (Partie 4) sert justement de point de mesure pour décider si l'itération suivante (amélioration n°2, le workflow standardisé) doit démarrer. Aucune étape du TP ne traite le problème "d'un coup" — chaque livrable s'appuie sur le retour du précédent.

## Point critique — AI Governance et modèle 6C

Sur ce cas précis, l'apport du module **AI Governance** et du modèle **6C** est **limité, et je le justifie plutôt que de l'affirmer vaguement** :

- Le dysfonctionnement diagnostiqué (tickets perdus, absence de traçabilité, rappels multiples) est un problème de **processus et d'organisation**, pas un problème nécessitant de l'intelligence artificielle. Ajouter une brique IA (ex. classification automatique de tickets) sur un service qui n'a même pas encore de canal de saisie unique reviendrait à optimiser une étape avant d'avoir fiabilisé les étapes en amont — contraire au principe "Progresser de manière itérative".
- Un exemple concret où le 6C pourrait s'appliquer plus tard, une fois GLPI centralisé : une fois que tous les tickets remontent dans un canal unique avec un historique fiable (résultat de la Partie 3), un modèle de classification automatique des tickets par priorité pourrait exploiter cet historique pour proposer une pré-priorisation. Mais cela suppose une capacité **Data** (qualité des données GLPI) et **Change management IA** (le 6C) qui n'existent pas encore sur ce cas — l'améliorer maintenant ferait porter le risque d'un déploiement IA sur une donnée non fiabilisée.
- Conclusion : sur ce TP, la non-pertinence immédiate de l'IA est elle-même le résultat d'une analyse rigoureuse par les 4 dimensions (Partie 1), pas d'un rejet de principe du module AI Governance.

---
*TP réalisé dans le cadre du BTS TSSR — 4 demi-journées, une partie par demi-journée.*
