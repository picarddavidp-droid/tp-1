## RFC — Centralisation de la saisie des tickets via GLPI

- **Type** : Normal (modifie une habitude de travail des utilisateurs et techniciens, nécessite une évaluation collective)
- **Impact** : tous les utilisateurs internes (nouveau point d'entrée unique) et les techniciens (discipline de saisie systématique) ; risque de contournement de GLPI par habitude dans les premiers jours
- **Plan de rollback** : si l'usage de GLPI reste sous 50% après 2 semaines, réactivation temporaire de la prise de ticket par appel en parallèle, avec ressaisie obligatoire dans GLPI par le technicien
- **Validation CAB simulée** :
  - Demandeur : "Coût technique faible, GLPI est déjà en place, et le plan de rollback sécurise la bascule"
  - Approbateur : "Approuvé sous réserve d'une communication aux utilisateurs avant bascule et d'un suivi du taux d'usage à J+15"

## Article de base de connaissance

- **Symptôme** : un utilisateur signale avoir déjà signalé le même problème plusieurs fois sans traitement visible
- **Cause** : demande initiale faite par un canal non tracé (appel direct), jamais saisie dans GLPI
- **Résolution** : créer un ticket GLPI recensant l'historique des signalements, l'assigner nominativement, communiquer le numéro de ticket à l'utilisateur
- **Mots-clés** : ticket perdu, appel direct, GLPI, doublon, traçabilité

## Positionnement dans le Product and Service Lifecycle

Ce changement mobilise principalement les étapes **Build** (mise en place technique de l'obligation de saisie GLPI) et **Transition** (bascule effective, communication, suivi de l'adoption). Les deux étapes se chevauchent : le retour d'usage collecté pendant la Transition peut renvoyer vers une nouvelle itération de Build avant même que la Transition soit terminée.
