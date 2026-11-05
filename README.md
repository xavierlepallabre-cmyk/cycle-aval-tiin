# Cycle aval TIIN

Application pédagogique sur le **cycle aval du combustible nucléaire** pour les apprentis du **Bac Pro TIIN** — Lycée Alexis de Tocqueville, Cherbourg-en-Cotentin.

Elle suit le combustible usé de sa sortie du réacteur jusqu'au stockage :
- **La Hague** (10 vues) : réception et piscines, cisaillage et dissolution, extraction, purification de l'uranium et du plutonium, vitrification, compactage, effluents, laboratoires et ventilation ;
- **Andra** (9 vues) : classement des déchets de VTC à HA, colis, Cires, CSA, CSM, FA-VL, Cigéo et laboratoire de Bure, surveillance et mémoire.

Chaque parcours a un synoptique cliquable, des vues animées et une lecture guidée étape par étape, organisée en chapitres numérotés.

**Version de relecture.** L'application est faite pour être relue par un spécialiste du cycle aval : le bouton **Relecture** note une remarque en la rattachant automatiquement au parcours, à la vue et à l'étape affichés, puis exporte toutes les remarques dans un fichier. Mode d'emploi : `RELECTURE.md`.

Application statique, installable sur tablette et utilisable hors connexion, sur le même principe que Nucléa TIIN, Élec TIIN et Sûreté & Cycle TIIN : HTML, CSS et JavaScript natifs, sans framework, sans compte, sans serveur, sans aucune note. Projet indépendant : le cycle amont, le réacteur, la sûreté et les accidents restent dans Sûreté & Cycle TIIN.

**En ligne :** https://xavierlepallabre-cmyk.github.io/cycle-aval-tiin/

## Organisation du dossier

| Fichier | Rôle |
|---|---|
| `index.html` | page d'accueil, navigation entre les deux parcours, mode relecture |
| `lahague.html`, `andra.html` | les deux parcours, chacun utilisable seul |
| `charte.css` | charte commune des applications TIIN (couleurs, police) |
| `fonts/` | police Lexend embarquée (licence OFL) |
| `icons/` | icônes de l'application, logo du Bac Pro TIIN et logo du lycée |
| `manifest.json`, `service-worker.js` | installation et fonctionnement hors connexion |
| `tools/version.py` | calcule le numéro de version du cache à partir du contenu |
| `tests/test_site.py` | 24 vérifications dans un vrai navigateur |
| `SOURCES.md` | sources des données affichées |
| `RELECTURE.md` | mode d'emploi pour le relecteur |

## Tester sur un ordinateur

```
python -m http.server 8000
```

puis ouvrir http://localhost:8000. Avant chaque publication : `python tools/version.py`, puis `python tests/test_site.py`.

## Auteur et droits

Conception originale : Xavier Le Pallabre  
Ressource pédagogique développée à titre personnel, avec l’assistance d’outils d’intelligence artificielle.  
© 2026 Xavier Le Pallabre — Attribution de l’auteur original à conserver lors des réutilisations et adaptations, conformément à la licence applicable : [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.fr).

## Licence

Sauf mention contraire, le contenu de ce dépôt (code, textes, schémas, illustrations) est mis à disposition selon les termes de la licence **Creative Commons Attribution – Pas d'utilisation commerciale – Partage dans les mêmes conditions 4.0 International** ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.fr)). Texte complet : fichier `LICENSE`.

Tu peux le réutiliser, le copier et l'adapter, à trois conditions :
- **Attribution** : citer l'auteur original (Xavier Le Pallabre), indiquer la licence et signaler les modifications ;
- **Pas d'utilisation commerciale** : pas de vente ni d'usage dans un service payant ;
- **Partage dans les mêmes conditions** : diffuser les adaptations sous la même licence.

Le logo du Bac Pro TIIN est une création de Xavier Le Pallabre : il est couvert par cette licence, comme le reste de ses contenus.

Ne sont pas couverts par cette licence :
- la police Lexend (`fonts/`), sous licence SIL Open Font License 1.1 (voir `fonts/OFL.txt`) ;
- le logo du lycée Alexis de Tocqueville, propriété de l'établissement ;
- les noms, marques et documents des organismes cités (Orano, EDF, Framatome, Andra, ASNR, AIEA…), qui restent leur propriété : les parcours en donnent des schémas fonctionnels et des résumés, avec leurs sources (voir `SOURCES.md`).
