# Rapport Lighthouse

## Conditions de mesure

Lighthouse : navigation, mobile, quatre catégories.
axe : contrôle de la page d’accueil servie par l’aperçu local.

## Scores Lighthouse

| Catégorie | Avant | Après |
| --- | ---: | ---: |
| Performance | 99 | 82 |
| Accessibilité | 96 | 100 |
| Bonnes pratiques | 96 | 100 |
| SEO | 82 | 83 |

## Violations axe

- Avant : 1 violation. `html-has-lang` — l’élément `<html>` n’avait pas d’attribut `lang` (1 occurrence). Aucune autre violation n’a été signalée.
- Après : 0 violation.

## Corrections effectuées

- Suppression du premier tableau JSON en double ; le tableau valide contient 12 livres.
- Déclaration de la langue française du document.
- Ajout d’un lien clavier vers le contenu principal et d’une cible focalisable.
- Remplacement du titre générique par un titre propre au site.

## Corrections restantes

Aucune violation d’accessibilité n’est signalée par axe ou les audits d’accessibilité Lighthouse après les corrections. axe rappelle que les contrôles automatisés ne remplacent pas une vérification manuelle.
