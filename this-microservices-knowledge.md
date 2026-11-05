## Keycloak - good to knows:

Keycloak has a concept named realms. It already has a master realm, for administrating Keycloak itself, but for our app we should create another "campfire" realm, where users of the app will be held.

A realm is NOT a tenant (in our app, a group of friend is a tenant), so only one realm is needed for our app. Our tenants will be separated inside our "campfire" realm by the tenant_id.