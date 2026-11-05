## General overview

This microservice uses proven IAM plus our own domain service, to keep the traveler profile information: display name, avatar, settins, and the identity ID (for invitations).

As such, JWT tokens are checked against Keycloak's JWKS endpoint, and not against this microservices endpoint, as it does NOT hold the IAM, OAuth2 or OIDC directly. <-- todo: what is the difference between IAM, OAuth2 and OIDC. Explain it, so we know precisely how it will be used in our app. Through this we "defend" the bonus #24 point, so that the assistent knows what and why we did.

The Keycloak will run as another deployment on our AKS cluster, as a configurable infrastructure. This way we are able to accomplish our goal of using Google to register the user, through configuring Google as an "identity provider" in Keycloak's admin console. The rest is then taken care of by Keycloak.

All services trust tokens only from the Keycloaks realm of this app, which should be "campfire", for example: "https://auth.../realms/campfire".


## What is deployed under this microservice:
1. Keycloak with its official Helm chart (it uses its own PostgreSQL)
2. This microservice

## Project Points covered

\#24 - IAM, OAuth2, OIDC

## Generated signals:

TravelerRegistered