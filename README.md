# Jus Mouna — dossier du site

## Structure

```
index.html              La page du site (doit rester à la racine du domaine)
robots.txt               Indexation par les moteurs de recherche (racine obligatoire)
sitemap.xml               Liste des pages pour les moteurs de recherche (racine obligatoire)
site.webmanifest          Fichier PWA : nom, couleurs, icônes (racine obligatoire)
_headers                  Sécurité HTTP + cache, reconnu automatiquement par Netlify (racine obligatoire)
og-image.png              Image affichée quand le site est partagé (WhatsApp, Facebook...)

icons/                     Toutes les icônes du site (favicon, PWA, Apple)
  favicon.ico
  favicon-16.png
  favicon-32.png
  apple-touch-icon.png
  icon-192.png
  icon-512.png

legal/                     Pages légales, reliées depuis le pied de page du site
  confidentialite.html
  conditions.html
  cookies.html
```

## Avant la mise en ligne

1. Remplacer le domaine `jusmouna.ci` par votre vrai nom de domaine dans :
   `index.html` (balises meta, JSON-LD), `robots.txt`, `sitemap.xml`.
2. Renseigner votre numéro WhatsApp dans `index.html`, variable `CONFIG.whatsapp`.
3. Remplacer les avis clients de démonstration par de vrais avis (voir plus bas).
4. Faire relire les pages du dossier `legal/` par un professionnel du droit ivoirien.

## Comment fonctionnent les avis clients

Le site n'a pas de serveur : il ne peut donc pas recevoir et publier automatiquement
les avis de vos clients en temps réel. La section « Avis » fonctionne ainsi :

- Un client qui clique sur **« Envoyer mon avis sur WhatsApp »** vous envoie sa note
  et son commentaire directement sur WhatsApp.
- Vous choisissez ensuite les meilleurs avis et les ajoutez **à la main** dans le
  code (`index.html`, section `id="avis"`, bloc `rev-grid`) — chaque avis est un
  petit bloc `<article class="rev">` à copier/coller et modifier.

Si vous voulez des avis publiés automatiquement et visibles par tous sans
intervention manuelle, il faudra soit :
- connecter le site à une base de données (ex. Supabase, Firebase), soit
- utiliser une **fiche Google Business Profile**, qui gère nativement les avis
  publics et peut être reliée à votre site par un simple lien ou un widget.

## Déploiement

Ce dossier est prêt à être déposé tel quel sur un hébergeur statique (Netlify,
Vercel, GitHub Pages, etc.), `index.html` devant rester à la racine.
