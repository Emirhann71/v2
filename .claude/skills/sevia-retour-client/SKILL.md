---
name: sevia-retour-client
description: Use when Emirhan sends 3 images (gabarit vierge "Retour Client", capture d'un avis/message client, photo du bouquet) et demande de générer le visuel SEVIA Flowers story/post Instagram-TikTok.
---

# SEVIA Flowers — Visuel "Retour Client"

Crée le prochain « Retour Client » SEVIA Flowers à partir des 3 images jointes. Si l'ordre n'est pas précisé, identifie-les par leur contenu : le gabarit a un cercle et une carte blanche vides, la capture d'avis est une interface d'app/message, la photo du bouquet est une photo produit réelle.

- Image 1 : gabarit.
- Image 2 : avis/message client.
- Image 3 : bouquet concerné.

L'image n°1 reste la référence absolue : conserve exactement tout ce qui n'est pas explicitement demandé ci-dessous.

## Règles

- Lis uniquement le message écrit par le client dans l'image 2.
- Ignore interface, étoiles, dates, réponse SEVIA, boutons et autres éléments.
- Corrige uniquement les fautes évidentes, sans reformuler.
- Conserve les emojis d'origine et n'en ajoute aucun.
- N'ajoute pas de guillemets.

## Bouquet

- Insère l'image 3 dans le cercle.
- Montre le bouquet dans son ensemble.
- Laisse visible une partie de l'emballage/accessoires.
- Évite tout gros plan uniquement sur les fleurs.
- Reste fidèle à la photo originale (ne modifie pas couleur, quantité, emballage, accessoires, initiales, rubans).

## Couleurs

- Fond : `#FBF3EF`
- RETOUR : `#6E1E28`
- Client : `#6E1E28`
- Témoignage : `#6E1E28`
- Identité : `#6E1E28`
- Provenance : `#6E1E28`
- Carte : `#FFFFFF`

## Polices

- RETOUR : Playfair Display
- Client : conserve exactement le script manuscrit du gabarit (ne le redessine pas avec une autre police)
- Témoignage, identité, provenance : Playfair Display Regular (jamais Karla/Arial/Helvetica ou une sans-serif pour le témoignage)

## Identité

- Prénom + initiale du nom si les deux sont clairement disponibles.
- Sinon prénom uniquement.
- Sinon « Client SEVIA ».
- Ne jamais inventer d'identité.
- Ne jamais afficher un @ ou pseudo complet Instagram/Snapchat.

## Source

- Google → « Avis Google »
- Instagram → « Message Instagram »
- Snapchat → « Message Snapchat »
- Judge.me → « Avis sur seviaflowers.fr »
- Si la source est incertaine, n'affiche aucune provenance.

## Carte blanche

Ordre obligatoire, tout centré et à l'intérieur de la carte :

1. Témoignage (dominant)
2. Identité (plus petite)
3. Provenance (encore plus discrète)

Si le témoignage est long, réduis uniquement sa taille de police (jamais sa police, sa couleur ou son alignement) pour qu'il tienne.

## Respect du gabarit

Ne déplace, n'agrandis et ne redesign aucun élément du gabarit. Conserve exactement : RETOUR, Client, le cercle (taille et position), la carte blanche (taille, forme, coins arrondis), le fond, les espacements, @SEVIAFLOWERS (police, couleur, espacement). N'ajoute aucun logo, étoile, badge ou icône.

## Résultat

Une seule image finale, format exact 9:16, prête pour Story Instagram et TikTok. Réponds uniquement avec l'image finale — aucune explication, variante ou texte après génération (livraison via SendUserFile, caption vide ou quasi vide).

## Méthode d'implémentation

Utilise un script Python (Pillow) plutôt que de décrire le rendu : charge le gabarit comme base (ne redessine jamais fond/titre/@SEVIAFLOWERS), mesure par pixels le centre/rayon du cercle et la bbox de la carte pour ne jamais les déplacer, recadre le bouquet en carré centré puis masque circulaire à coller sur le gabarit, vérifie que Playfair Display est disponible (`fc-list | grep -i playfair`, sinon télécharge-la), écris le texte avec réduction itérative de taille jusqu'à ce qu'il tienne, puis exporte en PNG 1080×1920.
