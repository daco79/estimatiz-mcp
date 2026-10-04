# Estimatiz MCP

Obtenez une estimation immobilière de votre bien avec Estimatiz : sélectionnez son adresse, indiquez son type et sa surface. Vous recevez une fourchette de valeur en euros, avec les montants bas, médian et haut, ainsi que les données utilisées pour le calcul.

Un rapport est créé et enregistré pour vous permettre de consulter et de partager les résultats. Non indexable par les moteurs de recherche, il reste accessible à toute personne possédant son lien. Aucun nom, e-mail ou téléphone n’est requis.

## Serveur distant

- URL : `https://www.estimatiz.fr/api/mcp.php`
- Transport : Streamable HTTP
- Authentification : aucune
- Registre MCP officiel : `fr.estimatiz.www/estimatiz`
- Documentation : https://www.estimatiz.fr/api-documentation

## Outils

- `search_addresses` recherche les adresses connues d’Estimatiz. En cas de plusieurs résultats, l’utilisateur choisit son adresse.
- `estimate_property` calcule les montants bas, médian et haut, puis enregistre un rapport partageable non indexable.

L’estimation demande une adresse numérotée issue de `search_addresses`, le type du bien et sa surface. Le nombre de pièces est facultatif.

## Configuration MCP

Dans un client compatible avec les serveurs MCP distants, ajoutez un serveur HTTP nommé `estimatiz` avec cette URL :

```json
{
  "mcpServers": {
    "estimatiz": {
      "type": "http",
      "url": "https://www.estimatiz.fr/api/mcp.php"
    }
  }
}
```

La forme exacte de la configuration dépend du client. Consultez sa documentation pour l’ajout d’un serveur Streamable HTTP distant.

## API HTTP

Les applications qui n’utilisent pas MCP peuvent appeler directement l’API HTTP publique décrite dans le contrat OpenAPI :

- OpenAPI : https://www.estimatiz.fr/api/openapi.json
- Documentation : https://www.estimatiz.fr/api-documentation

## Données et rapports

Le service exploite notamment les Demandes de valeurs foncières. Les sources, la méthode et les limites figurent dans la réponse et dans le rapport. Une estimation ne garantit pas un prix de vente.

Le rapport n’est pas indexable par les moteurs de recherche. Toute personne possédant son lien peut toutefois le consulter.

## Éditeur et assistance

Le service est édité par SAS ESTIMATIZ.

- Assistance : `contact@estimatiz.fr`
- Conditions d’utilisation : https://www.estimatiz.fr/conditions-api
- Confidentialité : https://www.estimatiz.fr/confidentialite
- Site : https://www.estimatiz.fr

Ce dépôt documente le serveur public. Le code du service Estimatiz n’y est pas distribué.
