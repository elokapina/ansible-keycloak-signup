# Ansible Keycloak Signup

Maintains a [Keycloak Signup](https://github.com/elokapina/keycloak-signup)
installation.

Traefik friendly via Docker container labels.

## Installing

`ansible-galaxy install elokapina.ansible_keycloak_signup`

## Configuration

### Required

```yaml
## PostgreSQL related
keycloak_signup_database_password:
keycloak_signup_database_host:

## Keycloak
## Admin API url. Should be the full url and end with `/auth`
keycloak_signup_keycloak_base_url: https://your.keycloak.domain/auth
## Grant type
## This must be either "password" or "client_credentials"
keycloak_signup_keycloak_grant_type: password | client_credentials
## Admin password (required if grant type password)
keycloak_signup_keycloak_password:
## Admin client secret (required if grant type client_credentials)
keycloak_signup_keycloak_client_secret:
## Realm to manage users for - not the admin realm, that is assumed to be 'master'
keycloak_signup_keycloak_realm:
## Admin user username in the 'master' realm
keycloak_signup_keycloak_username:

## API
## Secret used to authenticate with the API for creating new pages for example
keycloak_signup_secret_token:
```

### Optional

These defaults will be used if no values provided.

```yaml
## Docker image
keycloak_signup_docker_image: elokapinaorg/keycloak-signup:latest
## Use for example to hook up with Traefik
keycloak_signup_docker_labels: []
## Docker network to attach to
keycloak_signup_docker_network: default
## PostgreSQL defaults
keycloak_signup_database_name: keycloak_signup
keycloak_signup_database_port: "5432"
keycloak_signup_database_user: keycloak_signup
## Keycloak
keycloak_signup_keycloak_client_id: admin-cli

## Title and welcome text
keycloak_signup_title: "Keycloak Signup"
keycloak_signup_welcome_text: "Sign up for a Keycloak account"

## App functionality and appearance
## Page to redirect to after successful signup
keycloak_signup_success_redirect:

## App styling
keycloak_signup_style_hero_background_color:
keycloak_signup_style_page_background_color:
keycloak_signup_style_primary_button_background_color:
```

## License

Apache 2.0
