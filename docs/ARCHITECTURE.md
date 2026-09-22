# OpenG7 AI Evals — architecture

## Mission et état

Mesurer de façon reproductible la qualité, la sûreté et la fiabilité des modèles et agents OpenG7.
Le dépôt contient actuellement cadrage et gouvernance. Les modules décrits
dans le [README](../README.md) sont une architecture cible, pas du code livré.
Aucun build applicatif n’est disponible avant ajout de ses manifests et sources.

## Frontières

Le framework possède suites, fixtures, exécution isolée, scorers et rapports. L’entraînement appartient à Mini Code Lab, l’exécution opérationnelle à Agent Runtime et le routage à Model Gateway.

API/dashboard → orchestration des runs → suites, cas et résultats → ports de runners/scorers/artefacts. Les sorties brutes restent reliées aux scores; un scorer fournisseur est un adaptateur remplaçable.

## Invariants de conception

Appliquer les [invariants du projet](../AGENTS.md#périmètre-local) aux contrats,
aux adaptateurs et à leurs tests; ils restent définis à cet endroit unique.

## Évolution

Garder les contrats de domaine indépendants des fournisseurs et les effets dans
les adaptateurs. Pour matérialiser un module, documenter ses entrées/sorties,
consommateurs, permissions, état d’implémentation et validations disponibles.
Mettre à jour cette frontière si elle change; les consignes d’exécution restent
dans [AGENTS.md](../AGENTS.md), sans recopier une autre stack.
