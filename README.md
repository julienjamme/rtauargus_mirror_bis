
<!-- README.md is generated from README.Rmd. Please edit that file -->
rtauargus
=========

### τ-Argus depuis R

Le package *rtauargus* offre une interface **R** pour **τ-Argus**.

Il permet de :

-   créer les inputs (fichiers asc et rda) à partir de données au format R ;
-   générer la séquence d'instructions à exécuter en mode batch (fichier arb) ;
-   lancer un batch τ-Argus en ligne de commande ;
-   récupérer les résultats dans R.

Ces différentes opérations peuvent être exécutées en une seule fois, mais aussi de manière modulaire. Elles permettent d'intégrer les tâches réalisées par τ-Argus dans une chaîne de traitement écrite en R.

Le package présente d'autres fonctionnalités annexes, comme créer une variable hiérarchique à partir de microdonnées.

### Exemple simple

``` r
rtauargus(
  microdata        = donnees,
  explanatory_vars = c("variable1", "variable2"),
  safety_rules     = "FREQ(3,10)",
  suppress         = "GH(1,100)"
)
```

Une prise en main détaillée est disponible par `vignette("rtauargus")`.

### Remarques importantes

Les fonctions de *rtauargus* appelant τ-Argus nécessitent que ce logiciel soit accessible depuis le poste de travail. Le téléchargement de τ-Argus se fait sur la [page dédiée](http://neon.vb.cbs.nl/casc/tau.htm) du site de l'office néerlandais de statistiques. Cependant, toutes les fonctions n'exécutent pas τ-Argus (création des microdonnées...). Ne pas l'avoir sur son poste n'est donc pas bloquant.

Le package a été développé sur la base des versions open source de τ -Argus (versions 4.1 et supérieures), en particulier la dernière version disponible lors du développement (4.1.7). **Il n'est pas compatible avec la version 3.5.**

Pour l'instant, **seules les microdonnées sont acceptées** en entrée (pas les données déjà tabulées).