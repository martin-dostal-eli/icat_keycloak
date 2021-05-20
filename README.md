# Keycloak Dev Instance

`@TODO`

## Requirements

`@TODO`

- Docker
- Docker-Compose
- Domains and DNS records 

## Installation

### Network setup
1. Create a new Docker network called `traefik-proxy`:
	```
  docker network create traefik-proxy
  ```
2. Create a new directory for Traefik configuration and files:
	```
  mkdir -p /opt/traefik
  ```
3. Create an empty file for security certificates:
	```
  touch /opt/traefik/acme.json && chmod 600 /opt/traefik/acme.json
  ```
4. Copy files from the repository's `traefik` folder into the `/opt/traefik` folder and replace any values marked by square brackets.
5. Start Traefik:
	```
  docker-compose -f /opt/traefik/docker-compose.yml up -d
  ```
	
### Keycloak setup
`@TODO`

1. Create a new directory for Keycloak configuration:
  ```
  mkdir -p /opt/keycloak
  ```
2. Copy file from the repository's `keycloak` folder into the `/opt/keycloak` folder and replace any values marked by square brackets.
3. Start Keycloak:
  ```
  docker-compose -f /opt/keycloak/docker-compose.yml up -d
  ```

## Resources
- Keycloak
  - [Access type settings](https://stackoverflow.com/questions/61964998/cannot-find-keycloak-openid-clients-client-secret)
    - Enables connection through `client_secret` for OpenID
