# Integration setup
## 

Configure version control and authentication integrations for your Self-Hosted instance.

- [GitHub (Enterprise) integration setup](./github-integration-setup.md): Set up an OAuth integration with GitHub Enterprise or GitHub.com.
- [Bitbucket.org integration setup](./bitbucket-integration-setup.md): Set up an OAuth integration with the public Bitbucket.org service.
- [Bitbucket Data Center / Server integration setup](./bitbucket-server-integration-setup.md): Set up an OAuth integration with Bitbucket Data Center / Server.
- [GitLab integration setup](./gitlab-integration-setup.md): Set up an OAuth integration with GitLab Self-Managed or GitLab.com.
- [Authentication with email addresses and password setup](./authentication-email-addresses-passwords-setup.md): Enable login and account registration with email addresses and passwords.

## Reaching the admin section without an account

Integrations and the _Global Configuration_ form both live in the admin section, which requires an admin account. As long as no authentication method is configured, nobody can log in, so there is no way to create that first account. Setup Mode covers that gap: while it is enabled, the admin section is reachable without authentication, so you can create your first integration or allow authentication with email addresses and passwords.

A fresh installation in a cluster installed with kURL has Setup Mode enabled, so you can go straight to the admin section. The Helm chart ships with `application.setupMode.enabled` set to `false`, so an installation in an existing cluster only reaches the admin section once you enable it.

Enable Setup Mode in your Self-Hosted configuration:

- Cluster installed with kURL: enable _Packagist Settings > Setup Mode_ in the admin console and apply the changes.
- Helm chart in an existing cluster: set `application.setupMode.enabled` to `true` in your values.yaml, apply it with `helm upgrade`, then restart the ui deployment with `kubectl rollout restart deployment ui`.

Setup Mode grants full administrative access to everyone who can reach your instance. Disable it again once you have set up an authentication method, tested logging in, and granted your account admin permissions. The same steps re-enable Setup Mode later if you lock yourself out of every admin account.
