<img src="images/media/image1.jpeg" style="width:8.49653in;height:6.25in" />

# GUIDE De mise en œuvre TECHNIQUE 2024 DU PROGRAMME DE CIBLAGE du fret AÉRIEN PRÉALABLE AU CHARGEMENT

[Aperçu](#aperçu)

[Contexte](#contexte)

[Portée](#portée)

[Public visé](#public-visé)

[Participants nécessaires et admissibles](#participants-nécessaires-et-admissibles)

[Participants nécessaires (transporteurs aériens)](#participants-nécessaires-transporteurs-aériens)

[Participants admissibles (autres présentateurs de données)](#participants-admissibles-autres-présentateurs-de-données)

[Points de contact réglementaires](#points-de-contact-réglementaires)

[Date d’entrée en vigueur](#date-dentrée-en-vigueur)

[Connexion au programme CFAPC](#connexion-au-programme-cfapc)

[Diagramme de ciblage du CFAPC](#diagramme-de-ciblage-du-cfapc)

[Inscription au CFAPC](#inscription-au-cfapc)

[Inscription](#inscription)

[Configuration initiale et connexion](#configuration-initiale-et-connexion)

[Messages bidirectionnels](#messages-bidirectionnels)

[Configuration des webhook](#configuration-des-webhook)

[Exigences de présentation et réponses](#exigences-de-présentation-et-réponses)

[Environnements d’essai et de production du CFAPC](#environnements-dessai-et-de-production-du-cfapc)

[Environnement d’essai du CFAPC](#environnement-dessai-du-cfapc)

[Environnement de production du CFAPC](#environnement-de-production-du-cfapc)

[Caractéristiques des messages du CFAPC](#caractéristiques-des-messages-du-cfapc)

[Formats des messages](#formats-des-messages)

[Versions prises en charge des messages du CFAPC](#versions-prises-en-charge-des-messages-du-cfapc)

[Versions Cargo-XML prises en charge](#versions-cargo-xml-prises-en-charge)

[Versions C-IMP prises en charge](#versions-c-imp-prises-en-charge)

[Versions CAMIR prises en charge](#versions-camir-prises-en-charge)

[Réponses aux messages Cargo-XML](#réponses-aux-messages-cargo-xml)

[Réponses aux messages XFNM](#réponses-aux-messages-xfnm)

[Messages d’avis de statut XCSN](#messages-davis-de-statut-xcsn)

[Réponses aux messages CAMIR](#réponses-aux-messages-camir)

[Messages de rapport d’erreur préliminaire (PER)](#messages-de-rapport-derreur-préliminaire-per)

[Messages d’avis de statut préliminaire (PSN)](#messages-davis-de-statut-préliminaire-psn)

[Codes de réponse HTTP](#codes-de-réponse-http)

[Exemples de messages du CFAPC](#exemples-de-messages-du-cfapc)

[Exemple de présentation d’un message Cargo-XML](#exemple-de-présentation-dun-message-cargo-xml)

[Exemple de présentation d’un message C-IMP](#exemple-de-présentation-dun-message-c-imp)

[Diagramme du ciblage du CFAPC](#diagramme-du-ciblage-du-cfapc)

[Glossaire](#glossaire)

[Caractères et descriptions inacceptables](#caractères-et-descriptions-inacceptables)

[Caractères inacceptables dans le nom ou l’adresse de l’expéditeur/du destinataire ou dans la description des marchandises](#caractères-inacceptables-dans-le-nom-ou-ladresse-de-lexpéditeurdu-destinataire-ou-dans-la-description-des-marchandises)

[Descriptions de marchandises inacceptables](#descriptions-de-marchandises-inacceptables)

# Historique des modifications

| Date         | Version | Section(s) | Description/motif  |
|--------------|---------|------------|--------------------|
| 26 jan. 2024 |         |            | Diffusion initiale |
|10 avril 2024 |1.1 |[Éléments de données du CFAPC](#elements-de-données-du-CFAPC) |Remarque sur l’heure de départ|
| | |[Environnements d’essai et de production du CFAPC](#environnements-dessai-et-de-production-du-cfapc) |Clarifications sur les mises à l’essai |
| | |[Réponses aux messages XFNM](#réponses-aux-messages-xfnm) |Mise à jour de la définition du INVALID_HOUSE_BILL_NBR |
| | |[Messages de rapport d’erreur préliminaire (PER)](#messages-de-rapport-derreur-préliminaire-per) |Mise à jour de la définition du INVALID_HOUSE_BILL_NBR et des messages d’erreur CAMIR PER |
| | |Nouvelle section 6 sur les descriptions des marchandises |Exemples de descriptions de marchandises acceptables et inacceptables afin d’éviter des erreurs de données insuffisantes |
| 6 mai 2024 |     1.2    | [Mise à l’essai de la présentation des données](#présentation)          | Mise à jour de la section afin de fournir des paramètres sur l'analyse des données soumises |


# <a name="aperçu"></a>Aperçu

Le programme de ciblage du fret aérien préalable au chargement (CFAPC) vise à cerner et à prendre des mesures d’atténuation en ce qui concerne les expéditions de fret aérien à haut risque susceptibles de contenir des engins explosifs improvisés camouflés avant leur chargement et leur départ pour le Canada. Pour ce faire, on procède à l’évaluation des risques des renseignements avancés sur le fret à l’aide de technologies émergentes.

À compter de l’automne 2024, les transporteurs aériens qui transportent du fret au Canada au départ de destinations internationales seront tenus de présenter des données au CFAPC et, dans certains cas, de prendre des mesures d’atténuation des risques à l’égard d’envois particuliers conformément au *Règlement canadien de 2012 sur la sûreté aérienne*.

## <a name="contexte"></a>Contexte

Transports Canada collabore avec des experts du secteur de l’aéronautique afin de trouver une solution pouvant facilement s’intégrer aux processus opérationnels existants. Ces bénévoles ont collaboré de près avec Transports Canada pour harmoniser au maximum la présentation de données au CFAPC.

Pour plus de renseignements sur le CFAPC, consultez l’adresse <https://tc.canada.ca/fr/programmes/ciblage-fret-aerien-prealable-chargement-CFAPC>.

## <a name="portée"></a>Portée

Le *Règlement canadien de 2012 sur la sûreté aérienne* s’applique aux transporteurs aériens qui transportent du fret à bord d’un vol au départ d’un lieu situé à l’extérieur du Canada à destination d’un aérodrome situé au Canada. Cela comprend le fret à bord des vols passagers, d’affrètement, de messageries/express et ne transportant que du fret, ainsi que les vols en transit ou transférant au Canada (y compris le fret restant à bord (FRAB)).

Le règlement et, par conséquent, le programme CFAPC ne s’appliquent **<u>PAS</u>** à ce qui suit :

- Courrier

- Valises diplomatiques ou consulaires

- Bagages enregistrés des passagers

- Bagages à main des passagers

- Fret aérien transporté à bord d’un vol au départ du Canada

- Fret aérien à bord de vols à l’intérieur du Canada

- Fret qui arrive au Canada par un autre moyen de transport, comme la route, la mer ou le rail (y compris lorsque le dernier segment d’un vol est acheminé par mode routier).

## <a name="public-visé"></a>Public visé

Ce guide s’adresse à l’équipe de mise en œuvre ou au technicien chargé de configurer la connexion des données d’un transporteur aérien au programme CFAPC. Ce guide comprend également des exigences concernant le présentateur et la présentation des données, les dates estimatives d’entrée en vigueur des règlements et l’agencement des messageries bidirectionnelles.

## <a name="participants-nécessaires-et-admissibles"></a>Participants nécessaires et admissibles

### <a name="participants-nécessaires-transporteurs-aériens"></a>Participants nécessaires (transporteurs aériens)

Les transporteurs aériens qui transportent du fret à bord d’un vol depuis un lieu situé en dehors du Canada jusqu’à un aérodrome situé au Canada sont tenus de présenter les renseignements obligatoires sur le fret au CFAPC. Voir la section [Portée](#portée).

### <a name="participants-admissibles-autres-présentateurs-de-données"></a>Participants admissibles (autres présentateurs de données)

Les entreprises recrutées par les transporteurs aériens pour fournir des services de TI peuvent participer au programme CFAPC en soumettant et en recevant des données sur le fret au nom du transporteur aérien. Cela comprend les fournisseurs de services tiers, comme les agrégateurs de données et les agents généraux des ventes/de manutention (AGV/AGM).

Les transitaires ou les transporteurs aériens qui établissent des lettres de transport ou qui exploitent des vols avant le dernier point de départ pour le Canada (p. ex., les accords de partage de codes) peuvent également participer au CFAPC à titre volontaire, **<u>à la demande d’un transporteur aérien</u>**.

Au moment de leur inscription au CFAPC, les transporteurs aériens doivent préciser leurs fournisseurs de services afin d’autoriser la connexion de leurs partenaires au sein de la chaîne d’approvisionnement au système CFAPC.

**Remarque :** Même si les transporteurs aériens peuvent déléguer l’échange de renseignements à un fournisseur de services, ce sont les transporteurs aériens qui sont en définitive responsables de se conformer au *Règlement canadien de 2012 sur la sûreté aérienne*.

## <a name="points-de-contact-réglementaires"></a>Points de contact réglementaires

Transports Canada exige que les points de contact suivants inscrivent un transporteur aérien au CFAPC avant d’amorcer le processus de chargement. Voir la section [Inscription](#inscription) pour plus de précisions.

1.  **Principale personne-ressource responsable de la sûreté du fret :** Il s’agit d’un représentant de la compagnie qui est responsable du respect des règles et règlements de Transports Canada.

- Nom :

- Titre :

- N<sup>o</sup> de téléphone :

- Courriel :

2.  **Contact 24 heures sur 24, 7 jours sur 7 :** Une personne-ressource disponible 24 jours sur 24, 7 jours sur 7, qui peut répondre d’urgence aux demandes de renseignements (RFI), aux demandes de contrôle (RFS) et aux avis Ne pas charger (DNL). Cette personne doit avoir accès aux renseignements complémentaires sur l’envoi et être en mesure d’amorcer des procédures de contrôle face à une éventuelle menace planant sur le fret aérien. Cette personne peut être une boîte de réception dans la mesure où celle‑ci fait l’objet d’une surveillance 24 jours sur 24, 7 jours sur 7.

- Nom :

- Titre :

- N<sup>o</sup> de téléphone :

- Courriel :

3.  **Interlocuteur technique :** Interlocuteur qui peut amorcer la connectivité du système entre le transporteur aérien et Transports Canada et apporter une aide technique pour l’échange de données, notamment intervenir en cas de panne du système.

- Nom :

- Entreprise (si elle diffère du transporteur aérien) :

- Titre :

- N<sup>o</sup> de téléphone :

- Courriel :

## <a name="date-dentrée-en-vigueur"></a>Date d’entrée en vigueur

Les modifications du *Règlement canadien de 2012 sur la sûreté aérienne* entreront en vigueur lors de leur publication dans la partie II de la *Gazette du Canada*, à l’automne 2024. On escompte des transporteurs aériens qu’ils présentent les éléments de données prescrits au CFAPC et qu’ils soient prêts à répondre aux demandes de Transports Canada (RFI, RFS, DNL) à compter de la date de publication, à défaut de quoi ils sont susceptibles de faire l’objet de sanctions administratives pécuniaires (SAP).

Depuis l’automne 2023, Transports Canada s’est mis à inscrire certains transporteurs aériens et entend augmenter leur volume progressivement, jusqu’à la date d’entrée en vigueur du Règlement. L’objectif est de s’assurer que les modifications d’ordre technique et opérationnel peuvent être mises à l’épreuve et en œuvre bien avant la date d’entrée en vigueur.

# <a name="connexion-au-programme-cfapc"></a>Connexion au programme CFAPC

Le programme CFAPC utilise une interface de protocole d’application Web (« API Web ») afin d’expédier des messages aux participants et d’en recevoir de leur part en format XML-Cargo, ou C‑IMP/CAMIR. Vous trouverez plus de précisions à la section [Formats des messages](#formats-des-messages) et à la section [Versions prises en charge des messages CFAPC](#versions-prises-en-charge-des-messages-du-cfapc).

Cette section donne un aperçu du processus d’inscription technique et fournit les précisions nécessaires à l’agencement, à la connexion et à la mise à l’essai des données présentées au CFAPC.

## <a name="diagramme-de-ciblage-du-cfapc"></a>Diagramme de ciblage du CFAPC

Le [Diagramme du ciblage du CFAPC](#diagramme-du-ciblage-du-cfapc) illustre le flux prévu des informations du système de production.

Les participants doivent apprendre à connaître les avis qu’ils peuvent s’attendre à recevoir via le programme CFAPC plutôt que par courriel. Dans le cas où une mesure d’atténuation des risques s’avère nécessaire, le programme CFAPC est capable d’envoyer des messages bidirectionnels pour transmettre les RFI, RFS et DNL en temps quasi réel. Voir section [Messageries bidirectionnelles](#messages-bidirectionnels) pour plus de précisions.

## <a name="inscription-au-cfapc"></a>Inscription au CFAPC

Avant de présenter des données au CFAPC, les transporteurs aériens doivent s’adresser à Transports Canada pour une procédure unique d’inscription et d’agencement, laquelle consiste à identifier les personnes-ressources et à fournir les autorisations pour toute personne tierce qui doit présenter des données au CFAPC au nom du transporteur aérien, le cas échéant.

Une fois l’inscription terminée, l’équipe du CFAPC entrera en rapport avec le transporteur aérien ou son participant autorisé pour lui fournir les renseignements de connexion suivants :

- Un symbole d’authentification

- L’URL d’extrémité pour l’environnement d’essai du CFAPC

- Les consignes de connexion, notamment les informations d’en‑tête prescrites

### <a name="inscription"></a>Inscription

Pour amorcer le processus d’inscription, veuillez entrer en rapport avec Transports Canada à l’adresse <pact-information-cfapc@tc.gc.ca> et préciser les personnes-ressources figurant à la section [Points de contact réglementaires](#points-de-contact-réglementaires). Un représentant du CFAPC répondra dans les deux (2) jours ouvrables pour obtenir d’autres renseignements et finaliser l’inscription.

**Remarque :** Il est vivement conseillé aux transporteurs aériens de mener à bien ce processus le plus rapidement possible pour qu’ils aient suffisamment de temps pour mettre à l’épreuve avec succès les données qu’ils présentent avant que la conformité ne devienne obligatoire à l’automne 2024.

### <a name="configuration-initiale-et-connexion"></a>Configuration initiale et connexion

Une fois l’inscription faite, un représentant du CFAPC enverra un courriel à la personne-ressource technique pour lui fournir tous les renseignements nécessaires sur la connexion. Cela comprend un symbole pour l’authentification, l’URL et des renseignements sur la façon d’établir des connexions pour recevoir des messages de l’API Web du CFAPC.

Après s’être branché avec succès au programme CFAPC, un message synchrone standard est immédiatement expédié par le programme CFAPC pour indiquer que la présentation des données a bien été reçue, mais qu’elle n’a pas encore fait l’objet d’une évaluation sur le plan des risques. Ces messages précisent les erreurs d’interprétation et de format et peuvent également indiquer s’il manque un élément de donnée obligatoire.

Ces messages d’accusé de réception et d’erreurs synchrones sont distincts des messages bidirectionnels asynchrones que l’on peut activer pour les avis « d’évaluation terminée » et les mesures d’atténuation des risques. Voir la section 2.2.3 Messages bidirectionnels.

### <a name="messages-bidirectionnels"></a>Messages bidirectionnels

Les messages bidirectionnels sont disponibles sur l’API Web pour que les participants reçoivent l’avis « évaluation terminée » et des mises à jour sur l’état d’atténuation des risques de manière asynchrone par le biais de leur solution logicielle. Si une mesure d’atténuation s’avère nécessaire, la mise à jour de la situation est suivie d’un courriel.

**Remarque :** Si les participants ne sont pas en mesure d’établir des messages bidirectionnels, des messages d’accusé de réception synchrones peuvent être renvoyés en guise de réponse aux appels de l’API. Toutes les réponses d’atténuation après l’accusé de réception initial seront ensuite envoyées aux personnes-ressources uniquement par courriel.

Pour se brancher à l’API d’un participant, Transports Canada a besoin des renseignements suivants :

- Des précisions sur la connexion API (le CFAPC peut être connecté à des terminaux multiples).

- Le format de message préféré (Cargo-XML ou C‑IMP) et sa version (voir section [Versions prises en charge des messages du CFAPC](#versions-prises-en-charge-des-messages-du-cfapc)).

**Remarque :** On peut sélectionner différents formats pour la présentation et la réception.

- Toutes exigences supplémentaires pour la connexion, le cas échéant.

Après avoir confirmé les données sur la connexion, l’équipe du CFAPC envoie aux équipes de mise en œuvre les renseignements prescrits pour recevoir des messages asynchrones du CFAPC. Les messages asynchrones exigent la configuration de webhook pour être reçus du serveur du CFAPC.

### <a name="configuration-des-webhook"></a>Configuration des webhook

Les messages bidirectionnels exigent la configuration de solutions logicielles intégrées pour recevoir une connexion webhook du serveur du CFAPC à l’aide des éléments suivants :

|Élément	 |Définition | Exemple|
|:---|:---- |:---- |
|URL | Le périphérique du transporteur aérien auquel le CFAPC enverra des messages.	|https:\//myaircarrier.com/api/myendpoint |
|Secret |Une chaîne configurée par le transporteur aérien qui sera annexée à chaque message de réponse dans l’en‑tête « X‑PACT-SECRET » pour permettre au transporteur aérien de confirmer que le message a bien été reçu du programme CFAPC. |E6HuaaHIB6knkFyaTuUc934SRz37czVJGDM7rBtvKN5AhfWcCP9LRVF0LWx9c17LvWADfhXXbFa2iwSSKP8cuDyOnX9NDG64l5icklhXgw3fzQ6IT0suzZSZFrzPfrzfTcSbjh3gwlP7FEFF4uJdMrkjLxFDejKUV9kjYNR0DOQjWujD7I0K9AW1nR314SuCeEoOyIfV.......... |
|Type de réponse	 |	Le verbe http qui désigne la mesure relative aux données transmises comme la création ou la mise à jour.|POST, PUT | | |
|En‑tête	 |Une liste des principales paires de clé – valeur ajoutées aux demandes/réponses qui fournissent des renseignements complémentaires. |« X-MYAIRLINE-REQUIRED-HEADER » : « Custom provided header »;  Pour les messages de type texte (FWB, FHL) « Content-Type » : « text/plain »; Pour les messages de type XML (XFMB, XFZB) « Content-Type » : « application/xml »;  |



### <a name="exigences-de-présentation-et-réponses"></a>Exigences de présentation et réponses

Les participants doivent soumettre les données prescrites au CFAPC le plus tôt possible avant le chargement afin de permettre de mener à bien la procédure d’évaluation des risques. Consulter le [Diagramme du ciblage du CFAPC](#diagramme-du-ciblage-du-cfapc).

Les participants reçoivent une série de messages du programme CFAPC qui précisent l’état de l’évaluation de chaque ensemble de données, notamment l’identification des erreurs, la confirmation des messages reçus, les avis « d’évaluation terminée », les demandes de mesures d’atténuation des risques et les avis de résolution des mesures. Tous les avis du système sont transmis en temps quasi réel lorsque les messages bidirectionnels sont activés.

#### <a name="elements-de-données-du-CFAPC"></a>Éléments de données du CFAPC

Le CFAPC exige sept (7) éléments de données et un numéro de lettre de transport aérien (+1) afin de procéder à l’évaluation des risques de tout le fret aérien entrant. Ces éléments de données « 7+1 » sont reconnus à l’échelle internationale comme concept d’utilisation des renseignements préalables sur le fret (PLACI), et on les estime utiles à l’évaluation des risques, car il est possible de les obtenir au début du cycle de vie d’expédition du fret et que pris ensemble, ils peuvent révéler des tendances qui fixent des limites pour le fret à faible risque.

On s’attend de la part des participants à ce qu’ils soumettent les éléments de données au CFAPC le plus tôt possible avant le chargement et à ce qu’ils fournissent les mises à jour jusqu’au moment du départ du vol (signalé par la soumission des renseignements sur le vol énumérés ci-dessous). Aucune des données reçues après le départ ne sera évaluée.

Les transporteurs aériens sont tenus de soumettre les données obligatoires suivantes (7+1) au CFAPC pour procéder à l’évaluation des risques le plus tôt possible avant le chargement :

- Le numéro de lettre de transport aérien (qui comprend le numéro de connaissement interne, s’il y a lieu)

- Nom de l’expéditeur d’origine

- Adresse de l’expéditeur d’origine

- Nom du destinataire

- Adresse du destinataire

- La description du fret (description de chaque unité de fret)

- Le nombre total d’unités (dénombrement des unités)

- Le poids total du fret

Le programme CFAPC peut également accepter d’autres éléments de données sous réserve que les éléments réglementaires soient bien présents.

**Remarque :** Les messages de regroupement ne satisfont pas généralement à ces exigences car ceux-ci ne contiennent pas nécessairement les noms et les adresses des expéditeurs d’origine, ni la description de chaque unité de fret, auquel cas tous les connaissements internes connexes sont nécessaires. Bien que le système puisse accepter une description du fret telle que « regroupement », cette description ne satisfait pas aux exigences réglementaires.

**Remarque :** Le présentateur des données peut soumettre un connaissement interne avant de connaître le numéro du connaissement aérien principal et peut laisser ce dernier en blanc (p. ex., lorsque c’est un transitaire qui présente les données sur le connaissement interne pour le transporteur aérien). Une fois connu le numéro du connaissement aérien principal, le connaissement interne doit être présenté à nouveau par le transporteur aérien ou le transitaire avec le numéro du connaissement aérien principal avant le départ. Ce sont les transporteurs aériens qui demeurent responsables de se conformer aux exigences réglementaires sur toutes les données à soumettre (y compris lorsque ces données sont présentées par d’autres participants).

En plus des éléments de données « 7+1 », le programme CFAPC demande aussi que les renseignements suivants soient fournis dès que possible après le départ du vol à partir du dernier point de départ et avant son arrivée au Canada :

- La date du vol;

- Le numéro du vol;

- L’aérodrome de destination;

- L’heure de départ; et

- La liste des numéros des lettres de transport aérien du vol.

**Remarque :** le message FFM répond à ces exigences. Le programme CFAPC acceptera l’heure de soumission du message FFM comme étant équivalente à l’heure de départ.

#### <a name="données"></a>Données d’en‑tête à transmettre

Les données d’en‑tête qui doivent accompagner chaque message envoyé doivent inclure : le symbole, le code de transporteur aérien de l’IATA, et l’identifiant de la partie responsable (au maximum 50 caractères), le cas échéant.

Voici un exemple d’en‑tête valide :

- Ocp-Apim-Subscription-Key: abcd

- Code de transporteur aérien de l’IATA : 014

- Partie responsable : PACTPW8 (facultatif)

- Accepté : texte/simple

- Type de contenu : texte/simple

- Contenu-longueur : 767

- Agent utilisateur : PACTAI/1.0

Le tableau qui suit contient les données d’en‑tête prescrites et facultatives relatives aux demandes du CFAPC, ainsi que les consignes sur la façon de remplir chaque champ.

|Données d’en-tête |Description |
|:---|:---- |
|**Ocp-Apim-Subscription-Key**	 |Contient le logiciel qui vous a été remis par un représentant du CFAPC au moment de l’inscription.| 
|**Code du transporteur aérien de l’IATA** |	Le code à trois chiffres de l’IATA du transporteur aérien qui présente les données. Référence : https://www.iata.org/en/about/members/airline-list/ ou https://www.iata.org/en/publications/store/airline-coding-directory/ | 
|**Partie responsable** \<facultatif>	 |Code à sept chiffres qui identifie la partie responsable de la réception et de la réponse aux avis d’atténuation des risques, selon le présentateur des données. Voir [Partie responsable](#partie-responsable) pour plus de précisions | 
|**Accepté** |	Référence : https://www.rfc-editor.org/rfc/rfc9110.html#name-accept; application/xml pour le fret-XML ou texte/simple pour le C‑IMP | 
|**Type de contenu** |Référence : https://www.rfc-editor.org/rfc/rfc9110.html#name-content-type; application/xml pour le fret-XML ou texte/simple pour le C‑IMP |
|**Longueur du contenu** |Référence : https://www.rfc-editor.org/rfc/rfc9110.html#name-content-length. Taille de la demande |
|**Agent utilisateur** |Référence : https://www.rfc-editor.org/rfc/rfc9110.html#name-user-agent; Contient un renvoi au produit/au commentaire décrivant l’application d’où provient la demande |



#### <a name="partie-responsable"></a>Partie responsable

La valeur de l’en‑tête de la partie responsable est un code à sept (7) chiffres qui précise quelle partie recevra les avis d’atténuation de tous les risques émis par le CFAPC et qui y répondra. Si le présentateur des données reçoit également et réagit à toutes les mesures d’atténuation des risques, on peut alors laisser en blanc la valeur de la partie responsable. Cela vaut pour de nombreux transporteurs aériens et transitaires qui s’occupent eux-mêmes des RFI/RFS/DNL.

Pour les agrégateurs de données et toute autre partie qui présente des données au CFAPC au nom d’un transporteur aérien, mais qui ne s’occupe pas de la gestion des mesures d’atténuation des risques, le code de la partie responsable doit préciser la partie responsable.

Le code de la partie responsable doit contenir sept (7) chiffres et comporter les données suivantes :

- Les cinq premières lettres sont toujours CFAPC

- Une seule lettre pour désigner l’environnement du CFAPC :

- un « **P** » pour indiquer l’environnement de production

- un « **E** » pour l’environnement d’essai

- L’indicatif à deux caractères du transporteur aérien de l’IATA (ou le code convenu à deux caractères qui désigne les organismes en dehors de l’IATA, comme les AGV)

Par exemple : **PACTPW8**

**Remarque :** Un représentant du CFAPC précisera à quel environnement le symbole est destiné au moment où il est fourni, pour que le technicien puisse saisir la bonne lettre (P ou E).

#### <a name="types-de-réponses"></a>Types de réponses

À l’aide du [Diagramme du ciblage du CFAPC](#diagramme-du-ciblage-du-cfapc), cette section explique les divers codes de réponses que transmettra le programme CFAPC.

Une fois que l’on reçoit un message du programme CFAPC, on procède à la validation préliminaire des données pour déterminer les erreurs dans les éléments de données « 7+1 », le cas échéant. Ces erreurs peuvent être le reflet d’une demande https mal formatée, des erreurs d’authentification, des problèmes de serveur ou des données de présentation mal formatées. Les codes d’erreur se trouvent dans les [Réponses aux messages XFNM](#réponses-aux-messages-xfnm), les [Messages de rapport d’erreur préliminaire (PER)](#messages-de-rapport-derreur-préliminaire-per) et les sections des [Codes de réponse HTTP](#codes-de-réponse-http).

Quand un message est reçu sans erreurs, un avis « reçu » est envoyé en guise de réponse pour indiquer que les éléments de données « 7+1 » ont bien été reçus par Transports Canada.

Après avoir soumis les données obligatoires pour qu’elles fassent l’objet d’une évaluation, le CFAPC procède à une évaluation des risques pour chaque lettre de transport aérien. Si les données sur la lettre de transport aérien ne contiennent aucun indicateur de risque, le CFAPC transmet aux participants un code qui contient le statut « Évaluation terminée ».

Au cas où les données d’envoi contiendraient des indicateurs de risque, le CFAPC peut alors transmettre des codes pour refléter une RFI, un RFS ou un DNL. Les équipes de mise en œuvre doivent s’assurer que les scénarios d’essai comportent des mesures pour manipuler les codes dans le type de format sélectionné :

- Pour C-XML, qui comprend les codes DL, DV et CD. Voir [Messages d’avis de statut XCSN](#messages-davis-de-statut-xcsn).

- Pour le CAMIR/C-IMP, qui comprend les codes 7H, 7I, 7J, 8H, 8I, 8J, 6H, 6J, et 6I. Voir [Messages d’avis de statut préliminaire (PSN)](#messages-davis-de-statut-préliminaire-psn).

**Remarque** : Tous les messages du CFAPC contiennent un identifiant de conversation (corps CXML) et/ou un identifiant de corrélation (en‑tête http CXML/CIMP) à titre de référence.

## <a name="environnements-dessai-et-de-production-du-cfapc"></a>Environnements d’essai et de production du CFAPC 

Transports Canada propose deux environnements dans le programme CFAPC pour soumettre des données : un environnement d’essai et un environnement de production.

L’environnement d’essai permet aux participants de vérifier les données qu’ils soumettent et de recevoir des réponses du CFAPC dans un espace simulé qui n’affectera pas leurs activités effectives.

L’environnement de production est celui qui offre la plus grande stabilité et le meilleur rendement et il est mis à la disposition des participants dès qu’ils ont procédé avec succès aux essais dans l’environnement d’essai. Lorsque des données réelles sont fournies dans l’environnement de production, le CFAPC aura l’occasion de mieux connaître les données sur le transporteur aérien et de cerner les problèmes de conformité longtemps avant la date d’entrée en vigueur.

### <a name="environnement-dessai-du-cfapc"></a>Environnement d’essai du CFAPC

Avant de soumettre des données à l’environnement de production du CFAPC, les participants sont tenus de tester leur connectivité et le formatage des messages dans l’environnement d’essai du CFAPC. Après l’inscription, les participants se voient remettre un symbole d’authentification, une URL d’extrémité et des renseignements sur la façon de configurer les connexions pour recevoir des messages depuis l’environnement de production du CFAPC.

Une fois qu’ils ont testé une quantité satisfaisante de types de messages, de volumes et d’erreurs, les participants sont invités à soumettre toutes les données courantes à destination du Canada dans l’environnement d’essai.

#### <a name="présentation"></a>Mise à l’essai de la présentation des données 

Les essais dans l’environnement d’essai doivent débuter par un ou deux lots de 20 à 100 données présentées, en utilisant des données aussi proches que possible du « monde réel ». Ces lots serviront à évaluer la capacité du participant à transmettre les données de la lettre de transport au CFAPC et à recevoir des messages d’accusé de réception synchrones ou des erreurs en guise de réponse. Les données soumises seront examinées par un représentant du CFAPC qui vérifiera les éléments suivants:

Fournir tous les éléments de données « 7+1 » afin de recevoir le message d'accusé de réception :
- Numéro de lettre de transport aérien
- Nom et adresse de l’expéditeur d’origine 
- Nom et adresse du destinataire 
- Description de chaque unité de fret
- Nombre total d’unités 
- Poids total du fret

Fournir au moins un de chacun des messages d'essai suivants :
- Connaissement principal (FWB)
- Connaissement interne (FHL)
- Lettre de transport avec poids manquant pour tester les messages d'erreur
- Lettre de transport avec une description des marchandises conformément à la section 6.2 Descriptions de marchandises inacceptables pour tester les messages d'erreur

Le participant sera avisé par le CFAPC s’il y a des problèmes qu’il faut résoudre ou s’il doit soumettre d’autres données d’essai.


#### <a name="mise-à-lessai"></a>Mise à l’essai des procédures d’atténuation des risques (RFI, RFS et DNL)

Après avoir testé avec succès les données présentées, le participant est tenu de procéder à un essai de ses procédures d’atténuation des risques. En plus de l’échange de données, cet essai a pour but de simuler les diverses procédures qui seront mises en place des deux côtés au cas où un envoi présenterait un risque. Cela exige la présence d’un représentant du CFAPC et des personnes-ressources techniques du participant 24 heures sur 24, 7 jours sur 7 (et vraisemblablement de l’agent principal de sûreté du fret dans le cas d’une RFS ou d’un DNL) afin de le prévoir longtemps à l’avance.

L’environnement d’essai du CFAPC adressera alors aux participants un code RFI renvoyant à un envoi particulier et le représentant du CFAPC enverra un courriel d’essai au contact 24/7 en utilisant le modèle de RFI. Le contact 24/7 du participant doit répondre au courriel en fournissant des renseignements complémentaires sur l’envoi, après quoi l’équipe du CFAPC répondra par courriel et présentera un code « RFI résolue ».

Le même processus sera simulé avec un RFS et un DNL. Dans tous les cas, il est vivement conseillé au participant de renvoyer des données réelles dans les modèles réels utilisés, le cas échéant. Par exemple, une RFI peut demander une Déclaration de sûreté de l’envoi (DSE) et/ou un bordereau d’expédition; alors qu’une RFS sollicite un registre de contrôle comportant des renseignements précis stipulés dans le règlement. D’autres directives sont fournies durant la planification de l’essai.

Après un essai fructueux des procédures d’atténuation des risques, le participant sera autorisé à passer au système de production du CFAPC. Durant cette période, les représentants du CFAPC collaboreront avec les participants à la résolution des problèmes techniques qui pourraient survenir durant le passage à l’environnement de production.

**Remarque :** L’environnement d’essai du CFAPC ne bénéficie pas d’un appui 24 heures sur 24.

### <a name="environnement-de-production-du-cfapc"></a>Environnement de production du CFAPC

Après suffisamment d’essais dans l’environnement d’essai du CFAPC et l’approbation d’un représentant du CFAPC de Transports Canada, les participants passeront à l’environnement de production du CFAPC. Il est prévu que les participants commencent à travailler dans cet environnement au plus tard à l’automne 2024.

#### <a name="soutien-du-cfapc"></a>Soutien du CFAPC

Transports Canada a adopté et appuie les systèmes de sécurité essentiels inhérents à un environnement de production qui permettent au CFAPC de fonctionner 24 heures sur 24, 7 jours sur 7. Dans le cas inhabituel où le CFAPC connaîtrait une panne inopinée, Transports Canada avertira les participants lorsqu’une panne est confirmée en leur fournissant d’autres directives. Durant une panne, les participants doivent continuer de présenter des données au CFAPC.

Si vous éprouvez des problèmes à vous connecter au CFAPC, veuillez vous adresser au soutien du CFAPC à l’adresse <pact-information-cfapc@tc.gc.ca>.

#### <a name="procédures"></a>Procédures d’atténuation des risques (RFI, RFS et DNL)

Si les renseignements fournis ne permettent pas de procéder à l’évaluation des risques d’un envoi, ou qu’il y a suffisamment de données menaçantes qui justifient une RFS ou un DNL, l’environnement de production du CFAPC enverra au participant un code RFI/RFS/DNL renvoyant à un envoi particulier et un représentant du CFAPC fera le suivi au moyen d’un courriel auprès d’un contact présent 24 heures sur 24, 7 jours sur 7 contenant d’autres directives.

Si d’autres mises à jour ou présentations en double sont transmises au CFAPC après l’envoi du code d’atténuation des risques, d’autres messages de réponse seront expédiés en précisant qu’une « retenue » s’impose jusqu’à ce qu’on ait reçu et évalué la réponse par courriel. Si la réponse par courriel est satisfaisante, le représentant du CFAPC répondra par un courriel de confirmation et un message généré par le système sera expédié pour lever la « retenue ». Toutes les transmissions suivantes seront marquées du statut SF ou CO, selon le format du message de réponse.

Si de multiples participants à la chaîne d’approvisionnement ont déjà envoyé au CFAPC un message sur cet envoi précis, toutes les personnes-ressources connexes en seront averties (messages et courriels de statut).

**Remarque :** Jusqu’à ce que la « retenue » soit levée, il est interdit au transporteur aérien de transporter le fret à destination du Canada.

# <a name="caractéristiques-des-messages-du-cfapc"></a>Caractéristiques des messages du CFAPC

## <a name="formats-des-messages"></a>Formats des messages

Le programme CFAPC expédie et reçoit des messages en utilisant les formats Cargo-XML et CAMIR/C-IMP. Vous trouverez l’appui de ces types de messages à l’adresse :

<https://www.iata.org/en/publications/store/cargo-xml-toolkit/>

 | Type de messages Cargo-XML  |Type de messages C‑IMP   | Type de messages CAMIR |Description  | Auteur/origine |
|:-----| :-----  |:-----  |:-----  |:-----  |
|XFFM |FFM | | Renseignements sur le manifeste de vol|Transporteurs aériens/ présentateurs de données |
|XFWB |FWB | |Renseignements sur le connaissement aérien principal |Transporteurs aériens/ présentateurs de données/transitaires de fret |
|XFZB |FHL | | Renseignements sur le connaissement interne| Transporteurs aériens/ présentateurs de données/transitaires de fret|
|XFNM | |PER (erreur); PSN (accusé de réception |Notification des erreurs de présentation et des accusés de réception |CFAPC |
|XCSN | |PSN | 	Notification d’une « évaluation terminée » ou de la prise ou de la clôture d’une mesure d’atténuation des risques (RFI, RFS, DNL)|CFAPC |
 
 
## <a name="versions-prises-en-charge-des-messages-du-cfapc"></a>Versions prises en charge des messages du CFAPC

Le système CFAPC envoie et reçoit les messages Cargo-XML et CAMIR/C-IMP en fonction des versions suivantes :

### <a name="versions-cargo-xml-prises-en-charge"></a>Versions Cargo-XML prises en charge

|Type de messages Cargo-XML	 |Versions acceptées |
|:---|:---- |
|XFFM |Version 2.00, Version 3.00 |
|XFWB |Version 3.00 |
|XFZB | Version 3.00|
|XCSN |Version 1.00 |
|XFNM |Version 3.00 |


### <a name="versions-c-imp-prises-en-charge"></a>Versions C-IMP prises en charge

|Type de messages C-IMP |Versions acceptées |
|:---|:---- |
|FFM | Version 7, Version 8 |
|FHL |Version 4, Version 5 |
| FWB|Version 16 Version 17 |

**Remarque** :  Chaque ligne d'un message « C-IMP » ne peut pas comporter plus de 69 caractères. Si un message « C-IMP » dépasse 1600 octets, il doit être divisé en deux messages ou plus.

### <a name="versions-camir-prises-en-charge"></a>Versions CAMIR prises en charge

|Type de messages CAMIR |Versions |
|:---|:---- |
|CAMIR | Version 1 |



## <a name="réponses-aux-messages-cargo-xml"></a>Réponses aux messages Cargo-XML

Les sections qui suivent font état des réponses aux messages Cargo-XML.

### <a name="réponses-aux-messages-xfnm"></a>Réponses aux messages XFNM

Ce type de message expédie des réponses d’erreur et d’accusé de réception depuis le programme CFAPC, telles que soulignées dans le tableau suivant

|Code de message de réponse	 |Définition |Exemple |
|:---|:---- |:---|
|Accusé de réception	 |	Accusé de réception du message reçu sans erreurs | \<ram:ConditionCode>Acknowledgement</ram:ConditionCode>|
| | |\<ram:Reason>No Errors</ram:Reason>|
|MISSING_WBL_LINE	 |Numéro manquant du connaissement principal	 | \<ram:ConditionCode>Error</ram:ConditionCode>|
| | |\<ram:Reason>MISSING_WBL_LINE</ram:Reason>|
|MISSING_HOUSE_BILL_NBR	 |Numéro manquant du connaissement interne |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>MISSING_HOUSE_BILL_NBR</ram:Reason> |
|INVALID_HOUSE_BILL_NBR |	Le numéro du connaissement interne est inexact ou le numéro contient plus de 35 caractères	 |\<ram:ConditionCode>Error</ram:ConditionCode>|
| | | \<ram:Reason>MISSING_HOUSE_BILL_NBR</ram:Reason>|
|MISSING_CNE_ADDR |Adresse manquante du destinataire |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>MISSING_CNE_ADDR</ram:Reason> |
|MISSING_CNE_CTRY |Pays manquant du destinataire	 | \<ram:ConditionCode>Error</ram:ConditionCode>|
| | | \<ram:Reason>MISSING_CNE_CTRY</ram:Reason>|
|MISSING_CNE_NAME |Nom manquant du destinataire | \<ram:ConditionCode>Error</ram:ConditionCode>|
| | | \<ram:Reason>MISSING_CNE_NAME</ram:Reason>|
|MISSING_WEIGHT |Poids manquant du colis | \<ram:ConditionCode>Error</ram:ConditionCode>|
| | |\<ram:Reason>MISSING_WEIGHT</ram:Reason> |
|INVALID_WEIGHT |Le poids n’est pas un chiffre ou n’a pas pu être extrait |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>INVALID_WEIGHT</ram:Reason> |
|MISSING_BILL_QTY | Le nombre des pièces de fret du connaissement est manquant|\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>MISSING_BILL_QTY</ram:Reason> |
|INVALID_BILL_QTY |Le nombre des pièces de fret du connaissement n’est pas un chiffre ou n’a pas pu être extrait |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>INVALID_BILL_QTY</ram:Reason> |
|MISSING_SHP_ADDR |Adresse manquante de l’expéditeur |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | | \<ram:Reason>MISSING_SHP_ADDR</ram:Reason>|
|MISSING_SHP_CTRY | Pays manquant de l’expéditeur|\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>MISSING_SHP_CTRY</ram:Reason> |
|MISSING_SHP_NAME |Nom manquant de l’expéditeur	 |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>MISSING_SHP_NAME</ram:Reason> |
|MISSING_WT_UNITS | Unités de mesure manquantes des poids| \<ram:ConditionCode>Error</ram:ConditionCode>|
| | |\<ram:Reason>MISSING_WT_UNITS</ram:Reason> |
|INVALID_MESSAGE_TYPE	 |Il est possible de lire le message, mais on ne peut pas déterminer le type de message |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>INVALID_MESSAGE_TYPE</ram:Reason> |
|BAD_WBL_FORMAT |On n’a pas pu lire le message	 |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>BAD_WBL_FORMAT</ram:Reason> |
|MISSING_CSM_LINE |On n’a pas réussi à extraire les détails de l’envoi	 |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>MISSING_CSM_LINE</ram:Reason> |
|MISSING_CNE_LINE	 | On n’a pas réussi à extraire les détails du destinataire|\<ram:ConditionCode>Error</ram:ConditionCode> |
| | | \<ram:Reason>MISSING_CNE_LINE</ram:Reason>|
|MISSING_SHP_LINE |On n’a pas réussi à extraire les détails de l’expéditeur |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | | \<ram:Reason>MISSING_SHP_LINE</ram:Reason>|
|MISSING_CARGO_DESC |Description manquante du fret |\<ram:ConditionCode>Error</ram:ConditionCode> |
| | |\<ram:Reason>MISSING_CARGO_DESC</ram:Reason>|



##### Exemple XFNM—Message de réponse (erreur)

<img src="images/media/image2.png" style="width:6.25972in;height:5.74306in" alt="A screenshot of a computer code showing an error response from PACT in C-XML format." />


##### Exemple XFNM — Message de réponse (accusé de réception)

<img src="images/media/image3.png" style="width:6.17795in;height:5.62579in" alt="A screenshot of a computer code showing C-XML acknowledgement response from PACT." />


### <a name="messages-davis-de-statut-xcsn"></a>Messages d’avis de statut XCSN

Le type de message XCSN crée ou actualise un message d’avis de statut. Ce type de message contient l’un des codes de réponse suivants.


| Code de réponse Cargo-XML | Définition                                                                   | Exemple                                 |
|---------------------------|------------------------------------------------------------------------------|-----------------------------------------|
| CO                        | Évaluation terminée                                                          | \<ram:StatusCode\>CO\</ram:StatusCode\> |
| RI                        | Retenue de la demande de renseignements (RFI) émise ou actuellement en place | \<ram:StatusCode\>RI\</ram:StatusCode\> |
| CO                        | RFI résolue                                                                  | \<ram:StatusCode\>CO\</ram:StatusCode\> |
| RS                        | Demande de vérification (RFS) émise ou actuellement en place                 | \<ram:StatusCode\>RS\</ram:StatusCode\> |
| CO                        | RFS résolue – retenue levée                                                  | \<ram:StatusCode\>CO\</ram:StatusCode\> |
| CD                        | Ne pas charger (DNL) émis ou actuellement en place                           | \<ram:StatusCode\>CD\</ram:StatusCode\> |
| CO                        | DNL résolu                                                                   | \<ram:StatusCode\>CO\</ram:StatusCode\> |

##### Réponse CSN (RFI)

<img src="images/media/image4.jpeg" style="width:7.1966in;height:7.35652in" />

<img src="images/media/image5.jpeg" style="width:7.28505in;height:6.36522in" />


## <a name="réponses-aux-messages-camir"></a>Réponses aux messages CAMIR

La section qui suit souligne les réponses aux messages de format CAMIR.

### <a name="messages-de-rapport-derreur-préliminaire-per"></a>Messages de rapport d’erreur préliminaire (PER)

Ce type de message envoie les réponses d’erreur possible suivantes du programme CFAPC.


|Type de message de réponse	 |Explication |Exemple |
|:---|:---- |:---|
|MISSING_WBL_LINE |Numéro de connaissement principal manquant |**PER** 007-12345678-HAW0123456 ERR/MISSING_WBL_LINE |
|MISSING_HOUSE_BILL_NBR	 |Numéro de connaissement interne manquant|**PER** 007-54400194-HAW ERR/MISSING_HOUSE_BILL_NBR |
|INVALID_HOUSE_BILL_NBR |Numéro de connaissement interne inexact ou le numéro contient plus de 35 caractères |**PER** 007-12345678-HAW0123456 ERR/INVALID_HOUSE_BILL_NBR |
|MISSING_CNE_ADDR |Adresse manquante du destinataire | **PER** 007-12345678-HAW0123456 ERR/MISSING_CNE_ADDR|
|MISSING_CNE_CTRY	 |Pays manquant du destinataire | **PER** 007-12345678-HAW0123456 ERR/MISSING_CNE_CTRY|
|MISSING_CNE_NAME |Nom manquant du destinataire |**PER** 007-12345678-HAW0123456 ERR/MISSING_CNE_NAME |
|MISSING_WEIGHT	 |Poids manquant du colis |**PER** 007-12345678-HAW0123456 ERR/MISSING_WEIGHT|
|INVALID_WEIGHT	 |Le poids n’est pas un chiffre ou n’a pas pu être extrait |**PER** 007-12345678-HAW0123456 ERR/INVALID_WEIGHT |
|MISSING_BILL_QTY |Le nombre des pièces de fret du connaissement est absent	 |**PER** 007-12345678-HAW0123456 ERR/MISSING_BILL_QTY |
|INVALID_BILL_QTY |Le nombre des pièces de fret du connaissement n’est pas un chiffre ou n’a pas pu être extrait|**PER** 007-12345678-HAW0123456 ERR/INVALID_BILL_QTY |
|MISSING_SHP_ADDR |Adresse manquante de l’expéditeur |**PER** 007-12345678-HAW0123456 ERR/MISSING_SHP_ADDR |
|MISSING_SHP_CTRY	 |Pays manquant de l’expéditeur |**PER** 007-12345678-HAW0123456 ERR/MISSING_SHP_CTRY |
|MISSING_SHP_NAME |Nom manquant de l’expéditeur |**PER** 007-12345678-HAW0123456 ERR/MISSING_SHP_NAME |
|MISSING_WT_UNITS	 |Unités de mesure manquantes pour les poids |**PER** 007-12345678-HAW0123456 ERR/MISSING_WT_UNITS |
|INVALID_MESSAGE_TYPE |Possible de lire le message, mais on n’a pas pu déterminer le type de message	 |**PER** 007-12345678-HAW0123456 ERR/INVALID_MESSAGE_TYPE |
|BAD_WBL_FORMAT| On n’a pas réussi à lire le message|**PER** ERR/400/BAD_WBL_FORMAT |
|MISSING_CSM_LINE|On n’a pas réussi à extraire les précisions sur l’envoi |**PER** 007-12345678-HAW0123456 ERR/MISSING_CSM_LINE |
|MISSING_CNE_LINE |On n’a pas réussi à extraire les précisions sur le destinataire |**PER** 007-12345678-HAW0123456 ERR/MISSING_CNE_LINE |
|MISSING_SHP_LINE |On n’a pas réussi à extraire les précisions sur l’expéditeur	 |**PER** 007-12345678-HAW0123456 ERR/MISSING_SHP_LINE |
|MISSING_CARGO_DESC |Description manquante du fret |	**PER** 007-12345678-HAW0123456 ERR/MISSING_CARGO_DESC |



##### Exemple PER – Message de réponse (erreur)

<img src="images/media/image6.png" style="width:2.0625in;height:2.83333in" />


### <a name="messages-davis-de-statut-préliminaire-psn"></a>Messages d’avis de statut préliminaire (PSN)

Ce type de message envoie les réponses possibles suivantes sous format CAMIR du programme CFAPC.

| Message de réponse|Code du message de réponse	 | Exemple|
|:---|:---- |:---|
|Message reçu	 | SR|**PSN** 007-12345678-ABC1022506 CSN/SR/22NOV1902/NO ERRORS |
|Évaluation terminée	 |SF |**PSN** 007-12345678-ABC1022506 CSN/SF/22NOV1902/ASSESSMENT COMPLETE |
| RFI|7H |**PSN** 007-12345678- ABC31022506 CSN/7H/22NOV1902/PACT REQUEST FOR INFORMATION HOLD|
|RFI en place |7J	 |**PSN** 007-12345678- ABC31022506 CSN/7J/22NOV1902/PACT REQUEST FOR INFORMATION HOLD CURRENTLY IN PLACE |
|RFI résolue	 |7I |**PSN** 007-12345678- ABC31022506 CSN/7I/22NOV1902/PACT REQUEST FOR INFORMATION HOLD REMOVED |
|RFS |8H |**PSN** 007-12345678- ABC31022506 CSN/8H/22NOV1902/PACT REQUEST FOR SCREENING HOLD|
|RFS en place|8J |**PSN** 007-12345678- ABC31022506 CSN/8J/22NOV1902/PACT REQUEST FOR SCREENING HOLD CURRENTLY IN PLACE|
|RFS résolue |8I |**PSN** 007-12345678- ABC31022506 CSN/8I/22NOV1902/PACT REQUEST FOR SCREENING HOLD REMOVED |
|DNL |6H |**PSN** 007-12345678- ABC31022506 CSN/6H/22NOV1902/PACT DO NOT LOAD HOLD |
|DNL en place	 |6J |**PSN** 007-12345678- ABC31022506 CSN/6J/22NOV1902/PACT DO NOT LOAD HOLD CURRENTLY IN PLACE |
|DNL résolu |6I |**PSN** 007-12345678- ABC31022506 CSN/6I/22NOV1902/PACT DO NOT LOAD REMOVED |



### <a name="codes-de-réponse-http"></a>Codes de réponse HTTP

Le tableau qui suit souligne les codes de réponse HTTP normaux pris en charge par le CFAPC.


| Code HTTP | Définition                                                                                                                                                                                    |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 202       | Accepté. Le message a été accepté par Transports Canada.                                                                                                                                      |
| 422       | Le contenu ne peut pas être traité. La syntaxe du message est exacte, mais les renseignements que contient le message sont impossibles à traiter. Veuillez vérifier le contenu de la réponse. |
| 400       | Mauvaise demande. La transmission du message n’est pas prise en charge par Transports Canada.                                                                                                 |
| 401       | Non autorisé. Le symbole a expiré. Veuillez vous adresser à Transports Canada pour solliciter un nouveau symbole.                                                                             |
| 500       | Erreur de service interne. Impossible de traiter ce message. Veuillez essayer à nouveau ultérieurement.                                                                                       |
| 503       | Service non disponible. Le serveur de Transports Canada n’est pas disponible. Veuillez vous adresser à Transports Canada pour d’autres consignes.                                             |

## <a name="exemples-de-messages-du-cfapc"></a>Exemples de messages du CFAPC

Les messages suivants donnent des exemples de données présentées et de réponses escomptées à la fois en format Cargo-XML et CAMIR.

### <a name="exemple-de-présentation-dun-message-cargo-xml"></a>Exemple de présentation d’un message Cargo-XML

Les messages suivants sont des exemples d’un connaissement aérien principal et d’une réponse d’accusé de réception en format Cargo-XML.

##### Exemple de présentation d’un connaissement aérien principal

<img src="images/media/image7.png" style="width:6.25972in;height:7.66736in" alt="A screenshot of a computer code showing a submitted master air waybill in C-XML format-Part 1." />
<img src="images/media/image8.png" style="width:6.25972in;height:6.89861in" alt="A screenshot of a computer code showing a submitted master air waybill in C-XML format-Part 2." />
<img src="images/media/image9.png" style="width:6.25972in;height:6.97986in" alt="A screenshot of a computer code showing a submitted master air waybill in C-XML format-Part 3." />
<img src="images/media/image10.png" style="width:6.25972in;height:3.15833in" alt="A screenshot of a computer code showing a submitted master air waybill in C-XML format-Part 4." />


##### Réponse (accusé de réception – pas d’erreurs)

<img src="images/media/image11.png" style="width:5.43081in;height:4.05654in" alt="A screenshot of a computer code showing an application and error report response in C-XML format." />


##### Exemple du manifeste de vol

<img src="images/media/image12.jpeg" style="width:5.5in;height:5.01597in" /> 

<img src="images/media/image13.jpeg" style="width:5.5in;height:0.97292in" />

 

### <a name="exemple-de-présentation-dun-message-c-imp"></a>Exemple de présentation d’un message C-IMP

Les messages suivants sont des exemples : de connaissements principal et interne, d’une réponse d’accusé de réception et d’une réponse d’erreur, en format C-IMP et CAMIR. Le dernier exemple représente un message de type FFM d’un manifeste de vol, en format C-IMP.

##### Exemple de présentation d’un connaissement principal

<img src="images/media/image14.png" style="width:3.77409in;height:6.16029in" alt="A screenshot of a computer code showing an submitted house waybill in C-IMP." />

##### Exemple de réponse d’accusé de réception

<img src="images/media/image15.png" style="width:2.33333in;height:0.71875in" alt="A screenshot of a computer code showing a PSN response in C-IMP format." />

##### Exemple de présentation d’un connaissement interne comportant des erreurs

<img src="images/media/image16.png" style="width:4.02083in;height:3.60417in" alt="A screenshot of a computer code showing a house waybill with errors submission in C-IMP format." />

##### Exemple de réponse d’erreur

<img src="images/media/image17.png" style="width:2.09375in;height:0.72917in" alt="A screenshot of a computer code showing an error response in C-IMP format." />

##### Exemple de manifeste de vol

<img src="images/media/image18.png" style="width:4.02083in;height:3.01042in" /> 

# <a name="diagramme-du-ciblage-du-cfapc"></a>Diagramme du ciblage du CFAPC

<img src="images/media/image21.png" style="width:10.24342in;height:4.51824in" />

# <a name="glossaire"></a>Glossaire

|Abréviation/terme	 | Définition| 
|:---|:---- |
|API |Interface de programmation d’application |
|C-IMP	 | Procédures de message d’échange de fret. Protocole de message et norme créés par l’IATA.|
|Cargo-XML	 |Norme XML créée par l’IATA utilisée dans les communications électroniques. |
|CAMIR |Type de réponse du programme CFAPC (en réponse au C-IMP) |
|CSN/XCSN	 |Type de message de réponse à un avis de statut douanier |
|Data Submitter	 |Présentateur de données : l’entité qui présente les renseignements numériques de la lettre de transport au CFAPC. |
|DNL |Ne pas charger |
|FFM (C-IMP)/XFFM (Cargo-XML) |Message du manifeste de vol |
|AGV/AGM	 |Agent général des ventes/de manutention |
|HAWB, HAWB#	 |Connaissement aérien interne, numéro du connaissement aérien interne |
|IATA |Association du transport aérien international |
|LPD |Dernier point de départ. Dernière escale à l’itinéraire avant de partir à destination du Canada. |
| MAWB, MAWB#	| Connaissement aérien principal, numéro du connaissement aérien principal|
|CFAPC |Ciblage du fret aérien préalable au chargement |
|Participant au CFAPC	 |L’entité réglementée qui est tenue de participer au CFAPC. Il s’agit toujours du transporteur aérien qui exploite le vol entre le dernier point de départ avant d’arriver au Canada. |
|PER | Rapport d’erreur préliminaire. Réponse d’erreur du CFAPC en format C-IMP.|
|PSN |Avis de statut préliminaire. Réponse d’accusé de réception du CFAPC en format C-IMP. |
|RFI |Demande de renseignements |
|RFS |Demande de vérification |
|XFNM | Message de réponse envoyé en format Cargo-XML.|



# <a name="caractères-et-descriptions-inacceptables"></a>Caractères et descriptions inacceptables

La section suivante fournit des exemples de messages qui seront rejetés parce que les détails requis sont manquants.

Si des messages contenant de telles données inacceptables sont envoyés au CFAPC, une erreur description du fret manquante (MISSING_CARGO_DESC) de  données synchrone sera envoyée au présentateur et le message sera rejeté.

## <a name="caractères-inacceptables-dans-le-nom-ou-ladresse-de-lexpéditeurdu-destinataire-ou-dans-la-description-des-marchandises"></a>Caractères inacceptables dans le nom ou l’adresse de l’expéditeur/du destinataire ou dans la description des marchandises

Les caractères et chiffres suivants ne sont pas acceptés dans les champs de données suivants :

- Nom de l’expéditeur

- Adresse de l’expéditeur

- Nom du destinataire

- Adresse du destinataire

- Description des marchandises

| Caractères                                            | Définition                                                                                                  |
|-------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| 1004, 1005, etc. (chiffres)                           | Les descriptions qui ne contiennent que des chiffres ne sont pas acceptées.                                 |
| WPX. .wpx (extension de fichier)                      | Les descriptions qui ne contiennent que des extensions de fichiers ne sont pas acceptées.                   |
| XXX, … (trois symboles ou lettres identiques ou plus) | Les descriptions qui ne contiennent que trois symboles ou lettres identiques ou plus ne sont pas acceptées. |
| “.”, “-”, “ ” (caractères vides)                      | Les descriptions qui ne contiennent que des caractères vides ne sont pas acceptées.                         |
| \$%^&\<\>:”/\\?\* (caractères spéciaux)               | Les descriptions qui ne contiennent que des caractères spéciaux ne sont pas acceptées.                      |
| !£12 (caractères spéciaux et chiffres)                | Les descriptions qui ne contiennent que des caractères spéciaux et des chiffres ne sont pas acceptées.      |

## <a name="descriptions-de-marchandises-inacceptables"></a>Descriptions de marchandises inacceptables

La liste suivante donne des exemples de descriptions de marchandises qui ne sont pas suffisamment précises et qui seront rejetées par le CFAPC.

- Accessories

- All kind of cargo

- All kind of goods

- Articles

- AWB/HAWB

- Baggage

- Birthday gifts

- Bits

- Box

- Case

- Charity

- Collected items

- Commodity

- Company names

- Component

- Consumer

- Equipment, EQP

- Freight all kinds, FAK

- From UPU Postal

- Gift box

- Gifts

- Gizmos

- Goods, GDS

- Handling codes

- Invoice

- Joint shipping

- Label

- Line

- Likewise

- Mail

- Materials

- Merchandise, Merc.

- Miscellaneous products, Misc, Mixed, Mix

- Model

- None

- Odd parts

- Others

- Pad

- Package numbers

- Pallets, PLT

- Parcel

- Parts

- Personal address

- Personal effects

- Pieces, pces

- Pre-addressed parcel

- Private things

- Products

- Returned goods

- Said to contain, STC

- Sample

- Samples for analysis

- Scrap

- Several

- Several goods

- Souvenirs

- Spare

- Spare parts, SPPT

- Sporting goods

- Stuff

- Substance

- Test

- Things

- Toys

- Various

- Various goods

- Various products

- White goods
