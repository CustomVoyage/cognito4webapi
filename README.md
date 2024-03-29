# OAuth 2 / OpenID Connect (allowing for Cognito idiosyncrasies) for JavaScript Runtimes

## Notes on this fork
This fork takes [Filip Skokan](https://github.com/panva)s spec compliant library and breaks it to accommodate Cognito:
* Cognito doesn't include an 'aud' claim in its access tokens so this fork doesn't error when it's missing
  * Please upvote [this report](https://repost.aws/questions/QU4wv0qKIMSk2O64Wk5P4jdg/why-do-cognito-access-tokens-not-have-an-audience-claim) to get this issue fixed and remove the need for this fork
* Cognito doesn't include the 'typ' header parameter in its access tokens so this fork doesn't error when it's missing
  * Please upvote [this report](https://repost.aws/questions/QUdDANuP-mSLaNNwpQevEsyQ/cognito-oauth-access-token-missing-typ-header-parameter) to get this issue fixed and remove the need for this fork

In addition, this fork generalizes the validateJwtAccessToken() to accommodate scenarios where it is not possible to receive the token in the Authentication header (e.g. server rendered pages that don't involve client->server API calls) 

## Install

### Yarn
`yarn add cognito4webapi`

### npm
`npm install cognito4webapi`

Original readme [here](https://github.com/panva/oauth4webapi)