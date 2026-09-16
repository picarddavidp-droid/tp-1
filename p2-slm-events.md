## SLA / SLO proposés

- SLA priorité critique : première réponse sous 1h, résolution sous 4h — SLO : 99% des tickets critiques répondus dans ce délai
- SLA priorité haute : première réponse sous 4h, résolution sous 1 jour ouvré — SLO : 95% de respect
- SLA priorité normale : première réponse sous 1 jour ouvré, résolution sous 3 jours ouvrés — SLO : 90% de respect

## Classification des logs

| Log | Classification | Justification | Action |
|---|---|---|---|
| Connexion utilisateur réussie (WKS-042) | Informational | Comportement normal | Aucune |
| Disque SRV-FILE01 à 82% (seuil 80%) | Warning | Seuil dépassé, pas d'impact immédiat | Planifier nettoyage/extension avant saturation |
| Portail helpdesk injoignable 4min12 | Exception | Service analysé lui-même indisponible | Ouverture d'un Incident, redémarrage du service |
| Sauvegarde nightly-backup terminée | Informational | Comportement normal | Aucune |
| Lien réseau switch-3F-port12 down, flapping 6/10min | Exception | Anomalie avérée, impact potentiel sur plusieurs postes | Ouverture d'un Incident, vérification du port physique |
