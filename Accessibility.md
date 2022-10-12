**Je documente ici ce que je trouve pendant mes recherches sur ce sujet**

# Accessibilité

## Tab Index :
​
**-1 :** ne permet pas d'accéder à l'élément.
​
**0 :** l'élément peut capturer le focus et être atteint via la navigation au clavier, cependant son ordre relatif est défini par la plateforme, généralement selon l'ordre des éléments du DOM
​
**Une valeur positive :** l'élément peut capturer le focus et peut être atteint via la navigation au clavier, l'ordre relatif dans la navigation est défini par la valeur de l'attribut. Les navigations seront parcourues dans l'ordre croissant.

## ARIA :

**Aria-hidden:** Boolean
* false = élément affiché à l’écran et vocalisé
* true = élément affiché à l’écran et non vocalisé
Cet attribut permet de **masquer** un élément (ou un groupe d’éléments) pour les lecteurs d’écran. 

**Aria-modal:** Boolean
Indique aux technologies d'assistance que les fenêtres situées sous la boîte de dialogue actuelle ne sont pas disponibles pour une interaction.

**Aria-roledescription:** String i18n
Définit une description lisible par l'homme, pour le rôle d'un élément.
Certaines technologies d'assistance, comme les lecteurs d'écran, présentent le rôle d'un élément dans le cadre de l'expérience utilisateur.

**Aria-role: region:**
Le rôle de région doit être réservé aux sections de contenu suffisamment importantes pour que les utilisateurs veuillent y accéder facilement et qu'elles soient mentionnées dans un résumé de la page.

**Aria-live:** off | polite | assertive
A des roles "live" prédéfinit.
* Polite indique au lecteur d’écran qu’il doit attendre que l’utilisateur soit inactif avant de lui présenter une mise à jour. C’est la valeur la plus utilisée.
* Polite est à privilégier, la valeur assertive brise le flux de lecture.
Les changements de contenu simples, sans interaction possible, devraient être marqués comme des zones « live ».
Toute zone recevant une mise à jour qu’il est important de faire suivre à l’utilisateur, mais pas au point de le déranger dans sa navigation, devrait avoir l'atribut polite. Le lecteur d’écran lira les changements dès que l’utilisateur sera inoccupé.
Ajouter un polite pour attendre le "rechargement" du contenu avant de l'énoncer.

**Aria-label:** String i18n
Il est utilisé pour définir une légende non-visible associée à un élément HTML dont le sens est transmis uniquement par le visuel.
Par exemple, une croix pour fermer une fenêtre modale.

**Role:** Définit le rôle d’un élément.
* Si l’élément n’a pas de rôle, l’attribut role va en ajouter un.
* Si le composant en a déjà un, alors l'attribut role va écraser ce rôle existant.
Si un rôle ARIA est ajouté, il écrasera la sémantique native de l'élément. Il faut utiliser cet attribut que pour des éléments vides de sémantique, comme un div.

**Aria-labelledby:** String i18n
Décrit la nature d’un objet.
Il est utilisé pour établir une relation entre les composants, ou les groupes, et leurs labels. Les utilisateurs de technologies d’assistance telles que les lecteurs d’écran, naviguent généralement dans un document en tabulant entre les zones de l’écran. Si un label n’est pas associé à un élément de saisie, un composant ou un groupe, il ne sera pas lu par le lecteur d’écran.

**Aria-describedby:** String i18n
Description fournissant des informations pouvant être utiles à l’utilisateur.
Il est utilisé pour indiquer l’identifiant des éléments qui décrivent l’objet. Il est utilisé pour établir une relation entre des composants ou des groupes et un texte les décrivant

### Exemple d'utilisation de aria-labelledby, aria-describedby et id :

```
<div role="applicaton" aria-labelledby="calendar" aria-describedby="info">
    <h1 id="calendar">Calendrier<h1>
    <p id="info">
        Ce calendrier affiche les prévisions de match du Racing Métro.
    </p>
    <div role="grid">
        …
    </div>
</div>
```

## Autres

**Alt**: String i18n
Il permet aux lecteurs d'écrans de décrire l'image.