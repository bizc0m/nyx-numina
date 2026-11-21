# Numina — audit QA et captures — 2026-11-17

## Checkout et périmètre

- Checkout isolé : `/Users/JOB/Documents/Codex/2026-10-31/tu/outputs/nyx-numina-communication`
- Branche : `codex/p-01-025-numina`
- HEAD de départ : `6fe25805279bd440432e756f69f026908158ce6a`
- Fichier produit modifié : `index.html`
- Les essais navigateur ont utilisé un profil Chrome temporaire QA (`/tmp/nyx-numina-qa-interaction`) et le serveur local `http://127.0.0.1:8766/`. Aucun stockage local utilisateur n’a été chargé ni modifié.

## Changements livrés

- La page d’accueil Catalogue contient trois menus déroulants multisélection : **Déesse / figure**, **Titre / appellation**, **Fonction / rôle**. Chaque item possède une case, une forme anglaise et un bouton « Fiche » distinct.
- Les menus s’ouvrent au-dessus du contenu, se ferment au clic extérieur ou avec Échap, et restent dans les limites de l’écran.
- Les sélections persistent lorsqu’on passe d’un thème à l’autre; les compteurs reflètent les sélections par champ.
- La composition exige au moins deux champs distincts. Elle propose les paires possibles et la combinaison à trois champs, applique uniformément le préfixe Nyx et limite l’affichage à 48 noms.
- Les propositions affichent l’évocation, les champs assemblés, les formes anglaises, les origines, les réserves et les sources. Elles peuvent être copiées ou ajoutées au chariot; le prompt Perplexity est construit à partir du chariot.
- Les dossiers de Seshat, Athéna, Hécate et Mnémosyne contiennent chacun quatre chapitres sourcés; leurs longueurs respectives sont 761/774/782/820, 730/806/754/848, 824/841/838/861 et 832/823/780/911 caractères.
- La fiche directe `#fiche-66` ouvre la fiche 66 après le chargement.

## Vérifications effectuées

- `node --check /tmp/numina-inline.js` : réussi.
- `git diff --check` : réussi.
- Chrome headless avec interactions réelles : ouverture des trois menus, sélection de Seshat/Muse/Archiviste, conservation de la sélection lors d’un changement de thème, propositions à deux et trois champs, ajout au chariot, prompt Perplexity contenant la composition et chaque item : réussi.
- Dossier Seshat ouvert dans l’interface : quatre chapitres affichés, chacun au-dessus de 500 caractères, avec sept liens de source associés : réussi.
- Dimensions contrôlées : 320×568, 390×844, 768×1024, 1280×800, 1920×1080. Aucun débordement horizontal; les trois commandes et le menu ouvert restent dans la zone visible; Échap ferme le menu.
- Lien direct `#fiche-66` : sélection active 66, titre Aurora, inspecteur visible.
- Aucune exception JavaScript non gérée pendant les parcours QA.
- Serveur local : HTTP 200.

## Captures

- `qa/numina-dropdown-320.png` — menus visibles sur petit écran, menu déplié.
- `qa/numina-dropdown-1280.png` — menus visibles en largeur bureau, menu déplié.
- `qa/numina-product-proposal-1280.png` — exemple composé : **Nyx Seshat Muse Archivist**.

## Empreintes SHA-256

- `index.html` : `be66d0737afe34c69b905611c2ee7474869900918e1b9a5da930e867441d3d7f`
- `qa/numina-dropdown-1280.png` : `0c3e342fb034f3c962cccea12f7c5ab51fc8c7553d2bb21bcf40ab013b69010e`
- `qa/numina-dropdown-320.png` : `2587cce211f44e3ad9fd5c608b5f355490fe78590458167dc6409b26fd5ccf77`
- `qa/numina-product-proposal-1280.png` : `56c1eb235fc14a3373e07ec97cc7267431873feb27f370c25ef3b47cdf18b95c`


## Limites restantes

- Les fiches complètes de tout le catalogue ne sont pas encore rédigées; les quatre dossiers ci-dessus sont les seuls à dépasser maintenant le minimum demandé.
- Le corpus candidat des 100 propositions n’était pas présent; il n’a pas été inventé.
- Les essais automatisés couvrent le parcours de composition et l’affichage des menus. Import/export, presse-papiers et contrôles commerciaux restent hors de cette passe.
- Aucun commit, push ni déploiement GitHub Pages n’a été effectué.
