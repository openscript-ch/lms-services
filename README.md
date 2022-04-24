# lms-services

This repository contains the configuration of our learning management system (lms) setup.

## Set up

Before the lms service can be deployed, a host needs to be set up. This is described here:

- [Services](https://github.com/openscript-ch/services/)

### Configure continuous integration

Set the following secrets for Github Actions. Make sure `$` are enquoted with another `$`.

| Value | Description | Example |
|---|---|---|
| `HTTP_AUTH_PASSWORD` | Password for http auth protected pages | |
| `PROXY_URL` | URL where the proxies (traefik) dashboard becomes available. | proxy.lms.example.com |
| `SITE_URL` | URL where the LMS becomes available. | lms.example.com |
| `MOODLE_EMAIL` | Contact email address displayed inside LMS. | admin@example.com |
| `MOODLE_SITENAME` | LMS name. | My learning club |
| `MOODLE_USERNAME` | Administrators username. | localhero |
| `MOODLE_PASSWORD` | Administrators password. | herolocal |
| `SMTP_HOST` | SMTP email server host URL. | smtp.gmail.com |
| `SMTP_PORT` | SMTP email server port. | 587 |
| `SMTP_USER` | SMTP email server username. | example@gmail.com |
| `SMTP_PASSWORD` | SMTP email server password. | herolocal |
| `MOODLE_MAIL_NOREPLY_ADDRESS` | Sender email for emails sent by LMS. | noreply@example.com |
| `ACME_EMAIL` | Contact email address for ACME challenge. | admin@example.com |
| `SSH_PRIVATE_KEY` | Base64 version of the ssh private key which is used to deploy LMS. Create with `cat secret-key | openssl base64 | tr -d '\n'`. | ... |
