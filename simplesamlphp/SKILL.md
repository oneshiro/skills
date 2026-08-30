---
name: simplesamlphp
description: Configure, extend, troubleshoot, or upgrade SimpleSAMLphp for SAML 2.0 identity-provider and service-provider integrations. Use for SimpleSAMLphp PHP configuration, authentication sources, metadata, attribute processing, discovery services, modules, certificates, templates, Composer installation, and SAML login issues; do not use for generic PHP work unrelated to SimpleSAMLphp.
---

# SimpleSAMLphp

Inspect the project's installed version, existing configuration, module state, and deployment environment before changing anything. Preserve the site's established configuration format and framework conventions.

## Safe implementation

- Keep entity IDs, ACS/SLO URLs, certificate references, and metadata identifiers internally consistent. Validate endpoint URLs against the actual public deployment URL.
- Treat private keys, certificates, client secrets, passwords, and production metadata as sensitive. Do not expose values in output, rotate credentials, or overwrite production configuration unless explicitly authorized.
- Make narrowly scoped configuration changes. Keep authentication source and metadata changes separate where the installation uses separate files.
- For new or changed attribute filters, confirm whether attributes can be multi-valued and preserve required identifiers such as NameID.
- Validate PHP syntax and test in the relevant SAML role (SP or IdP) when a safe test environment is available.

## Reference

Read `references/simplesamlphp.md` for task-specific examples. It is a large, sourced collection; search first and read only matching sections.

```powershell
rg -n -i -C 3 'authsources|metadata|entityid|saml20' references/simplesamlphp.md
rg -n -i -C 3 'certificate|private key|signing|encryption' references/simplesamlphp.md
rg -n -i -C 3 'attribute|NameID|filter|eduPerson' references/simplesamlphp.md
rg -n -i -C 3 'disco|discovery|idp|service provider' references/simplesamlphp.md
rg -n -i -C 3 'composer|upgrade|module|memcache|ldap' references/simplesamlphp.md
```

Use examples as patterns, not drop-in production configuration. Reconcile them with the installed SimpleSAMLphp version and local configuration before applying them.
