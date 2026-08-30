### Navigate to Installation Directory

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install-repo.md

Change to the directory where SimpleSAMLphp will be installed.

```bash
cd /var
```

--------------------------------

### Install SimpleSAMLphp Archive

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Extracts the downloaded SimpleSAMLphp archive to the desired installation directory.

```bash
cd /var
tar xzf simplesamlphp-x.y.z.tar.gz
mv simplesamlphp-x.y.z simplesamlphp
```

--------------------------------

### Enable Example Authentication Module

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-googleapps.md

Enable the 'exampleauth' module in SimpleSAMLphp's configuration to use the example authentication sources.

```php
'module.enable' => [
    'exampleauth' => true,
    …
],
```

--------------------------------

### Install Dependencies on Windows with Composer

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install-repo.md

Install dependencies on Windows, ignoring the POSIX platform requirement.

```bash
php composer.phar install --ignore-platform-req=ext-posix
```

--------------------------------

### Example Certificate Request Input

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-googleapps.md

Example of user input when creating a certificate signing request using OpenSSL.

```bash
Country Name (2 letter code) [AU]:NO
State or Province Name (full name) [Some-State]:Trondheim
Locality Name (eg, city) []:Trondheim
Organization Name (eg, company) [Internet Widgits Pty Ltd]:UNINETT
Organizational Unit Name (eg, section) []:
Common Name (eg, YOUR name) []:dev2.andreas.feide.no
Email Address []:

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:
```

--------------------------------

### SP Configuration with UIInfo

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example configuration for a Service Provider (SP) in authsources.php, demonstrating the use of UIInfo for display.

```php
<?php
$config = [

    'default-sp' => [
        'saml:SP',

        'UIInfo' => [
            'DisplayName' => [
                'en' => 'English name',
                'es' => 'Nombre en Español'
            ],
            'Description' => [
                'en' => 'English description',
                'es' => 'Descripción en Español'
            ],
        ],
        /* ... */
    ],
];

```

--------------------------------

### Install Dependencies with Composer

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install-repo.md

Install external dependencies required by SimpleSAMLphp using Composer.

```bash
php composer.phar install
```

--------------------------------

### UIInfo Description Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example of how to define localized descriptions for an entity within the UIInfo configuration.

```php
'Description' => [
    'en' => 'English description',
    'es' => 'Descripción en Español',
],
```

--------------------------------

### Navigate to SimpleSAMLphp Installation Directory for Upgrade

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install-repo.md

Change to the root directory of your SimpleSAMLphp installation to perform an upgrade.

```bash
cd /var/simplesamlphp
```

--------------------------------

### UIInfo InformationURL Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example of how to define localized URLs for additional information about an entity within the UIInfo configuration.

```php
'InformationURL' => [
    'en' => 'http://example.com/info/en',
    'es' => 'http://example.com/info/es',
],
```

--------------------------------

### Install and Run Markdown Linter

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-developer-information.md

Installs markdownlint-cli and runs it against a markdown file, with an option to automatically fix simpler issues.

```bash
npm install markdownlint-cli
cd ./node_modules/.bin
# copy the markdown lint file to markdownlintrc
./markdownlint -c markdownlintrc /tmp/simplesamlphp-developer-information.md
./markdownlint -c markdownlintrc --fix /tmp/simplesamlphp-developer-information.md
```

--------------------------------

### Install casserver Module with Composer

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-1.16.md

Install the updated `casserver` module using Composer. This module is maintained separately and requires explicit installation.

```bash
composer require simplesamlphp/simplesamlphp-module-casserver
```

--------------------------------

### Install LDAP Module with Composer

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-2.0.md

Use Composer to install the LDAP module if it was previously included by default.

```bash
composer require simplesamlphp/simplesamlphp-module-ldap --update-no-dev
```

--------------------------------

### UIInfo DisplayName Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example of how to define localized display names for an entity within the UIInfo configuration.

```php
'DisplayName' => [
    'en' => 'English name',
    'es' => 'Nombre en Español',
],
```

--------------------------------

### Configure Multiple Metadata Storage Sources

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Example configuration for using different metadata storage backends simultaneously, such as flatfile, directory, and serialize.

```php
'metadata.sources' => [
    ['type' => 'flatfile'],
    ['type' => 'flatfile', 'directory' => 'metadata/metarefresh-kalmar'],
    ['type' => 'serialize', 'directory' => 'metadata/metarefresh-ukaccess'],
    ['type' => 'directory'],
    ['type' => 'directory', 'directory' => 'metadata/somewhere-else'],
],
```

--------------------------------

### Install Memcache and PHP Extension (Debian/Ubuntu)

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-artifact-idp.md

Installs the memcached server and the PHP memcached client extension on Debian-based systems. Ensure memcache is secured and only accessible locally by default.

```bash
apt install memcached php-memcached
```

--------------------------------

### UIInfo Logo Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example of how to define logos for an entity within the UIInfo configuration, including URL, dimensions, and language.

```php
'Logo' => [
    [
        'url'    => 'http://example.com/logo1.png',
        'height' => 200,
        'width'  => 400,
        'lang'   => 'en',
    ],
    [
        'url'    => 'http://example.com/logo2.png',
        'height' => 201,
        'width'  => 401,
    ],
],
```

--------------------------------

### Configure DiscoHints - IPHint

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example configuration for IPHint within DiscoHints, specifying IP addresses in CIDR notation.

```php
'IPHint' => ['130.59.0.0/16', '2001:620::0/96']
```

--------------------------------

### UIInfo Keywords Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example of how to define localized keywords for an entity within the UIInfo configuration. Note that the '+' character is forbidden.

```php
'Keywords' => [
    'en' => ['communication', 'federated session'],
    'es' => ['comunicación', 'sesión federated'],
],
```

--------------------------------

### Configure Memcache Servers

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Example of a simple Memcache configuration with a single server running on localhost. All sessions will be lost if the Memcache server crashes.

```php
'memcache_store.servers' => [
    [
        ['hostname' => 'localhost'],
    ],
],
```

--------------------------------

### Configure UIInfo Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example configuration for UIInfo metadata, including display names, descriptions, URLs, keywords, and logos. Supports localization.

```php
$metadata['https://example.com/saml-idp'] = [
    'host' => 'www.example.com',
    'certificate' => 'example.com.crt',
    'privatekey' => 'example.com.pem',
    'auth' => 'example-userpass',

    'UIInfo' => [
        'DisplayName' => [
            'en' => 'English name',
            'es' => 'Nombre en Espa\u00f1ol',
        ],
        'Description' => [
            'en' => 'English description',
            'es' => 'Descripci\u00f3n en Espa\u00f1ol',
        ],
        'InformationURL' => [
            'en' => 'http://example.com/info/en',
            'es' => 'http://example.com/info/es',
        ],
        'PrivacyStatementURL' => [
            'en' => 'http://example.com/privacy/en',
            'es' => 'http://example.com/privacy/es',
        ],
        'Keywords' => [
            'en' => ['communication', 'federated session'],
            'es' => ['comunicaci\u00f3n', 'sesi\u00f3n federated'],
        ],
        'Logo' => [
            [
                'url'    => 'http://example.com/logo1.png',
                'height' => 200,
                'width'  => 400,
            ],
            [
                'url'    => 'http://example.com/logo2.png',
                'height' => 201,
                'width'  => 401,
            ],
        ],
    ],
    'DiscoHints' => [
        'IPHint'          => ['130.59.0.0/16', '2001:620::0/96'],
        'DomainHint'      => ['example.com', 'www.example.com'],
        'GeolocationHint' => ['geo:47.37328,8.531126', 'geo:19.34343,12.342514'],
    ],
];
```

--------------------------------

### New SimpleSAMLphp Event Listener Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-modules.md

Shows the modern SimpleSAMLphp event listener implementation using a class with an __invoke method, receiving an event object.

```php
    class ConfigPageListener
    {
        public function __invoke(ConfigPageEvent $event): void
        {
            $template = $event->getTemplate();
        
            $template->data['links'][] = [
                'href' => \SimpleSAML\Module::getModuleURL('cron/info'),
                'text' => \SimpleSAML\Locale\Translate::noop('Cron module information page'),
            ];
            ...
        }
    }
```

--------------------------------

### Configure DiscoHints - DomainHint

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example configuration for DomainHint within DiscoHints, specifying domain names.

```php
'DomainHint' => ['example.com', 'www.example.com']
```

--------------------------------

### Minimal metadata/saml20-idp-remote.php example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

This file configures the remote Identity Providers your Service Provider will connect to. It includes essential endpoints and the IdP's signing certificate.

```php
<?php
$metadata['https://example.org/saml-idp'] = [
    'SingleSignOnService' => [
        [
          'Location' => 'https://example.org/simplesaml/module.php/saml/idp/singleSignOnService',
          'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect',
        ],
    ],
    'SingleLogoutService' => [
        [
          'Location' => 'https://example.org/simplesaml/module.php/saml/idp/singleLogout',
          'ResponseLocation' => 'https://sp.example.org/LogoutResponse',
          'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect',
        ],
    ],
    'certificate' => 'example.pem',
];

```

--------------------------------

### Multiple Service Providers in authsources.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

Example demonstrating how to configure multiple Service Providers within the same authsources.php file. Ensure each SP has an explicitly set EntityID.

```php
    'sp1' => [
        'saml:SP',
        'entityID' => 'https://myapp.example.org/',
    ],
    'sp2' => [
        'saml:SP',
        'entityID' => 'https://myotherapp.example.org/',
    ],

```

--------------------------------

### Install Dependencies with npm

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/New-UI

Use npm or another package manager to install project dependencies, including new ones as they are added.

```bash
npm install
```

--------------------------------

### Managing PHP Sessions with SimpleSAMLphp API

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Demonstrates how to correctly manage PHP sessions when interacting with the SimpleSAMLphp API. It shows how to start a session, use the SimpleSAMLphp API, and then revert to the original PHP session.

```php
session_start();
// ...
$auth = new \SimpleSAML\Auth\Simple('default-sp');
$auth->isAuthenticated(); // Replaces our session with the SimpleSAMLphp one
// $_SESSION['key'] = 'value'; // This would save to the SimpleSAMLphp session which isn't what we want
\SimpleSAML\Session::getSessionFromRequest()->cleanup(); // Reverts to our PHP session
// Save to our session
$_SESSION['key'] = 'value';
```

--------------------------------

### Get Global Database Instance

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-database.md

Retrieve the globally configured database instance for general use.

```php
$db = \SimpleSAML\Database::getInstance();
```

--------------------------------

### IdP Metadata Configuration with UIInfo and DiscoHints

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example configuration for an Identity Provider (IdP) in metadata/saml20-idp-hosted.php, including UIInfo for display and DiscoHints for discovery.

```php
<?php
$metadata['entity-id-1'] = [
    /* ... */
    'UIInfo' => [
        'DisplayName' => [
            'en' => 'English name',
            'es' => 'Nombre en Español',
        ],
        'Description' => [
            'en' => 'English description',
            'es' => 'Descripción en Español',
        ],
        'InformationURL' => [
            'en' => 'http://example.com/info/en',
            'es' => 'http://example.com/info/es',
        ],
        'PrivacyStatementURL' => [
            'en' => 'http://example.com/privacy/en',
            'es' => 'http://example.com/privacy/es',
        ],
        'Keywords' => [
            'en' => ['communication', 'federated session'],
            'es' => ['comunicación', 'sesión federated'],
        ],
        'Logo' => [
            [
                'url'    => 'http://example.com/logo1.png',
                'height' => 200,
                'width'  => 400,
                'lang'   => 'en',
            ],
            [
                'url'    => 'http://example.com/logo2.png',
                'height' => 201,
                'width'  => 401,
            ],
        ],
    ],
    'DiscoHints' => [
        'IPHint'          => ['130.59.0.0/16', '2001:620::0/96'],
        'DomainHint'      => ['example.com', 'www.example.com'],
        'GeolocationHint' => ['geo:47.37328,8.531126', 'geo:19.34343,12.342514'],
    ],
    /* ... */
];

```

--------------------------------

### SourceIPSelector Configuration Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authsource_selector.md

Configure the SourceIPSelector to delegate authentication based on the client's IP address. Define zones with IP subnets and their corresponding authentication sources, with an optional default fallback.

```php
    'selector' => [
        'core:SourceIPSelector',

        'zones' => [
            'internal' => [
                'source' => 'ldap',
                'subnet' => [
                    '10.0.0.0/8',
                    '2001:0DB8::/108',
                ],
            ],

            'other' => [
                'source' => 'radius',
                'subnet' => [
                    '172.16.0.0/12',
                    '2002:1234::/108',
                ],
            ],

            'default' => 'yubikey',
        ],
    ],
```

--------------------------------

### Example User Data for Database Authentication

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

Inserts a sample user into the 'userdb' table with a base64 encoded SSHA password hash.

```sql
INSERT INTO userdb (username, password_hash, full_name)
    VALUES('exampleuser', 'QwVYkvlrAMsXIgULyQ/pDDwDI3dF2aJD4XeVxg==', 'Example User');

```

--------------------------------

### UIInfo PrivacyStatementURL Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example of how to define localized URLs for an entity's privacy statement within the UIInfo configuration.

```php
'PrivacyStatementURL' => [
    'en' => 'http://example.com/privacy/en',
    'es' => 'http://example.com/privacy/es',
],
```

--------------------------------

### Database Schema for Custom Authentication Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

Defines the structure of the 'userdb' table for storing username, password hash, and full name.

```sql
CREATE TABLE userdb (
    username VARCHAR(32) PRIMARY KEY NOT NULL,
    password_hash VARCHAR(64) NOT NULL,
    full_name TEXT NOT NULL);

```

--------------------------------

### PHP Configuration for Entity Attributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-attributes.md

Example of defining entity attributes within a SimpleSAMLphp IdP hosted metadata configuration file.

```php
<?php
$metadata['entity-id-1'] = [
    /* ... */
    'EntityAttributes' => [
        'urn:simplesamlphp:v1:simplesamlphp' => ['is', 'really', 'cool'],
        '{urn:simplesamlphp:v1}foo'          => ['bar'],
    ],
    /* ... */
];

```

--------------------------------

### Example: Generating Persistent NameID and eduPersonTargetedID

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/nameid.md

This example configures the generation of a persistent NameID and its subsequent addition to the eduPersonTargetedID attribute using the saml:PersistentNameID2TargetedID filter. It also includes attribute mapping to OID names.

```php
'authproc' => [
        // Generate the persistent NameID.
        2 => [
            'class' => 'saml:PersistentNameID',
            'identifyingAttribute' => 'eduPersonPrincipalName',
        ],
        // Add the persistent to the eduPersonTargetedID attribute
        60 => [
            'class' => 'saml:PersistentNameID2TargetedID',
            'attribute' => 'eduPersonTargetedID', // The default
            'nameId' => true, // The default
        ],
        // Use OID attribute names.
        90 => [
            'class' => 'core:AttributeMap',
            'name2oid',
        ],
    ],
    // The URN attribute NameFormat for OID attributes.
    'attributes.NameFormat' => 'urn:oasis:names:tc:SAML:2.0:attrname-format:uri',
    'attributeencodings' => [
        'urn:oid:1.3.6.1.4.1.5923.1.1.1.10' => 'raw', /* eduPersonTargetedID with oid NameFormat is a raw XML value */
    ],
```

--------------------------------

### Example Error Log Entry

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Segmentation-faults-in-Apache

This is an example of a segmentation fault error message that might appear in the Apache error log.

```log
[core:notice] [pid 1234] AH00051: child pid 12345 exit signal Segmentation fault (11), possible coredump in /etc/apache2
```

--------------------------------

### Cron Module Configuration Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/cron/docs/cron.md

Configure the cron module by setting a unique 'key' for security, 'allowed_tags' for task categorization, and 'sendemail' to control email notifications.

```php
$config = [
   'key' => 'RANDOM_KEY',
   'allowed_tags' => ['daily', 'hourly', 'frequent'],
   'debug_message' => true,
   'sendemail' => true,
];
```

--------------------------------

### RequestedAuthnContextSelector Configuration Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authsource_selector.md

Configure the RequestedAuthnContextSelector to delegate authentication based on the RequestedAuthnContext. Map specific contexts to authentication sources, with a default source for requests lacking a context.

```php
    'selector' => [
        'core:RequestedAuthnContextSelector',

        'contexts' => [
            10 => [
                'identifier' => 'urn:x-simplesamlphp:loa1',
                'source' => 'ldap',
            ],

            20 => [
                'identifier' => 'urn:x-simplesamlphp:loa2',
                'source' => 'radius',
            ],

            'default' => [
                'identifier' => 'urn:x-simplesamlphp:loa0',
                'source' => 'sql',
            ],
        ],
    ],
```

--------------------------------

### Old SimpleSAMLphp Hook Interface Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-modules.md

Illustrates the structure of a legacy SimpleSAMLphp hook function, which directly receives a Template object as an argument.

```php
    // old hook interface
    function cron_hook_configpage(Template &$template): void
    {
      $template->data['links'][] = [
          'href' => Module::getModuleURL('cron/info'),
          'text' => Translate::noop('Cron module information page'),
      ];
      ...
    }
```

--------------------------------

### Access SimpleSAMLphp Admin Interface

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Access the administrative interface of your SimpleSAMLphp installation by appending '/admin/' to the base URL.

```text
https://service.example.org/simplesaml/admin/
```

--------------------------------

### Get Alternate Database Instance

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-database.md

Connect to an alternate database server using a custom configuration array. Ensure the configuration contains keys like database.dsn, database.username, and database.password.

```php
$config = new \SimpleSAML\Configuration($myconfigarray, "mymodule/lib/Auth/Source/myauth.php");
$db = \SimpleSAML\Database::getInstance($config);
```

--------------------------------

### Configure AuthnContextClassRef in IDP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/authproc_authncontextclassref.md

Example configuration for the 'authproc.idp' filter to set the AuthnContextClassRef in SAML authentication responses.

```php
'authproc.idp' => [
      92 => [
        'class' => 'saml:AuthnContextClassRef',
        'AuthnContextClassRef' => 'urn:oasis:names:tc:SAML:2.0:ac:classes:PasswordProtectedTransport',
      ],
    ],
```

--------------------------------

### Generated XML Metadata for UIInfo and DiscoHints

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example of XML metadata generated from the PHP configuration, showcasing UIInfo and DiscoHints elements.

```xml
<?xml version="1.0"?>
<md:EntityDescriptor xmlns:md="urn:oasis:names:tc:SAML:2.0:metadata" xmlns:mdattr="urn:oasis:names:tc:SAML:metadata:attribute" xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:mdui="urn:oasis:names:tc:SAML:metadata:ui" xmlns:ds="http://www.w3.org/2000/09/xmldsig#" entityID="https://example.com/saml-idp">
  <md:IDPSSODescriptor protocolSupportEnumeration="urn:oasis:names:tc:SAML:2.0:protocol">
    <md:Extensions>
      <mdui:UIInfo xmlns:mdui="urn:oasis:names:tc:SAML:metadata:ui">
        <mdui:DisplayName xml:lang="en">English name</mdui:DisplayName>
        <mdui:DisplayName xml:lang="es">Nombre en Espa&#xF1;ol</mdui:DisplayName>
        <mdui:Description xml:lang="en">English description</mdui:Description>
        <mdui:Description xml:lang="es">Descripci&#xF3;n en Espa&#xF1;ol</mdui:Description>
        <mdui:InformationURL xml:lang="en">http://example.com/info/en</mdui:InformationURL>
        <mdui:InformationURL xml:lang="es">http://example.com/info/es</mdui:InformationURL>
        <mdui:PrivacyStatementURL xml:lang="en">http://example.com/privacy/en</mdui:PrivacyStatementURL>
        <mdui:PrivacyStatementURL xml:lang="es">http://example.com/privacy/es</mdui:PrivacyStatementURL>
        <mdui:Keywords xml:lang="en">communication federated+session</mdui:Keywords>
        <mdui:Keywords xml:lang="es">comunicaci&#xF3;n sesi&#xF3;n+federated</mdui:Keywords>
        <mdui:Logo width="400" height="200" xml:lang="en">http://example.com/logo1.png</mdui:Logo>
        <mdui:Logo width="401" height="201">http://example.com/logo2.png</mdui:Logo>
      </mdui:UIInfo>
      <mdui:DiscoHints xmlns:mdui="urn:oasis:names:tc:SAML:metadata:ui">
        <mdui:IPHint>130.59.0.0/16</mdui:IPHint>

```

--------------------------------

### Apache Virtual Host Configuration for SimpleSAMLphp

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Configure an Apache virtual host to serve SimpleSAMLphp. This example sets up an alias for the SimpleSAMLphp public directory and specifies the configuration directory.

```apacheconf
<VirtualHost *>
    ServerName service.example.com
    DocumentRoot /var/www/service.example.com

    SetEnv SIMPLESAMLPHP_CONFIG_DIR /var/simplesamlphp/config

    Alias /simplesaml /var/simplesamlphp/public

    <Directory /var/simplesamlphp/public>
        Require all granted
    </Directory>
</VirtualHost>
```

--------------------------------

### Example: Making Three NameIDs Available

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/nameid.md

This configuration snippet demonstrates how to make three different types of NameIDs available: TransientNameID, PersistentNameID, and AttributeNameID with a specific format.

```php
'authproc' => [
        1 => [
            'class' => 'saml:TransientNameID',
        ],
        2 => [
            'class' => 'saml:PersistentNameID',
            'identifyingAttribute' => 'eduPersonPrincipalName',
        ],
        3 => [
            'class' => 'saml:AttributeNameID',
            'identifyingAttributes' => ['mail','eduPersonPrincipalName'],
            'Format' => 'urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress',
        ],
    ],
```

--------------------------------

### Configure core:ScopeAttribute Filter

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_scopeattribute.md

Example configuration for the core:ScopeAttribute filter. Use this to combine attributes into a scoped attribute.

```php
10 => [
        'class' => 'core:ScopeAttribute',
        'scopeAttribute' => 'eduPersonPrincipalName',
        'sourceAttribute' => 'eduPersonAffiliation',
        'targetAttribute' => 'eduPersonScopedAffiliation',
    ]
```

--------------------------------

### Configure AuthProc Filter with Precondition

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-authproc.md

Example of adding an 'authproc' filter with a precondition. The filter will only run if the specified condition evaluates to true.

```php
'authproc' => [
    40 => 'core:TargetedID',
    '%precondition' => 'return $attributes["displayName"] === "John Doe";',
],
```

--------------------------------

### Require Authentication (Basic)

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Ensures the user is authenticated. If not, it initiates the authentication process. This example cleans up the session and prints a message upon successful authentication.

```php
$auth->requireAuth();
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
print("Hello, authenticated user!");
```

--------------------------------

### Running Unit Tests with PhpUnit

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/List-of-tasks

This command is used to run the test suite for SimpleSAMLphp and generate code coverage information to identify areas lacking testing. Ensure PhpUnit is installed and configured.

```bash
php vendor/phpunit/phpunit/phpunit --configuration tools/phpunit
```

--------------------------------

### Initialize Configuration and Metadata Files

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install-repo.md

Copy default configuration and metadata files to their active locations.

```bash
cd /var/simplesamlphp
cp config/config.php.dist config/config.php
cp config/authsources.php.dist config/authsources.php
cp metadata/saml20-idp-hosted.php.dist metadata/saml20-idp-hosted.php
cp metadata/saml20-idp-remote.php.dist metadata/saml20-idp-remote.php
cp metadata/saml20-sp-remote.php.dist metadata/saml20-sp-remote.php
```

--------------------------------

### Configure DiscoHints - GeolocationHint

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-ui.md

Example configuration for GeolocationHint within DiscoHints, specifying geographic coordinates using the geo URI scheme.

```php
'GeolocationHint' => ['geo:47.37328,8.531126', 'geo:19.34343,12.342514']
```

--------------------------------

### PHP Namespace Declaration Example

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/List-of-tasks

Demonstrates how to declare namespaces for classes located in the lib directory or within modules. This is part of the migration to PSR-4 standards.

```php
namespace SimpleSAML\Foo; // for classes located in lib/SimpleSAML/Foo/

```

```php
namespace SimpleSAML\Module\modulename\Bar; // for classes located in modules/modulename/lib/Bar/

```

--------------------------------

### Shorthand Notation for Min/Max Values

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_cardinality.md

This example demonstrates the shorthand notation for specifying minimum and maximum values for an attribute, such as 'mail'. It's a more concise way to define cardinality rules.

```php
'authproc' => [
    50 => [
        'class' => 'core:Cardinality',
        'mail' => [0, 2],
    ],
],
```

--------------------------------

### Copy Configuration and Metadata for Upgrade

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Copies configuration and metadata directories from an old SimpleSAMLphp version to a new one during an upgrade.

```bash
cd /var/simplesamlphp-x.y.z
rm -rf config metadata
cp -rv ../simplesamlphp/config config
cp -rv ../simplesamlphp/metadata metadata
```

--------------------------------

### Configure ScopeFromAttribute Filter

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_scopefromattribute.md

Example configuration for the core:ScopeFromAttribute filter to set the 'scope' attribute based on 'eduPersonPrincipalName'.

```php
'authproc' => [
    50 => [
        'class' => 'core:ScopeFromAttribute',
        'sourceAttribute' => 'eduPersonPrincipalName',
        'targetAttribute' => 'scope',
    ],
],
```

--------------------------------

### Configure AuthProc Filter in Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-authproc.md

Example of adding an 'authproc' filter to hosted metadata. This filter is applied during the authentication process.

```php
$metadata['https://example.org/saml-idp'] = [
    'host' => '__DEFAULT_',
    'privatekey' => 'example.org.pem',
    'certificate' => 'example.org.crt',
    'auth' => 'feide',
    'authproc' => [
        40 => 'core:TargetedID',
    ],
]
```

--------------------------------

### Running Tests Locally with PHPUnit

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/TESTING.md

Command to execute tests using a locally installed PHPUnit version. Ensure the config directory is not in the root.

```sh
phpunit -c ./phpunit.xml
```

--------------------------------

### Configure a Static Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-modules.md

Defines a static authentication source named 'example-static' using the 'exampleauth:StaticSource' class and provides user attributes.

```php
'example-static' => [
        /* This maps to modules/exampleauth/src/Auth/Source/Static.php */
        'exampleauth:StaticSource',
    
        /* The following is configuration which is passed on to
         * the exampleauth:StaticSource authentication source. */
        'uid' => 'testuser',
        'eduPersonAffiliation' => ['member', 'employee'],
        'cn' => ['Test User'],
    ],
```

--------------------------------

### Complete Custom Authentication Class with Login Logic

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

A full example of a custom authentication class extending UserPassBase, including constructor and login method.

```php
<?php

class MyAuth extends \SimpleSAML\Module\core\Auth\UserPassBase
{
    private $username;
    private $password;

    public function __construct($info, $config)
    {
        parent::__construct($info, $config);
        if (!is_string($config['username'])) {
            throw new Exception('Missing or invalid username option in config.');
        }
        $this->username = $config['username'];

        if (!is_string($config['password'])) {
            throw new Exception('Missing or invalid password option in config.');
        }
        $this->password = $config['password'];
    }

    protected function login(string $username, string $password): array
    {
        if ($username !== $this->username || $password !== $this->password) {
            throw new \SimpleSAML\Error\Error(\SimpleSAML\Error\ErrorCodes::WRONGUSERPASS);
        }

        return [
            'uid' => [$this->username],
            'displayName' => ['Some Random User'],
            'eduPersonAffiliation' => ['member', 'employee'],
        ];
    }
}

```

--------------------------------

### IdP-first Flow URL Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp-more.md

This URL initiates the SSO flow at the IdP by redirecting the user to the SSOService endpoint with a specified SP EntityID.

```url
https://idp.example.org/simplesaml/module.php/saml/idp/singleSignOnService?spentityid=urn:mace:feide.no:someservice
```

--------------------------------

### Define allowed attributes in SP metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

Example of how to define allowed attributes and specific values for an attribute within the SP metadata configuration.

```php
$metadata['https://saml2sp.example.org'] = [
    'AssertionConsumerService' => 'https://saml2sp.example.org/simplesaml/module.php/saml/sp/saml2-acs.php/default-sp',
    'SingleLogoutService' => 'https://saml2sp.example.org/simplesaml/module.php/saml/sp/saml2-logout.php/default-sp',
    ...
    'attributes' => [
        'uid',
        'mail',
        'eduPersonEntitlement' => [
            'urn:mace:example.org:admin',
            'urn:mace:example.org:user',
        ],
    ],
    ...
];
```

--------------------------------

### Global Auth Proc Filters Configuration in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-authproc.md

Example of configuring multiple Auth Proc Filters globally in the config.php file for an IdP. Filters are executed based on their priority index.

```php
'authproc.idp' => [
    10 => [
        'class' => 'core:AttributeMap',
        'addurnprefix'
    ],
    20 => 'core:TargetedID',
    50 => 'core:AttributeLimit',
    90 => [
        'class' => 'consent:Consent',
        'store' => 'consent:Cookie',
        'focus' => 'yes',
        'checked' => true
    ]
],
```

--------------------------------

### Configure Authentication Source with Users

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp.md

Define an authentication source named 'example-userpass' using the 'exampleauth:UserPass' module. This configuration includes two users, 'student' and 'employee', with their respective passwords and associated attributes.

```php
<?php

$config = [
    'example-userpass' => [
        'exampleauth:UserPass',
        'users' => [
            'student:studentpass' => [
                'uid' => ['student'],
                'eduPersonAffiliation' => ['member', 'student'],
            ],
            'employee:employeepass' => [
                'uid' => ['employee'],
                'eduPersonAffiliation' => ['member', 'employee'],
            ],
        ],
    ],
];

```

--------------------------------

### Implement Custom Metadata Storage Handler

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Example of defining a custom metadata storage handler class that extends \SimpleSAML\Metadata\MetaDataStorageSource and follows PSR-4 autoloading standards.

```php
<?php
namespace SimpleSAML\Module\mymodule\MetadataStore;

class MyMetadataHandler extends \SimpleSAML\Metadata\MetaDataStorageSource
{
    ...
}
```

--------------------------------

### Configure ExpectedAuthnContextClassRef

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/authproc_expectedauthncontextclassref.md

Example configuration for the saml:ExpectedAuthnContextClassRef filter in the SP's authproc configuration. It specifies a list of accepted AuthnContextClassRef values.

```php
'authproc.sp' => [
      91 => [
        'class' => 'saml:ExpectedAuthnContextClassRef',
        'accepted' => [
          'urn:oasis:names:tc:SAML:2.0:post:ac:classes:nist-800-63:3',
          'urn:oasis:names:tc:SAML:2.0:ac:classes:Password',
        ],
      ],
    ],
```

--------------------------------

### Expecting Exceptions in Tests

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/TESTING.md

This example demonstrates how to use PHPUnit's expectException() method to ensure a specific method throws an exception under certain conditions.

```php
  /**
    * Test SimpleSAML\Utils\HTTP::addURLParameters().
    */
  public function testAddURLParametersInvalidParameters() {
      $this->expectException(ExpectedException::class);
```

--------------------------------

### Configuring Identity Provider Hosted Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-2.0.md

Example of how an Identity Provider (IdP) hosted metadata is defined in SimpleSAMLphp, specifically showing how the entityID is used as the key in the metadata array.

```php
...
$metadata['https://example.com/the-service/'] = [
...
```

--------------------------------

### Select Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

Instantiate the SimpleSAML\Auth\Simple class, specifying the name of your authentication source configuration.

```php
$as = new \SimpleSAML\Auth\Simple('default-sp');
```

--------------------------------

### Configure saml:SubjectID Filter

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/authproc_subjectid.md

Example configuration for the saml:SubjectID filter, specifying the identifying attribute, scope attribute, and enabling hashing.

```php
    'authproc' => [
        50 => [
            'class' => 'saml:SubjectID',
            'identifyingAttribute' => 'uid',
            'scopeAttribute' => 'scope',
            'hashed' => true,
        ],
    ],
```

--------------------------------

### Enable New UI Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/New-UI

To activate the new user interface, set the 'usenewui' option to true in the configuration.

```php
'usenewui' => true,
```

--------------------------------

### Require Authentication with Redirect Parameters

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Ensures user authentication, redirecting to a specified URL and optionally keeping POST data. This example demonstrates setting 'ReturnTo' and 'KeepPost' parameters.

```php
$auth->requireAuth([
    'ReturnTo' => 'https://sp.example.org/',
    'KeepPost' => FALSE,
]);
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
print("Hello, authenticated user!");
```

--------------------------------

### Define allowed attributes using regex in SP metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

Example of how to define allowed attributes using regular expressions within the SP metadata configuration.

```php
$metadata['https://saml2sp.example.org'] = [
    'AssertionConsumerService' => 'https://saml2sp.example.org/simplesaml/module.php/saml/sp/saml2-acs.php/default-sp',
    'SingleLogoutService' => 'https://saml2sp.example.org/simplesaml/module.php/saml/sp/saml2-logout.php/default-sp',
    ...
    'attributes' => ['cn', ... ],
    'attributesRegex' => [ '/^mail$/', ... ],
    ...
];
```

--------------------------------

### Initiate Login with Passive Request

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Starts a login operation with a passive authentication request, specifying an error URL. The session is cleaned up after the operation.

```php
# Send a passive authentication request.
$auth->login([
    'isPassive' => true,
    'ErrorURL' => 'https://.../error_handler.php',
]);
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
```

--------------------------------

### PHP Class Definition with Namespace

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/List-of-tasks

Shows how to define a class within a declared namespace, following the new naming conventions. This example illustrates the change from the old naming convention to the new namespaced structure.

```php
class Bar
{

```

--------------------------------

### Allow attributes matching a regex pattern

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This snippet allows attributes whose names start with 'eduPerson' by using a regular expression.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeLimit',
        '/^eduPerson' => [ 'nameIsRegex' => true ]
    ],
],
```

--------------------------------

### IdP Metadata for SP's ArtifactResolutionService

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-artifact-idp.md

Example of how the 'ArtifactResolutionService' endpoint should be represented in the remote IdP metadata on a SimpleSAMLphp SP. This specifies the SOAP binding for artifact resolution.

```php
'ArtifactResolutionService' => [
    [
        'index' => 0,
        'Location' => 'https://idp.example.org/simplesaml/saml2/idp/ArtifactResolutionService.php',
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:SOAP',
    ],
],
```

--------------------------------

### Autoloader Renaming Mapping Example

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/List-of-tasks

Illustrates how to add a mapping to the autoloader function in `lib/_autoload_modules.php` when renaming a class during namespace migration. This ensures backward compatibility by creating aliases.

```php
   'SimpleSAML_Foo_Bar' => 'SimpleSAML_Bar_Foo',
```

--------------------------------

### Configure UserPass Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-googleapps.md

Define an authentication source named 'example-userpass' using the 'exampleauth:UserPass' module. This configuration sets up two users, 'student' and 'employee', with their respective passwords and a 'uid' attribute.

```php
<?php

$config = [
    'example-userpass' => [
        'exampleauth:UserPass',
        'student:studentpass' => [
            'uid' => ['student'],
        ],
        'employee:employeepass' => [
            'uid' => ['employee'],
        ],
    ],
];

```

--------------------------------

### IdP-First SSO URL Example

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp.md

Use this URL to initiate an SSO flow from the IdP to a specific Service Provider (SP). The 'spentityid' parameter identifies the target SP.

```text
https://idp.example.org/simplesaml/module.php/saml/idp/singleSignOnService?spentityid=sp.example.org
```

--------------------------------

### Example: Storing Persistent NameIDs in SQL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/nameid.md

This configuration shows how to use the saml:SQLPersistentNameID filter to store persistent NameIDs in a SQL database, alongside the TransientNameID filter.

```php
'authproc' => [
        1 => [
            'class' => 'saml:TransientNameID',
        ],
        2 => [
            'class' => 'saml:SQLPersistentNameID',
            'identifyingAttribute' => 'eduPersonPrincipalName',
        ],
    ],
```

--------------------------------

### Translate Organization Name to Multiple Languages

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-remote.md

This snippet illustrates how to specify translated names for the organization responsible for the IdP. It provides an example for English and Norwegian.

```php
'OrganizationName' => [
    'en' => 'Example organization',
    'no' => 'Eksempel organisation',
]
```

--------------------------------

### Running Tests with Composer's PHPUnit

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/TESTING.md

Command to execute tests using the PHPUnit version installed via Composer. This is useful if your default PHPUnit version is newer than 5.7.

```sh
./vendor/bin/phpunit -c ./phpunit.xml
```

--------------------------------

### Initialize PDO Metadata Storage Database

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-pdostoragehandler.md

Run this command to create the necessary database tables for storing metadata when using the PDO metadata handler. Ensure your database connection is configured in `config.php`.

```bash
php bin/initMDSPdo.php
```

--------------------------------

### login

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Initiates a login operation, always starting a new authentication process. Supports various parameters to control the authentication flow, such as error URLs, post data handling, and return destinations.

```APIDOC
## login

### Description
Start a login operation. This function will always start a new authentication process.

### Parameters
* **params** (array) - Optional - An associative array with named parameters. Supported global parameters include:
    * **ErrorURL** (string): A URL to a page which will receive errors that may occur during authentication.
    * **KeepPost** (bool): If set to `TRUE`, the current POST data will be submitted again after authentication. The default is `TRUE`.
    * **ReturnTo** (string): The URL the user should be returned to after authentication. The default is to return the user to the current page.
    * **ReturnCallback** (array): The function to call when the user finishes authentication.
    The [`saml:SP`](./saml:sp) authentication source also defines some parameters.

### Example
```php
# Send a passive authentication request.
$auth->login([
    'isPassive' => true,
    'ErrorURL' => 'https://.../error_handler.php',
]);
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
```
```

--------------------------------

### Enable Module and Set Theme in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-theming.md

Configure SimpleSAMLphp to enable a custom module and specify which theme to use. The `theme.use` parameter points to the desired theme.

```php
'module.enable' => [
    ...
    'mymodule' => true,
],

'theme.use' => 'mymodule:fancytheme',
```

--------------------------------

### Attribute Map in Separate File

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributemap.md

Reference an external attribute map file located in the 'attributemap/' directory of the SimpleSAMLphp installation. The filter will use the mappings defined in this file.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeMap',
            'name2oid',
        ],
    ],
```

--------------------------------

### Custom Error Display Function in SimpleSAMLphp

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-errorhandling.md

Implement a custom error display function by defining 'errors.show_function' in config.php. This example replicates the default functionality of \SimpleSAML\Error\Error::show.

```php
public static function show(\SimpleSAML\Configuration $config, array $data)
{
    $t = new \SimpleSAML\XHTML\Template($config, 'error.twig', 'errors');
    $t->data = array_merge($t->data, $data);
    $t->send();
    exit;
}
```

--------------------------------

### Processing eduPersonTargetedID Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-1.14.md

Example of how to process the eduPersonTargetedID attribute when it is returned as a DOMNodeList object. This is useful for Service Providers that need to extract the NameID value.

```php
<?php
$attributes = $as->getAttributes();
$eptid = $attributes['eduPersonTargetedID'][0]->item(0);
$nameID = new SAML2_XML_saml_NameID($eptid);
?>
```

--------------------------------

### Configure Flatfile and PDO Metadata Sources

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-pdostoragehandler.md

Add this configuration to your `config/config.php` file to enable both flatfile and PDO metadata sources. This allows for a hybrid approach to metadata management.

```php
'metadata.sources' => [
    ['type' => 'flatfile'],
    ['type' => 'pdo'],
],
```

--------------------------------

### Flatten Multi-Value Attribute to Delimited String

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_cardinalitysingle.md

This example first copies 'eduPersonAffiliation' to 'eduPersonAffiliationWithCommas' using 'core:AttributeCopy'. Then, it uses 'core:CardinalitySingle' with 'flatten' and 'flattenWith' parameters to create a single, comma-separated string from the 'eduPersonAffiliationWithCommas' attribute.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeCopy',
            'eduPersonAffiliation' => 'eduPersonAffiliationWithCommas',
        ],
        51 => [
            'class' => 'core:CardinalitySingle',
            'flatten' => ['eduPersonAffiliationWithCommas'],
            'flattenWith' => ',',
        ],
    ],
```

--------------------------------

### Copy Base Header Template

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-theming.md

Copy the default header template file from SimpleSAMLphp's base templates into your custom theme's directory. This serves as a starting point for your custom header.

```bash
cp templates/_header.twig modules/mymodule/themes/fancytheme/default/
```

--------------------------------

### Configuring Service Provider EntityID in authsources.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-2.0.md

Example of how to set the 'entityID' for a Service Provider (SP) in the SimpleSAMLphp authsources.php configuration file. The entityID uniquely identifies the SP in SAML interactions.

```php
...
    'default-sp' => [
        'saml:SP',
        // The entity ID of this SP.
        'entityID' => 'https://example.com/the-service/',
...
```

--------------------------------

### Translate IdP Name to Multiple Languages

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-remote.md

This snippet demonstrates how to provide translated names for an IdP. It shows an example of setting the 'name' option with different translations for English and Norwegian.

```php
'name' => [
    'en' => 'A service',
    'no' => 'En tjeneste',
]
```

--------------------------------

### Configure Scoped Issuer Filter

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/authproc_scopedissuer.md

Example configuration for the saml:ScopedIssuer filter in SimpleSAMLphp's authproc array. It uses the 'userPrincipalName' attribute and a pattern to generate the scoped issuer.

```php
    'authproc' => [
        50 => [
            'class' => 'saml:ScopedIssuer',
            'scopeAttribute' => 'userPrincipalName',
            'pattern' => 'https://%1$s/issuer',
        ],
    ],
```

--------------------------------

### \SimpleSAML\Auth\Simple Constructor

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Initializes a \SimpleSAML\Auth\Simple object, specifying the authentication source to be used. The authentication source must be defined in \`config/authsources.php\` and be of type saml:SP.

```APIDOC
## \SimpleSAML\Auth\Simple Constructor

### Description
Initializes a \SimpleSAML\Auth\Simple object.

### Parameters
* **authSource** (string) - Required - The ID of the authentication source to be used. This must exist in `config/authsources.php` and be of type saml:SP.

### Example
```php
$auth = new \SimpleSAML\Auth\Simple('default-sp');
```
```

--------------------------------

### Instantiate SimpleSAML\Auth\Simple

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Initializes a SimpleSAML\Auth\Simple object using the ID of an authentication source defined in config/authsources.php.

```php
$auth = new \SimpleSAML\Auth\Simple('default-sp');
```

--------------------------------

### Clone SimpleSAMLphp Git Repository

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Use this command to clone the entire SimpleSAMLphp git repository. This is the first step in preparing for a new release.

```bash
% git clone https://github.com/simplesamlphp/simplesamlphp
```

--------------------------------

### Instantiating Utility Classes in SimpleSAMLphp 2.0

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-2.0.md

Demonstrates the shift from static method calls to instantiating utility classes in SimpleSAMLphp 2.0. This change applies to classes like \SimpleSAML\Utils\Arrays, \SimpleSAML\Utils\Auth, and others.

```php
// Old style
$x = \SimpleSAML\Utils\Arrays::arrayize($someVar)
```

```php
// New style
$arrayUtils = new \SimpleSAML\Utils\Arrays();
$x = $arrayUtils->arrayize($someVar);
```

--------------------------------

### Configure SP Entity Attributes for Data Protection Code of Conduct

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-attributes.md

Example configuration for a service provider in `authsources.php` to declare support for the Géant Data Protection Code of Conduct entity category.

```php
'saml:SP' => [
        ...
        'EntityAttributes' => [
            'http://macedir.org/entity-category' => [
                'http://www.geant.net/uri/dataprotection-code-of-conduct/v1'
            ]
        ],
        'UIInfo' =>[
                'DisplayName' => [
                    'en' => 'English name',
                    'es' => 'Nombre en Español',
                ],
                'Description' => [
                    'en' => 'English description',
                    'es' => 'Descripción en Español',
                ],
                'InformationURL' => [
                    'en' => 'http://example.com/info/en',
                    'es' => 'http://example.com/info/es',
                ],
                'PrivacyStatementURL' => [
                    'en' => 'http://example.com/privacy/en',
                    'es' => 'http://example.com/privacy/es',
                ],
        ]
    ],
```

--------------------------------

### Configure Web Proxy for HTTP/S Requests

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-advancedfeatures.md

This configuration option in config/config.php allows SimpleSAMLphp to send HTTP/S requests via a web proxy. Authentication for the proxy can also be configured.

```php
'proxy' => null,
'proxy.auth' => false,
```

--------------------------------

### Retrieve AuthenticatingAuthority from AuthData

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-scoping.md

Get the list of authentication authorities involved in the user's authentication. This information is retrieved using the getAuthData method on a SimpleSAMLphp authentication source object.

```php
# Get the authentication source.
$as = new \SimpleSAML\Auth\Simple();

# Get the AuthenticatingAuthority
$aa = $as->getAuthData('saml:AuthenticatingAuthority');
```

--------------------------------

### Module Enable Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

Enabling a custom module in SimpleSAMLphp's config.php file.

```php
'module.enable' => [
    'mymodule' => true,
    /* Other enabled modules follow. */
],
```

--------------------------------

### Generate Internet2 Compatible TargetedID

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_targetedid.md

Configure the core:TargetedID filter to generate the eduPersonTargetedID attribute in SAML 2 NameID format for Internet2 compatibility. This example is typically placed within the IdP hosted configuration.

```php
$metadata['urn:x-simplesamlphp:example-idp'] = [
    'host' => '__DEFAULT__',
    'auth' => 'example-static',

    'authproc' => [
        60 => [
            'class' => 'core:TargetedID',
            'nameId' => true,
        ],
        90 => [
            'class' => 'core:AttributeMap',
            'name2oid',
        ],
    ],
    'attributes.NameFormat' => 'urn:oasis:names:tc:SAML:2.0:attrname-format:uri',
    'attributeencodings' => [
        'urn:oid:1.3.6.1.4.1.5923.1.1.1.10' => 'raw', /* eduPersonTargetedID with oid NameFormat. */
    ],
];
```

--------------------------------

### Implementing a Custom Metadata Storage Backend

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/List-of-tasks

This code snippet demonstrates how to extend the \SimpleSAML\Metadata\MetaDataStorageSource class to create a custom metadata storage backend. The class name can then be specified in the configuration.

```php
class CustomMetaDataStorage extends \SimpleSAML\Metadata\MetaDataStorageSource
{
    // ... implementation ...
}
```

--------------------------------

### Create Symlink to Public Directory

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Create a symbolic link from your web-accessible directory (e.g., 'public_html') to the 'simplesamlphp/public' folder.

```bash
cd ~/public_html
ln -s ../simplesamlphp/public simplesaml
```

--------------------------------

### Enable Admin Module and Set Password

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-testing-install.md

Configure SimpleSAMLphp to enable the admin module and set a password for accessing the admin interface. This is necessary for testing and viewing configuration details.

```php
    'auth.adminpassword' => '123',
    ...
    'module.enable' => [
        'admin' => true,
        ...

```

--------------------------------

### SimpleSAMLphp SP Configuration for HTTP-Artifact Binding

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-artifact-sp.md

Configure your SimpleSAMLphp SP to request the HTTP-Artifact binding from the IdP. Ensure the `privatekey` and `certificate` options are set to the generated files for SSL client authentication.

```php
'artifact-sp' => [
        'saml:SP',
        'ProtocolBinding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Artifact',
        'privatekey' => 'sp.example.org.pem',
        'certificate' => 'sp.example.org.crt',
    ],
```

--------------------------------

### Create Custom Module Directory

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

This command creates the directory for a new custom module in SimpleSAMLphp.

```bash
cd modules
mkdir mymodule
```

--------------------------------

### Enable Metadata Signing

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-advancedfeatures.md

Configuration to enable metadata signing in SimpleSAMLphp. This involves setting the enable flag to TRUE and providing paths to the private key and certificate.

```php
'metadata.sign.enable' => TRUE,
'metadata.sign.privatekey' => 'file:/path/to/your/private.key',
'metadata.sign.privatekey_pass' => 'your_passphrase',
'metadata.sign.certificate' => 'file:/path/to/your/certificate.crt',
```

--------------------------------

### Copy SAML2Int Configuration Template

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/saml2int.md

Copy the distribution template to create your local SAML2Int configuration file.

```bash
cp config/saml2int.conf.php.dist config/saml2int.conf.php
```

--------------------------------

### Preselect AuthSource via URL Parameter

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/multiauth/docs/multiauth.md

Demonstrates how to use the 'source' URL parameter to preselect an authentication source when accessing a service.

```url
https://example.com/service/?source=saml
```

--------------------------------

### Process State with Exception Handling

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-errorhandling.md

Demonstrates how to set up the state array to handle exceptions during processing. It configures an exception handler URL and then attempts to process the state, catching any `\SimpleSAML\Error\Exception` that may occur.

```php
if (array_key_exists("__Exception_ID__", $_REQUEST)) {
    $state = \SimpleSAML\Auth\State::loadExceptionState();
    $exception = $state["__Exception_Data__"];

    /* Handle exception... */
    [...] 
}

$procChain = [...];

$state = [
    'ReturnURL' => \SimpleSAML\Utils\HTTP::getSelfURLNoQuery(),
    '__Exception_Handler_URL__' => \SimpleSAML\Utils\HTTP::getSelfURLNoQuery(),
    [...],
]

try {
    $procChain->processState($state);
} catch (\SimpleSAML\Error\Exception $e) {
    /* Handle exception. */
    [...];
}
```

--------------------------------

### Configure Bridge Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-advancedfeatures.md

This configuration snippet shows how to set up an authentication source for bridging between protocols. It specifies the default SP to use for authentication.

```php
'auth' => 'default-sp',
```

--------------------------------

### Import Flatfile Metadata to PDO Database

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-pdostoragehandler.md

Execute this script to migrate all metadata from your flatfile sources into the configured PDO database. Existing metadata for an entity ID will be overwritten.

```bash
php bin/importPdoMetadata.php
```

--------------------------------

### Organization Information Configuration with Translations

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Configure organizational details including name, display name, and URL, with multi-language support.

```php
'OrganizationName' => [
            'en' => 'Voorbeeld Organisatie Foundation b.a.',
            'nl' => 'Stichting Voorbeeld Organisatie b.a.',
        ],
        'OrganizationDisplayName' => [
            'en' => 'Example organization',
```

--------------------------------

### Configure New Key for Service Provider

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/keyrollover.md

Add the new private key, certificate, and passphrase to the 'authsources.php' configuration file for a SimpleSAMLphp service provider. The new key details are prefixed with 'new_'.

```php
    'default-sp' => [
        'saml:SP',
        'privatekey' => 'old.pem',
        'certificate' => 'old.crt',
        // When private key is passphrase protected.
        'privatekey_pass' => '<old-secret>',

        'new_privatekey' => 'new.pem',
        'new_certificate' => 'new.crt',
        // When new private key is passphrase protected.
        'new_privatekey_pass' => '<new-secret>',
    ],
```

--------------------------------

### Extract and Move SimpleSAMLphp Archive

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Extract the SimpleSAMLphp archive into your home directory and rename the folder to 'simplesamlphp'.

```bash
cd ~
tar xzf simplesamlphp-1.x.y.tar.gz
mv simplesamlphp-1.x.y simplesamlphp
```

--------------------------------

### Dispatching a SimpleSAMLphp Event

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-modules.md

Demonstrates how to dispatch an event using the ModuleEventDispatcherFactory and retrieve potentially modified state from the returned event object.

```php
    $eventDispatcher = ModuleEventDispatcherFactory::getInstance();
    $event = $eventDispatcher->dispatch(new ConfigPageEvent($t));
    $t = $event->getTemplate();
```

--------------------------------

### Generate Private Key and Certificate using OpenSSL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-artifact-sp.md

Use the `openssl` command-line utility to generate a private key and a self-signed certificate for SSL client authentication. The certificate is valid for 10 years.

```bash
openssl req -newkey rsa:3072 -new -x509 -days 3652 -nodes -out sp.example.org.crt -keyout sp.example.org.pem
```

--------------------------------

### Authentication Source Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

Configuration for a custom authentication source instance in SimpleSAMLphp's authsources.php file.

```php
'myauthinstance' => [
    'mymodule:MyAuth',
    'dsn' => 'mysql:host=sql.example.org;dbname=userdatabase',
    'username' => 'db_username',
    'password' => 'secret_db_password',
],
```

--------------------------------

### Basic Configuration Format

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

This shows the general structure for configuring the AttributeConditionalAdd authproc, including optional flags, attributes to add, and conditions.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            '%<flags>',
            'attributes' => [
                'attribute' => ['value'],
                [...],
            ],
            'conditions' => [],
        ],
    ],
```

--------------------------------

### Checkout a Specific Release Tag

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install-repo.md

Checkout a newer release tag to upgrade SimpleSAMLphp to a specific version.

```bash
git checkout v2.2.2
```

--------------------------------

### Replace Old Version with New for Upgrade

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Replaces the old SimpleSAMLphp directory with the newly extracted version during an upgrade.

```bash
cd /var
mv simplesamlphp simplesamlphp.old
mv simplesamlphp-x.y.z simplesamlphp
```

--------------------------------

### Register SimpleSAMLphp Classes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

Include this line at the beginning of your application to register the SimpleSAMLphp classes with the PHP autoloader.

```php
require_once('../../src/_autoload.php');
```

--------------------------------

### Push All Tags

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Push all tags, including the new release tag, to the remote repository to trigger the build process.

```shell
% git push --tags
```

--------------------------------

### PHP Array Syntax Comparison

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-1.17.md

Illustrates the equivalence between old-style and modern PHP array syntax. Both formats are supported.

```php
// Old style array syntax
$config = array(
    'authproc' => array(
        60 => 'class:etc'
    ),
    'other example' => 1
);

// Current style array syntax
$config = [
    'authproc' => [
        60 => 'class:etc'
    ],
    'other example' => 1
];
```

--------------------------------

### Set Authentication Source for SAML IdP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-modules.md

Configures a SAML 2.0 IdP to use the 'example-static' authentication source.

```php
'https://example.org/saml-idp' => [
        'host' => '__DEFAULT__',
        'privatekey' => 'example.org.pem',
        'certificate' => 'example.org.crt',
        'auth' => 'example-static',
    ],
```

--------------------------------

### Configure Hosted IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp.md

Minimal configuration for a SimpleSAMLphp Identity Provider. This file defines the IdP's hostname, private key, certificate, and the authentication source to use for user authentication.

```php
<?php

$metadata['https://example.org/saml-idp'] = [
    /*
     * The hostname for this IdP. This makes it possible to run multiple
     * IdPs from the same configuration. '__DEFAULT__' means that this one
     * should be used by default.
     */
    'host' => '__DEFAULT__',

    /*
     * The private key and certificate to use when signing responses.
     * These can be stored as files in the cert-directory or retrieved
     * from a database.
     */
    'privatekey' => 'example.org.pem',
    'certificate' => 'example.org.crt',

    /*
     * The authentication source which should be used to authenticate the
     * user. This must match one of the entries in config/authsources.php.
     */
    'auth' => 'example-userpass',
];

```

--------------------------------

### Enable SAML 2.0 IdP Functionality

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-googleapps.md

Enable the SAML 2.0 IdP functionality in the SimpleSAMLphp configuration.

```php
'enable.saml20-idp' => true,
```

--------------------------------

### Configure Available Languages in SimpleSAMLphp

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Add new language codes to the 'language.available' array in 'config.php' to enable multi-language support. Set the 'language.default' to specify the fallback language.

```php
/*
 * Languages available and which language is default
 */
'language.available' => ['en', 'no', 'da', 'es', 'xx'],
'language.default'   => 'en',
```

--------------------------------

### Configure New Key for Identity Provider

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/keyrollover.md

Add the new private key, certificate, and passphrase to the 'saml20-idp-hosted.php' metadata file for a SimpleSAMLphp identity provider. The new key details are prefixed with 'new_'.

```php
    $metadata['urn:x-simplesamlphp:idp'] = [
        'host' => '__DEFAULT__',
        'auth' => 'example-userpass',
        'privatekey' => 'old.pem',
        'certificate' => 'old.crt',
        // When private key is passphrase protected.
        'privatekey_pass' => '<old-secret>',

        'new_privatekey' => 'new.pem',
        'new_certificate' => 'new.crt',
        // When new private key is passphrase protected.
        'new_privatekey_pass' => '<new-secret>',
    ];
```

--------------------------------

### SP with Encryption and Signing

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Configure an SP to accept encrypted assertions and to sign/validate all messages using provided certificates and keys.

```php
'example-enc' => [
    'saml:SP',
    'entityID' => 'https://myapp.example.org',

    'certificate' => 'example.crt',
    'privatekey' => 'example.key',
    'privatekey_pass' => 'secretpassword',
    'redirect.sign' => true,
    'redirect.validate' => true,
],
```

--------------------------------

### Clone SimpleSAMLphp Repository

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install-repo.md

Clone the SimpleSAMLphp repository from GitHub, specifying a release tag for stability.

```bash
git clone --branch <tag_name> https://github.com/simplesamlphp/simplesamlphp.git simplesamlphp
```

--------------------------------

### Enable Cron Module

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/cron/docs/cron.md

Enable the cron module by setting 'cron' to true in the 'module.enable' configuration array in config.php.

```php
'module.enable' => [
     'cron' => true,
     …
],
```

--------------------------------

### Minimal authsources.php for a Service Provider

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

This is a basic configuration file for a Service Provider. It defines a default authentication source with a unique entity ID.

```php
<?php
$config = [

    /* This is the name of this authentication source, and will be used to access it later. */
    'default-sp' => [
        'saml:SP',
        'entityID' => 'https://myapp.example.org/',
    ],
];

```

--------------------------------

### Minimal SP Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

A basic configuration for a Service Provider with only the essential 'saml:SP' type and an entity ID.

```php
'example-minimal' => [
    'saml:SP',
    'entityID' => 'https://myapp.example.org',
],
```

--------------------------------

### Create Theme Directory Structure

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-theming.md

Within your custom module, create the necessary directory structure for your theme, including a 'default' subdirectory for template overrides.

```bash
cd modules/mymodule
mkdir -p themes/fancytheme/default/
```

--------------------------------

### Configure ProfileAuth for User Testing

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-testing-install.md

Set up the ProfileAuth authentication source to test login with predefined user profiles. This allows for easy simulation of different user types in a testing environment.

```php
    'module.enable' => [
        'admin' => true,
        'exampleauth' => true,
        ...
    ],

    'profileauth' => [
        'exampleauth:UserClick',
        'users' => [
            [
                'uid' => ['student'],
                'displayName' => ['Student'],
                'eduPersonAffiliation' => ['student', 'member'],
            ],
            [
                'uid' => ['employee'],
                'displayName' => ['Employee'],
                'eduPersonAffiliation' => ['employee', 'member'],
            ],
        ],
    ],

```

--------------------------------

### Configure Certificate in authsources.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

Update your Service Provider's entry in authsources.php to include references to the generated private key and certificate files.

```php
    'default-sp' => [
        'saml:SP',
        'entityID' => 'https://myapp.example.org/',
        'privatekey' => 'saml.pem',
        'certificate' => 'saml.crt',
    ],

```

--------------------------------

### Enable DebugSP Module

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/debugsp/docs/debugsp.md

To enable the DebugSP module, add its name to the 'module.enable' array in your SimpleSAMLphp configuration file (`config.php`).

```shell
'module.enable' => [
     'debugsp' => true,
     …
],
```

--------------------------------

### PHP Configuration for Single Entity Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-attributes.md

Illustrates defining a single entity attribute with its values in SimpleSAMLphp configuration.

```php
'EntityAttributes' => [
    'urn:simplesamlphp:v1:simplesamlphp' => ['is', 'really', 'cool'],
],

```

--------------------------------

### SP Name Configuration with Translations

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Configure the name of the Service Provider, supporting multi-language translations.

```php
'name' => [
            'en' => 'A service',
            'no' => 'En tjeneste',
        ],
```

--------------------------------

### Service Provider RegistrationInfo Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-rpi.md

Configure RegistrationInfo for a hosted service provider in metadata/saml20-idp-hosted.php. Includes authority, instant, and policy URLs.

```php
'default-sp' => [
    'saml:SP',
    'entityID' => NULL,
    ...
    'RegistrationInfo' => [
        'RegistrationAuthority' => 'urn:mace:sp.example.org',
        'RegistrationInstant' => '2008-01-17T11:28:03.577Z',
        'RegistrationPolicy' => ['en' => 'http://sp.example.org/policy', 'es' => 'http://sp.example.org/politica'],
    ],
],
```

--------------------------------

### Implement Basic Username/Password Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

This PHP class implements a basic username and password authentication source. It extends UserPassBase and hardcodes credentials for demonstration.

```php
<?php

namespace SimpleSAML\Module\mymodule\Auth\Source;

class MyAuth extends \SimpleSAML\Module\core\Auth\UserPassBase
{
    protected function login(string $username, string $password): array
    {
        if ($username !== 'theusername' || $password !== 'thepassword') {
            throw new \SimpleSAML\Error\Error(\SimpleSAML\Error\ErrorCodes::WRONGUSERPASS);
        }

        return [
            'uid' => ['theusername'],
            'displayName' => ['Some Random User'],
            'eduPersonAffiliation' => ['member', 'employee'],
        ];
    }
}
```

--------------------------------

### Create Signed Git Tag

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Create a PGP-signed tag for the release version. Ensure GPG is configured for signing.

```shell
% git tag -s -a vX.Y.Z -m 'Releasing version X.Y.Z'
```

--------------------------------

### Commit Version Changes and Push

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Stage all modified files, commit the changes with a version message, and push to the repository.

```shell
% git add composer.json composer.lock docs/simplesamlphp-changelog.md extra/simplesamlphp.spec src/SimpleSAML/Configuration.php
% git status

% git commit -m "Setting version number to X.Y"
% git push origin
```

--------------------------------

### Fetch Latest Repository Information

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install-repo.md

Update the local repository information by fetching from the origin.

```bash
git fetch origin
```

--------------------------------

### Configure WarnShortSSOInterval

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_warnshortssointerval.md

Add the 'core:WarnShortSSOInterval' authentication processor to your SimpleSAMLphp configuration to enable warnings for short SSO intervals.

```php
'authproc' => [
    50 => [
        'class' => 'core:WarnShortSSOInterval',
    ],
],
```

--------------------------------

### Logout with Return Parameters and State Handling

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Logs the user out, specifying return parameters and a state stage for post-logout processing. The `cleanup()` method is called to clear the session.

```php
$auth->logout([
    'ReturnTo' => 'https://sp.example.org/logged_out.php',
    'ReturnStateParam' => 'LogoutState',
    'ReturnStateStage' => 'MyLogoutState',
]);
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
```

--------------------------------

### Configure Identity Provider Discovery Extension in authsources.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-idpdisc.md

Add the 'DiscoveryResponse' configuration to your SP's entry in `authsources.php` to enable Identity Provider Discovery. This specifies the binding, location, and default status for the discovery response.

```php
<?php
$config = [

    'default-sp' => [
        'saml:SP',

        'DiscoveryResponse' => [
            [
                'index' => 1,
                'Binding' => 'urn:oasis:names:tc:SAML:profiles:SSO:idp-discovery-protocol',
                'Location' => 'https://simplesamlphp.org/some/endpoint',
                'isDefault' => true,
            ],
        ],
        /* ... */
    ],
];

```

--------------------------------

### SimpleSAMLphp SP Configuration for RelayState

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp.md

Configure the 'RelayState' parameter directly in the SP's 'authsources.php' file. This sets the default redirect URL after successful authentication.

```php
'default-sp' => [
    'saml:SP',
    'RelayState' => 'https://sp.example.org/welcome.php',
],
```

--------------------------------

### Define Default SP Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-advancedfeatures.md

This configuration defines the 'default-sp' authentication source, specifying that it should use the 'saml:SP' handler.

```php
'default-sp' => [
    'saml:SP',
],
```

--------------------------------

### SP with Attribute Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Configure an SP to request specific attributes like eduPersonPrincipalName and mail, marking some as required. It also shows how to specify friendly names and NameFormat.

```php
'example-attributes => [
    'saml:SP',
    'entityID' => 'https://myapp.example.org',
    'name' => [
        'en' => 'Example service',
        'no' => 'Eksempeltjeneste',
    ],
    'attributes' => [
        'eduPersonPrincipalName',
        'mail',
        'sn' => 'urn:oid:2.5.4.4',
        'givenName' => 'urn:oid:2.5.4.42',
    ],
    'attributes.required' => [
        'eduPersonPrincipalName',
    ],
    'attributes.NameFormat' => 'urn:oasis:names:tc:SAML:2.0:attrname-format:basic',
],
```

--------------------------------

### Identity Provider RegistrationInfo Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-rpi.md

Configure RegistrationInfo for a hosted identity provider. Includes authority and instant, with optional policy.

```php
$metadata['https://example.org/saml-idp'] = [
    'host' => '__DEFAULT__',
    ...
    'RegistrationInfo' => [
        'RegistrationAuthority' => 'urn:mace:idp.example.org',
        'RegistrationInstant' => '2008-01-17T11:28:03.577Z',
    ],
];
```

--------------------------------

### Configure Redis Sentinels

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Sets up connection details for Redis servers managed by Redis-Sentinel. Includes options for sentinel hostnames, ports, and password protection.

```php
[
    'tcp://[yoursentinel1]:[port]',
    'tcp://[yoursentinel2]:[port]',
    'tcp://[yoursentinel3]:[port]',
]
```

--------------------------------

### Using samlp:Extensions with Custom Data

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Add custom SAML extensions to an authentication request using XML DOM manipulation and SimpleSAML's XML chunking.

```php
$dom = \SimpleSAML\XML\DOMDocumentFactory::create();
$ce = $dom->createElementNS('http://www.example.com/XFoo', 'xfoo:test', 'Test data!');
$ext[] = new \SimpleSAML\XML\Chunk($ce);

$auth = new \SimpleSAML\Auth\Simple('default-sp');
$auth->login([
    'saml:Extensions' => $ext,
]);
```

--------------------------------

### Configure Custom Authentication Source Instance

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

This configuration snippet adds a custom authentication source instance named 'myauthinstance' to SimpleSAMLphp's authsources.php.

```php
'myauthinstance' => [
    'mymodule:MyAuth',
]
```

--------------------------------

### Add and Commit Changelog

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Stage and commit updates to the changelog file.

```shell
% git add docs/simplesamlphp-changelog.md
% git commit -m "update changelog"
```

--------------------------------

### Implement Constructor for Custom Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

The constructor parses configuration, validates username and password, and stores them in class properties.

```php
public function __construct($info, $config)
{
    parent::__construct($info, $config);

    if (!is_string($config['username'])) {
        throw new Exception('Missing or invalid username option in config.');
    }
    $this->username = $config['username'];

    if (!is_string($config['password'])) {
        throw new Exception('Missing or invalid password option in config.');
    }
    $this->password = $config['password'];
}

```

--------------------------------

### Configure ServerName for Apache

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Developing-on-Ubuntu

Fixes the 'Could not reliably determine the server's fully qualified domain name' error in Apache by setting a default ServerName.

```bash
echo "ServerName localhost" | sudo tee /etc/apache2/conf-available/fqdn.conf
sudo a2enconf fqdn
sudo systemctl restart apache2
```

--------------------------------

### Basic Hosted IdP Metadata Structure

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-hosted.md

Defines the fundamental structure of the hosted IdP metadata file, showing how to register entity IDs and their corresponding configurations.

```php
<?php
/* The index of the array is the entity ID of this IdP. */
$metadata['entity-id-1'] = [
    'host' => 'idp.example.org',
    /* Configuration options for the first IdP. */
];
$metadata['entity-id-2'] = [
    'host' => '__DEFAULT__',
    /* Configuration options for the default IdP. */
];
/* ... */

```

--------------------------------

### Set Base URL Path in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Configure the canonical URL for your SimpleSAMLphp deployment. Ensure it uses HTTPS for security, especially when behind a reverse proxy.

```php
'baseurlpath' => 'https://your.canonical.host.name/simplesaml/',
```

--------------------------------

### Move Public Directory for SimpleSAMLphp

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Use this command to move the 'public' directory if symlinking fails due to Apache configuration. This ensures the SimpleSAMLphp public-facing files are correctly placed.

```bash
cd ~/public_html
mv ../simplesamlphp/public simplesaml
```

--------------------------------

### Enable Holder-of-Key SSO Profile in SimpleSAMLphp SP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-hok-sp.md

Set 'saml20.hok.assertion' to TRUE and specify the 'ProtocolBinding' for the Holder-of-Key profile in the SP configuration.

```php
'hok-sp' => [
    'saml:SP',
    'saml20.hok.assertion' => TRUE,
    'ProtocolBinding' => 'urn:oasis:names:tc:SAML:2.0:profiles:holder-of-key:SSO:browser',
],
```

--------------------------------

### Enable ECP Profile in IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-ecp-idp.md

Add the 'saml20.ecp' option to your 'saml20-idp-hosted' metadata file to enable the IdP to send ECP assertions. Ensure that authentication filters do not require user interaction.

```php
$metadata['https://example.org/saml-idp'] = [
    [....]
    'auth' => 'example-userpass',
    'saml20.ecp' => true,
];
```

--------------------------------

### Nginx Server Block Configuration for SimpleSAMLphp

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Configure an Nginx server block to serve SimpleSAMLphp, including SSL settings and FastCGI parameters for PHP processing.

```nginx
server {
    listen 443 ssl; 
    server_name idp.example.com;
    index index.php;

    ssl_certificate        /etc/pki/tls/certs/idp.example.com.crt;
    ssl_certificate_key    /etc/pki/tls/private/idp.example.com.key;
    ssl_protocols          TLSv1.3 TLSv1.2;
    ssl_ciphers            EECDH+AESGCM:EDH+AESGCM;

    location ^~ /simplesaml {
        alias /var/simplesamlphp/public;

        location ~^(?<prefix>/simplesaml)(?<phpfile>.+?\.php)(?<pathinfo>/.*)?$ {
            include          fastcgi_params;
            fastcgi_pass     $fastcgi_pass;
            fastcgi_param SCRIPT_FILENAME $document_root$phpfile;

            # Must be prepended with the baseurlpath
            fastcgi_param SCRIPT_NAME /simplesaml$phpfile;

            fastcgi_param PATH_INFO $pathinfo if_not_empty;
        }
    }
}
```

--------------------------------

### Configure Authentication Source in authsources.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

Add your custom authentication source to 'config/authsources.php', specifying the class and configuration options.

```php
'myauthinstance' => [
    'mymodule:MyAuth',
    'username' => 'theconfigusername',
    'password' => 'theconfigpassword',
],

```

--------------------------------

### Configure Custom Theme Controller

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-theming.md

Set a custom theme controller in config.php to manage specific theme requirements.

```php
'theme.controller' => '\\SimpleSAML\\Module\\mymodule\\FancyThemeController',
```

--------------------------------

### Copy Cron Configuration File

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/cron/docs/cron.md

Copy the default cron configuration file to the global config directory to customize settings.

```shell
[user@simplesamlphp] cd /var/simplesamlphp
[user@simplesamlphp simplesamlphp] cp modules/cron/config/module_cron.php.dist config/module_cron.php
```

--------------------------------

### PHP Configuration with Custom NameFormat

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-attributes.md

Shows how to specify a custom NameFormat for an entity attribute using curly braces in the key name.

```php
'EntityAttributes' => [
    '{urn:simplesamlphp:v1}foo' => ['bar'],
],

```

--------------------------------

### Enable HoK Assertion in SimpleSAMLphp IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-hok-idp.md

Add the 'saml20.hok.assertion' option to your 'saml20-idp-hosted' metadata to enable the IdP to send HoK assertions.

```php
$metadata['https://example.org/saml-idp'] = [
    [....]
    'auth' => 'example-userpass',
    'saml20.hok.assertion' => true,
];
```

--------------------------------

### SimpleSAMLphp baseurlpath Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Set the 'baseurlpath' option in SimpleSAMLphp's config.php to match the alias defined in the web server configuration.

```php
$config = [
    [...]
    'baseurlpath' => 'simplesaml/',
    [...]
]
```

--------------------------------

### Enable Custom Module in SimpleSAMLphp Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

This configuration snippet enables the custom 'mymodule' in SimpleSAMLphp's main config.php file.

```php
'module.enable' => [
    'mymodule' => true,
    /* Other enabled modules follow. */
]
```

--------------------------------

### Add Multiple Attributes with Multiple Values

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Demonstrates how to specify multiple attributes, where some attributes can have multiple values. This is useful for setting various user affiliations or properties.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'attributes' => [
                'eduPersonPrimaryAffiliation' => 'student',
                'eduPersonAffiliation' => ['student', 'employee', 'members'],
            ],
        ],
    ],
```

--------------------------------

### Configure SAML SP Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/multiauth/docs/multiauth.md

Defines a 'saml:SP' authentication source, typically referenced by a MultiAuth source.

```php
'example-saml' => [
    'saml:SP',
    'entityId' => 'https://myapp.example.org',
    'idp' => 'my-idp',
],
```

--------------------------------

### Set Administrator Password in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Set a secure administrator password to access the SimpleSAMLphp web interface. Use the bin/pwgen.php script to generate a safe hash.

```php
'auth.adminpassword' => 'setnewpasswordhere',
```

--------------------------------

### Configure PHP Session Handler Options

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Customize PHP session handler settings in SimpleSAMLphp. Ensure 'session.phpsession.cookiename' is unique if other applications use PHP sessions.

```php
'session.phpsession.cookiename' => null,
'session.phpsession.savepath' => null,
'session.phpsession.httponly' => true,
```

--------------------------------

### Generate Signing Certificate and Key

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-googleapps.md

Use OpenSSL to generate a new RSA private key and a self-signed X.509 certificate for signing SAML messages. The certificate is valid for 10 years.

```bash
openssl req -newkey rsa:3072 -new -x509 -days 3652 -nodes -out googleworkspaceidp.crt -keyout googleworkspaceidp.pem
```

--------------------------------

### Complete SAML Metadata XML with Entity Attributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-attributes.md

The full XML metadata for an entity, including the 'EntityAttributes' extension, demonstrating how SimpleSAMLphp generates the SAML attributes based on the configuration.

```xml
<?xml version="1.0"?>
<md:EntityDescriptor xmlns:md="urn:oasis:names:tc:SAML:2.0:metadata" xmlns:mdattr="urn:oasis:names:tc:SAML:metadata:attribute" xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:mdui="urn:oasis:names:tc:SAML:metadata:ui" xmlns:ds="http://www.w3.org/2000/09/xmldsig#" entityID="https://example.com/saml-idp">
  <md:Extensions>
    <mdattr:EntityAttributes xmlns:mdattr="urn:oasis:names:tc:SAML:metadata:attribute">
      <saml:Attribute xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" Name="urn:simplesamlphp:v1:simplesamlphp" NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri">
        <saml:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:string">is</saml:AttributeValue>
        <saml:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:string">really</saml:AttributeValue>
        <saml:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:string">cool</saml:AttributeValue>
      </saml:Attribute>
      <saml:Attribute xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" Name="foo" NameFormat="urn:simplesamlphp:v1">
        <saml:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:string">bar</saml:AttributeValue>

```

--------------------------------

### Configure Apache for Client Certificate Authentication

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-hok-idp.md

Enable TLS, specify server certificates, and configure Apache to optionally request and export client certificates for HoK SSO.

```apacheconf
SSLEngine on
SSLCertificateFile /etc/openssl/certs/server.crt
SSLCertificateKeyFile /etc/openssl/private/server.key
SSLVerifyClient optional_no_ca
SSLOptions +ExportCertData
```

--------------------------------

### Configure SP AssertionConsumerService for HoK Profile

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-hok-idp.md

Define the complex endpoint format in 'saml20-sp-remote' metadata on the IdP to specify the AssertionConsumerService endpoint supporting the HoK profile.

```php
'AssertionConsumerService' => [
    [
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST',
        'Location' => 'https://sp.example.org/simplesaml/module.php/saml/sp/saml2-acs.php/default-sp',
        'index' => 0,
    ],
    [
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:profiles:holder-of-key:SSO:browser',
        'Location' => 'https://sp.example.org/simplesaml/module.php/saml/sp/saml2-acs.php/default-sp',
        'index' => 4,
    ],
],
```

--------------------------------

### Update SP Metadata with HoK SingleSignOnService Endpoint

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-hok-idp.md

Configure the 'saml20-idp-remote' metadata on SimpleSAMLphp SPs to include the HoK-specific SingleSignOnService endpoint.

```php
'SingleSignOnService' => [
    [
        'hoksso:ProtocolBinding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect',
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:profiles:holder-of-key:SSO:browser',
        'Location' => 'https://idp.example.org/simplesaml/module.php/saml/idp/singleSignOnService',
        'attributes' => [
            [
                'namespaceURI' => 'urn:oasis:names:tc:SAML:2.0:profiles:holder-of-key:SSO:browser',
                'namespacePrefix' => 'hoksso',
                'attrName' => 'ProtocolBinding',
                'attrValue' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect',
            ],
        ],
    ],
    [
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect',
        'Location' => 'https://idp.example.org/simplesaml/module.php/saml/idp/singleSignOnService',
    ],
],
```

--------------------------------

### Enable/Disable Modules in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Control which modules are enabled or disabled by setting their status to true, false, or null in the 'module.enable' configuration.

```php
'module.enable' => [
    'exampleauth' => true, // Setting to TRUE enables.
    'saml' => false, // Setting to FALSE disables.
    'core' => null, // Unset or NULL uses default for this module.
],
```

--------------------------------

### Configure SAML 2.0 SP Remote Metadata for Google Workspace

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-googleapps.md

Sets up the remote metadata for Google Workspace, specifying the Assertion Consumer Service URL, NameID format, and attribute processing for user identification. Modify the entityID and ACS URL to match your Google Workspace domain.

```php
/*
 * This example shows an example config that works with Google Workspace for education.
 * You send the email address that identifies the user from your IdP in the SAML Name ID.
 */
$metadata['https://www.google.com/a/g.feide.no'] = [
    'AssertionConsumerService' => 'https://www.google.com/a/g.feide.no/acs',
    'NameIDFormat' => 'urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress',
    'simplesaml.attributes' => false,
    'authproc' => [
        1 => [
          'class' => 'saml:AttributeNameID',
          'identifyingAttribute' => 'mail',
          'Format' => 'urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress',
        ],
    ],
];
```

--------------------------------

### Auth Proc Filter Configuration with Parameters

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-authproc.md

Configuring an Auth Proc Filter with specific parameters. This format is required when passing options like 'store', 'focus', or 'checked' to the filter.

```php
20 => [
    'class' => 'core:TargetedID'
],
```

```php
90 => [
    'class' => 'consent:Consent',
    'store' => 'consent:Cookie',
    'focus' => 'yes',
    'checked' => true,
],
```

--------------------------------

### Write to Database with Prepared Statement

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-database.md

Insert data into a table using a prepared statement. Values are bound as PDO::PARAM_STR by default.

```php
$table = $db->applyPrefix("test");
$values = [
    'id' => 20,
    'data' => 'Some data',
];

$query = $db->write("INSERT INTO $table (id, data) VALUES (:id, :data)", $values);
```

--------------------------------

### Generate Admin Password Hash

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Frequently-Asked-Questions-(FAQ)

Use this command to generate a hashed password for the SimpleSAMLphp admin interface. This is required for versions 2.3 and later.

```bash
./bin/pwgen.php
```

--------------------------------

### Minimal SAML 2.0 IdP Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-hosted.md

Defines the essential configuration for a SAML 2.0 IdP, including the hostname, certificate, private key, and authentication source. The '__DEFAULT__' hostname is used to avoid specifying a hostname.

```php
<?php

$metadata['https://example.org/saml-idp'] = [
    /*
     * We use '__DEFAULT__' as the hostname so we won\'t have to
     * enter a hostname.
     */
    'host' => '__DEFAULT__',

    /* The private key and certificate used by this IdP. */
    'certificate' => 'example.org.crt',
    'privatekey' => 'example.org.pem',

    /*
     * The authentication source for this IdP. Must be one
     * from config/authsources.php.
     */
    'auth' => 'example-userpass',
];

```

--------------------------------

### Requesting Specific Authentication Method

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Initiate a login request specifying a particular authentication context class reference, such as Password.

```php
$auth = new \SimpleSAML\Auth\Simple('default-sp');
$auth->login([
    'saml:AuthnContextClassRef' => 'urn:oasis:names:tc:SAML:2.0:ac:classes:Password',
]);
```

--------------------------------

### Extract New Version for Upgrade

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Extracts the new version of SimpleSAMLphp during an upgrade process.

```bash
cd /var
tar xzf simplesamlphp-x.y.z.tar.gz
```

--------------------------------

### Initiate IdP-initiated Logout URL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp-more.md

Visit this URL to initiate an IdP-initiated logout. It sends a logout request to each SP and returns the user to the specified ReturnTo URL.

```url
https://idp.example.org/simplesaml/saml2/idp/SingleLogoutService.php?ReturnTo=<URL to return to after logout>
```

--------------------------------

### Set Session Store Type to Memcache

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Configure SimpleSAMLphp to use memcache for session storage. This enables distributed sessions for load-balancing and fail-over.

```php
'store.type' => 'memcache',
```

--------------------------------

### Configure Remote Service Provider Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp.md

Minimal metadata configuration for a remote SimpleSAMLphp Service Provider (SP). This file registers the SP with the IdP, specifying its Assertion Consumer Service and Single Logout Service endpoints.

```php
<?php

$metadata['https://sp.example.org/simplesaml/module.php/saml/sp/metadata.php/default-sp'] = [
    'AssertionConsumerService' => [
        [
            'Location' => 'https://sp.example.org/simplesaml/module.php/saml/sp/saml2-acs.php/default-sp',
            'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST',
        ],
    ],
    'SingleLogoutService' => [
        [
            'Location' => 'https://sp.example.org/simplesaml/module.php/saml/sp/saml2-logout.php/default-sp',
            'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect',
        ],
    ],
];

```

--------------------------------

### Configure Default Preselected Source in Authsources

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/multiauth/docs/multiauth.md

Set the 'preselect' option within the multiauth configuration in 'authsources.php' to define a default authentication source. This source will be used if no other preselection method is specified.

```php
'example-multi' => [
    'multiauth:MultiAuth',

    /*
     * The available authentication sources.
     * They must be defined in this authsources.php file.
     */
    'sources' => [
        'example-saml' => [
        // ...
        ],
        'example-admin' => [
        // ...
        ],
    ],
    'preselect' => 'example-saml',
],
```

--------------------------------

### Multilingual Organization Details in IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-hosted.md

Shows how to configure organization name, display name, and URL with support for multiple languages in the IdP metadata.

```php
'OrganizationName' => [
    'en' => 'Voorbeeld Organisatie Foundation b.a.',
    'nl' => 'Stichting Voorbeeld Organisatie b.a.',
],
'OrganizationDisplayName' => [
    'en' => 'Example organization',
    'nl' => 'Voorbeeldorganisatie',
],
'OrganizationURL' => [
    'en' => 'https://example.com',
    'nl' => 'https://example.com/nl',
],

```

--------------------------------

### Handle Custom Session Handlers

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

When using a custom session handler, unset it before interacting with SimpleSAMLphp and restore it afterwards to avoid conflicts.

```php
// use custom save handler
session_set_save_handler($handler);
session_start();

// close session and restore default handler
session_write_close();
session_set_save_handler(new SessionHandler(), true);

// use SimpleSAML\Session
$session = \SimpleSAML\Session::getSessionFromRequest();
$session->cleanup();
session_write_close();

// back to custom save handler
session_set_save_handler($handler);
session_start();
```

--------------------------------

### Read from Database with Prepared Statement

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-database.md

Select data from a table using a prepared statement. Values are bound as PDO::PARAM_STR by default.

```php
$table = $db->applyPrefix("test");
$values = [
    'id' => 20,
];

$query = $db->read("SELECT * FROM $table WHERE id = :id", $values);
```

--------------------------------

### Configuring Other Contact with Attributes in IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-hosted.md

Demonstrates how to specify an 'other' contact type with additional attributes, such as for security contact information required by trust frameworks like SIRTFI.

```php
'contacts' => [
    [
        'contactType'       => 'other',
        'emailAddress'      => 'mailto:abuse@example.org',
        'givenName'         => 'John',
        'surName'           => 'Doe',
        'telephoneNumber'   => '+31(0)12345678',
        'company'           => 'Example Inc.',
        'attributes' => [
            [
                'namespaceURI' => 'http://refeds.org/metadata',
                'namespacePrefix' => 'remd',
                'attrName' => 'contactType',
                'attrValue' => 'http://refeds.org/metadata/contactType/security',
            ],
        ],
    ],
],

```

--------------------------------

### Set Technical Contact Information in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Provide technical contact details, including name and email, for metadata generation and error reporting.

```php
'technicalcontact_name' => 'John Smith',
'technicalcontact_email' => 'john.smith@example.com',
```

--------------------------------

### Generate New Keypair and Self-Signed Certificate

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/keyrollover.md

Use OpenSSL to create a new RSA keypair and a self-signed certificate valid for 10 years. This command should be executed within the 'cert' directory.

```bash
cd cert
openssl req -newkey rsa:3072 -new -x509 -days 3652 -nodes -out new.crt -keyout new.pem
```

--------------------------------

### Configure IdP to Use Custom Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

Update the 'auth' option in your IdP's hosted metadata to point to your custom authentication instance.

```php
<?php

/* ... */
$metadata['https://example.org/saml-idp'] = [
    /* ... */
    /*
     * Authentication source to use. Must be one that is configured in
     * 'config/authsources.php'.
     */
    'auth' => 'myauthinstance',
    /* ... */
];

```

--------------------------------

### Configure Session Check Function

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-advancedfeatures.md

This configuration snippet shows how to enable a custom session checking function in SimpleSAMLphp's config.php.

```php
    'session.check_function' => ['\SimpleSAML\CustomCode', 'checkSession'],
```

--------------------------------

### Simple Auth Proc Filter Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-authproc.md

A basic configuration for an Auth Proc Filter using its module and class name. This is a shorthand for the more verbose array format.

```php
20 => 'core:TargetedID',
```

--------------------------------

### Connecting to a Specific IdP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Configure an SP to connect to a particular Identity Provider by specifying its entity ID.

```php
'example' => [
    'saml:SP',
    'entityID' => 'https://myapp.example.org',
    'idp' => 'https://example.net/saml-idp',
],
```

--------------------------------

### Push Git Tag

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Push the newly created tag to the remote repository.

```shell
% git push origin vX.Y.Z
```

--------------------------------

### Configure MultiAuth Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/multiauth/docs/multiauth.md

Defines a 'multiauth:MultiAuth' authentication source in `config/authsources.php`, specifying available sub-authentication sources with display text and optional attributes.

```php
'example-multi' => [
    'multiauth:MultiAuth',

    /*
     * The available authentication sources.
     * They must be defined in this authsources.php file.
     */
    'sources' => [
        'example-saml' => [
            'text' => [
                'en' => 'Log in using a SAML SP',
                'es' => 'Entrar usando un SP SAML',
            ],
            'css_class' => 'SAML',
            'AuthnContextClassRef' => ['urn:oasis:names:tc:SAML:2.0:ac:classes:SmartcardPKI', 'urn:oasis:names:tc:SAML:2.0:ac:classes:MobileTwoFactorContract'],
        ],
        'example-admin' => [
            'text' => [
                'en' => 'Log in using the admin password',
                'es' => 'Entrar usando la contraseña de administrador',
            ],
            'AuthnContextClassRef' => 'urn:oasis:names:tc:SAML:2.0:ac:classes:PasswordProtectedTransport',
        ],
    ],
],
```

--------------------------------

### SP Remote Metadata with HTTP-Artifact Binding

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-artifact-idp.md

Defines the 'AssertionConsumerService' endpoints for an SP in the remote IdP metadata. Includes both HTTP-POST and HTTP-Artifact bindings with their respective locations and indices.

```php
'AssertionConsumerService' => [
    [
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST',
        'Location' => 'https://sp.example.org/simplesaml/module.php/saml/sp/saml2-acs.php/default-sp',
        'index' => 0,
    ],
    [
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Artifact',
        'Location' => 'https://sp.example.org/simplesaml/module.php/saml/sp/saml2-acs.php/default-sp',
        'index' => 2,
    ],
],
```

--------------------------------

### Minimal Configuration for NameIDAttribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/nameidattribute.md

This snippet shows the most basic configuration for the saml:NameIDAttribute filter. It uses default values for the attribute name and format.

```php
'default-sp' => [
        'saml:SP',
        'authproc' => [
            20 => 'saml:NameIDAttribute',
        ],
    ],
```

--------------------------------

### Enable Artifact Sending in IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-artifact-idp.md

Configures the IdP's hosted metadata to enable sending artifacts. This involves adding the 'saml20.sendartifact' option to the specific IdP entry.

```php
$metadata['https://example.org/saml-idp'] = [
    [....]
    'auth' => 'example-userpass',
    'saml20.sendartifact' => true,
];
```

--------------------------------

### Update Version in Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Edit the Configuration.php file to set the new release version number.

```php
    /**
     * The release version of this package
     */
    public const VERSION = 'X.Y.Z';
```

--------------------------------

### Set Version in Composer

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Use composer to set the version number in the composer.json file.

```shell
% composer config version vX.Y.Z
```

--------------------------------

### Configure Crontab for Daily Cron Jobs

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/cron/docs/cron.md

Schedule daily cron jobs using curl to trigger the SimpleSAMLphp cron module endpoint. Ensure the URL, key, and tag match your configuration.

```text
# Run cron [daily]
02 0 * * * curl -sS "https://YOUR_SERVER/simplesaml/module.php/cron/run/daily/RANDOM_KEY"
```

--------------------------------

### Configure Admin Password Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/multiauth/docs/multiauth.md

Defines a 'core:AdminPassword' authentication source, often used as a fallback or alternative in MultiAuth configurations.

```php
'example-admin' => [
    'core:AdminPassword',
],
```

--------------------------------

### Configure SAML 2.0 IdP Hosted Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-googleapps.md

Defines the SAML entity ID, host, private key, certificate, and authentication method for the IdP. This configuration should replace the default entry in your metadata file.

```php
// The SAML entity ID is the index of this config.
$metadata['https://example.org/saml-idp'] = [
    // The hostname of the server (VHOST) that this SAML entity will use.
    'host' => '__DEFAULT__',

    // X.509 key and certificate. Relative to the cert directory.
    'privatekey'   => 'googleworkspaceidp.pem',
    'certificate'  => 'googleappsidp.crt',

    'auth' => 'example-userpass',
]
```

--------------------------------

### Set Default Language in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Change the default language for the SimpleSAMLphp interface from English to another language.

```php
'language.default' => 'no',
```

--------------------------------

### Handle Multi-Value Attributes: Abort and Take First Value

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_cardinalitysingle.md

This configuration aborts if multiple values are received for 'eduPersonPrincipalName' but takes the first value for 'eduPersonPrimaryAffiliation'. It demonstrates the use of both 'singleValued' and 'firstValue' parameters.

```php
'authproc' => [
        50 => [
            'class' => 'core:CardinalitySingle',
            'singleValued' => ['eduPersonPrincipalName'],
            'firstValue' => ['eduPersonPrimaryAffiliation'],
            ],
        ],
    ],
```

--------------------------------

### Aggregator2 Module RegistrationInfo Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-rpi.md

Configure RegistrationInfo for the aggregator2 module. Supports authority and policy URLs.

```php
$config = [
    'example.org' => [
        'sources' => [
            ...
        ],
        'RegistrationInfo' => [
            'RegistrationAuthority' => 'urn:mace:example.federation',
            'RegistrationPolicy' => ['en' => 'http://example.org/federation_policy', 'es' => 'https://example.org/politica_federacion'],
        ],
    ],
];
```

--------------------------------

### Script to Merge Master into Release Branches

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-developer-information.md

A script to merge the 'master' branch into both the current ('simplesamlphp-2.5') and next ('simplesamlphp-2.6') release branches, followed by pushing the changes.

```bash
git checkout master
git pull
git checkout simplesamlphp-2.5
git merge master
git push

git checkout simplesamlphp-2.6
git merge master
git push
```

--------------------------------

### getLoginURL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Generates a URL that can be used to initiate the authentication process. The URL can optionally specify a page to return to after successful authentication.

```APIDOC
## getLoginURL

### Description
Generates a URL that can be used to initiate the authentication process. The URL can optionally specify a page to return to after successful authentication.

### Method Signature
`string getLoginURL(string $returnTo = null)`

### Parameters
*   **$returnTo** (string) - Optional. The URL the user should be returned to after authentication. Defaults to the current page.

### Return Value
A string representing the login URL.

### Example
```php
$url = $auth->getLoginURL();

print('<a href="' . htmlspecialchars($url) . '">Login</a>');
```

### Note
The URL format is `.../simplesaml/module.php/core/login/<authentication source>?ReturnTo=<return URL>`.
```

--------------------------------

### Enable AJAX iFrame Single Log-Out in IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp-more.md

Add this configuration line to your saml20-idp-hosted.php metadata to enable the AJAX iFrame Single Log-Out approach.

```php
'logouttype' => 'iframe',
```

--------------------------------

### Apply Database Table Prefix

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-database.md

Prepend the configured database table prefix to a table name. This is essential when administrators have set a prefix for all tables.

```php
$table = $db->applyPrefix("saml20_idp_hosted");
```

--------------------------------

### Generate Login URL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Generates a static URL to initiate the authentication process. The user will be redirected to the specified URL after successful authentication. The default return URL is the current page.

```php
$url = $auth->getLoginURL();

print('<a href="
```

--------------------------------

### Promote Next Release Branch to Current Release

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-developer-information.md

Merges the 'next-release-branch' (e.g., simplesamlphp-2.6) into 'master' to make it the current release branch. This merge should ideally occur without conflicts.

```bash
# When we are ready to make "next-release-branch" the current release
git checkout master
git merge simplesamlphp-2.6
# This should go without any conflicts, since we kept merging the "next-release-branch" with master
```

--------------------------------

### Configure Memcache Servers for Redundancy and Load Balancing

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Define memcache server groups for redundant and load-balanced session storage. Sessions are mirrored across server groups and load-balanced within each group.

```php
'memcache_store.servers' => [
    [
        ['hostname' => 'mc_a1'],
        ['hostname' => 'mc_a2'],
    ],
    [
        ['hostname' => 'mc_b1'],
        ['hostname' => 'mc_b2'],
    ],
],
```

--------------------------------

### Configure Crontab for Hourly Cron Jobs

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/cron/docs/cron.md

Schedule hourly cron jobs using curl to trigger the SimpleSAMLphp cron module endpoint. Ensure the URL, key, and tag match your configuration.

```text
# Run cron [hourly]
01 * * * * curl -sS "https://YOUR_SERVER/simplesaml/module.php/cron/run/hourly/RANDOM_KEY"
```

--------------------------------

### Retrieve User Attributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

After successful authentication, use getAttributes() to fetch the user's attributes. Each attribute value is returned as an array.

```php
$attributes = $as->getAttributes();
print_r($attributes);
```

--------------------------------

### Enable Signing for Logout Messages

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-hosted.md

Set the 'redirect.sign' option to true to enable signing of logout requests and responses sent from this IdP. This option defaults to false.

```php
'redirect.sign' => true,
```

--------------------------------

### Set Metadata Signing Algorithm

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-advancedfeatures.md

This configuration option specifies the algorithm to use when signing metadata for an entity. The default is RSA-SHA256.

```php
'metadata.sign.algorithm' => 'http://www.w3.org/2001/04/xmldsig-more#rsa-sha256',
```

--------------------------------

### Configure AssertionConsumerService Endpoints

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-endpoints.md

Defines multiple AssertionConsumerService endpoints with different bindings and default settings. Use this to specify various ways a Service Provider can accept assertions.

```php
'AssertionConsumerService' => [
    [
        'index' => 1,
        'isDefault' => true,
        'Location' => 'https://sp.example.org/ACS',
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST',
    ],
    [
        'index' => 2,
        'Location' => 'https://sp.example.org/ACS',
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Artifact',
    ],
],
```

--------------------------------

### Configure SP AssertionConsumerService for ECP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-ecp-idp.md

For an SP using the ECP profile, configure the 'saml20-sp-remote' metadata with a complex endpoint format, including an AssertionConsumerService endpoint that supports the PAOS binding for ECP.

```php
'AssertionConsumerService' => [
    0 => [
      'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST',
      'Location' => 'https://sp.example.org/Shibboleth.sso/SAML2/POST',
      'index' => 1,
    ],
    1 => [
      'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:PAOS',
      'Location' => 'https://sp.example.org/ECP',
      'index' => 2,
    ],
],
```

--------------------------------

### Update IdP Hosted Metadata for New Key

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/keyrollover.md

Modify the hosted IdP metadata in saml20-idp-hosted.php to reflect the new signing certificate and private key.

```php
    $metadata['urn:x-simplesamlphp:idp'] = [
        'host' => '__DEFAULT__',
        'auth' => 'example-userpass',
        'certificate' => 'new.crt',
        'privatekey' => 'new.pem',
        // When private key is passphrase protected.
        'privatekey_pass' => '<new-secret>',
    ];
```

--------------------------------

### Remote SP Metadata Configuration Structure

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-sp-remote.md

Defines the basic structure for configuring remote Service Provider (SP) metadata. Each entry in the metadata array is keyed by the SP's entity ID and contains its specific configuration options.

```php
<?php
/* The index of the array is the entity ID of this SP. */
$metadata['entity-id-1'] = [
    /* Configuration options for the first SP. */
];
$metadata['entity-id-2'] = [
    /* Configuration options for the second SP. */
];
/* ... */

```

--------------------------------

### Set Session Store Type to PHP Session

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Configure SimpleSAMLphp to use the built-in PHP session management. This is the default and simplest option.

```php
'store.type' => 'phpsession',
```

--------------------------------

### Fetch and Pull Latest Changes

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Fetch the latest changes from the remote repository and pull them into the master branch. This ensures you are working with the most up-to-date code.

```bash
% git fetch origin
% git pull origin master
```

--------------------------------

### Throwing Exception in Authentication Module or Processing Filter

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-errorhandling.md

Use this method to throw an exception directly within the `authenticate()` or `process()` methods of modules or filters. The exception will be caught and handled by SimpleSAMLphp's error handling system.

```php
public function process(array &$state): void
{
    if ($state['something'] === false) {
        throw new \SimpleSAML\Error\Exception('Something is wrong...');
    }
}
```

--------------------------------

### logout

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Logs the user out of the SimpleSAMLphp session. It can optionally redirect the user to a specified URL or call a function after logout. This function never returns.

```APIDOC
## logout

### Description
Logs the user out of the SimpleSAMLphp session. It can optionally redirect the user to a specified URL or call a function after logout. This function never returns.

### Method Signature
`void logout(mixed $params = null)`

### Parameters
*   **$params** (mixed) - Optional. Parameters for the logout operation. Can be a string (URL to redirect to) or an associative array with options like `ReturnTo`, `ReturnCallback`, `ReturnStateParam`, `ReturnStateStage`.

### Example 1: Redirect to URL
```php
$auth->logout('https://sp.example.org/logged_out.php');
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
```

### Example 2: Using return parameters and handling state
```php
$auth->logout([
    'ReturnTo' => 'https://sp.example.org/logged_out.php',
    'ReturnStateParam' => 'LogoutState',
    'ReturnStateStage' => 'MyLogoutState',
]);
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
```

### Handling Logout State (in `logged_out.php`)
```php
$state = \SimpleSAML\Auth\State::loadState((string)$_REQUEST['LogoutState'], 'MyLogoutState');
$ls = $state['saml:sp:LogoutStatus']; /* Only works for SAML SP */
if ($ls['Code'] === 'urn:oasis:names:tc:SAML:2.0:status:Success' && !isset($ls['SubCode'])) {
    /* Successful logout. */
    echo("You have been logged out.");
} else {
    /* Logout failed. Tell the user to close the browser. */
    echo("We were unable to log you out of all your sessions. To be completely sure that you are logged out, you need to close your web browser.");
}
```
```

--------------------------------

### Translate Strings for a New Language

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Define translations for UI strings in the 'dictionaries/' files. Each string should be an associative array mapping language codes to their translated text.

```php
'user_pass_header' => [
    'en' => 'Enter your username and password',
    'no' => 'Skriv inn brukernavn og passord',
    'xx' => 'Pooa jujjique jamba',
],
```

--------------------------------

### Configure Log Prefix and Level with core:AttributeDump

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributedump.md

This configuration demonstrates how to specify a custom log prefix and a 'debug' log level for the AttributeDump filter. Use this to control the output format and visibility of debug messages.

```php
'authproc' => [
    49 => [
        'class' => 'core:AttributeAdd',
        [...]
    ],

    50 => [
        'class' => 'core:AttributeDump',
        'logPrefix' => 'After running AttributeAdd but before applying AttributeLimit filter',
        'logLevel' => 'debug',
    ],

    51 => [
        'class' => 'core:AttributeLimit',
        [...]
    ],
]
```

--------------------------------

### Logout and Redirect to URL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Logs the user out and redirects them to a specified URL. The `cleanup()` method is called to clear the session.

```php
$auth->logout('https://sp.example.org/logged_out.php');
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
```

--------------------------------

### Generate Self-Signed Certificate

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

Command to create a self-signed certificate and private key for your Service Provider. This is often required by Identity Providers for signing requests and responses.

```bash
cd cert
openssl req -newkey rsa:3072 -new -x509 -days 3652 -nodes -out saml.crt -keyout saml.pem

```

--------------------------------

### Generate Self-Signed Certificate with OpenSSL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp.md

Generates a new private key and a self-signed certificate using OpenSSL. This certificate is used by the IdP to sign SAML assertions. Ensure the output files are placed in the directory specified by the 'certdir' setting.

```bash
openssl req -newkey rsa:3072 -new -x509 -days 3652 -nodes -out example.org.crt -keyout example.org.pem
```

--------------------------------

### Configuring Support Contact in IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-hosted.md

Specifies how to add a support contact to the IdP metadata, including type, email, name, and phone number.

```php
'contacts' => [
    [
        'contactType'       => 'support',
        'emailAddress'      => 'support@example.org',
        'givenName'         => 'John',
        'surName'           => 'Doe',
        'telephoneNumber'   => '+31(0)12345678',
        'company'           => 'Example Inc.',
    ],
],

```

--------------------------------

### IdP-first Flow URL with RelayState

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp-more.md

This URL initiates the SSO flow at the IdP and includes a RelayState parameter, often used to specify the redirect URL after authentication.

```url
https://idp.example.org/simplesaml/module.php/saml/idp/singleSignOnService?spentityid=urn:mace:feide.no:someservice&RelayState=https://sp.example.org/somepage
```

--------------------------------

### Write to Database Without Prepared Statements

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-database.md

Execute a SQL query without using prepared statements. Use this only for statements with no user input, such as CREATE TABLE. The params variable must be explicitly set to false.

```php
$table = $db->applyPrefix("test");
$query = $db->write("CREATE TABLE IF NOT EXISTS $table (id INT(16) NOT NULL, data TEXT NOT NULL)", false);
```

--------------------------------

### Include Webserver Certificate in IdP Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-artifact-idp.md

Configures the IdP's hosted metadata to include the webserver certificate file path. This is used by some SPs to validate the ArtifactResolutionService SSL certificate.

```php
$metadata['https://example.org/saml-idp'] = [
    [....]
    'auth' => 'example-userpass',
    'saml20.sendartifact' => true,
    'https.certificate' => '/etc/apache2/webserver.crt',
];
```

--------------------------------

### Custom Metadata Extension for eduGAIN Republish Request

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-hosted.md

Includes a custom metadata extension for an eduGAIN republish request by creating an XML Chunk. This allows specifying a target for republishing metadata.

```php
<?php

$dom = \SimpleSAML\XML\DOMDocumentFactory::create();
$republishRequest = $dom->createElementNS('http://eduid.cz/schema/metadata/1.0', 'eduidmd:RepublishRequest');
$republishTarget = $dom->createElementNS('http://eduid.cz/schema/metadata/1.0', 'eduidmd:RepublishTarget', 'http://edugain.org/');
$republishRequest->appendChild($republishTarget);
$ext = [new \SimpleSAML\XML\Chunk($republishRequest)];

$metadata['https://example.org/saml-idp'] = [
    'host' => '__DEFAULT__',
    'certificate' => 'example.org.crt',
    'privatekey' => 'example.org.pem',
    'auth' => 'example-userpass',

    /*
     * The custom metadata extensions.
     */
    'saml:Extensions' => $ext,
];

```

--------------------------------

### ConfigPageEvent Class Definition

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-modules.md

Defines the ConfigPageEvent class, which encapsulates state and provides access to the template object for event listeners.

```php
    class ConfigPageEvent
    {
        public function __construct(
            private readonly XHTML\Template $template,
        )
        {}

        public function getTemplate(): XHTML\Template
        {
            return $this->template;
        }
    }
```

--------------------------------

### Checkout and Pull Latest from Major Version Branch

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Ensure you are on the correct major version branch and have the latest updates before proceeding with minor version releases.

```bash
% git checkout simplesamlphp-X.Y
% git pull origin simplesamlphp-X.Y
```

--------------------------------

### Add Attribute with Multiple OR Conditions

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

This configuration adds an attribute ('allowedSystems') if any of the specified conditions are true (logical OR). It allows adding the attribute if 'supplierId' exists OR if 'role' is 'Staff' and 'departmentName' is 'Procurement'.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            '%anycondition',
            'conditions' => [
                'attrExistsAny' => [
                    'supplierId',
                ],
                'attrValueIsAll' => [
                    'role' => ['Staff'],
                    'departmentName' => ['Procurement'],
                ],
            ],
            'attributes' => [
                'allowedSystems' => ['procurement'],
            ],
        ],
    ],
```

--------------------------------

### Define Properties for Custom Authentication Source Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

Declare private properties in your custom authentication class to store configuration values like username and password.

```php
private $username;
private $password;

```

--------------------------------

### Define User Attributes for Authentication Source

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp.md

Specify attributes for a user within an authentication source configuration. These attributes, such as 'uid' and 'eduPersonAffiliation', will be returned by the IdP upon successful user login.

```php
[
    'uid' => ['student'],
    'eduPersonAffiliation' => ['member', 'student'],
],
```

--------------------------------

### Add Links to Login Page in authsources.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp-more.md

Configure the 'core:loginpage_links' option in your authsources.php configuration to add helpful links to the login page. These links will be translated if translations are available.

```php
    'example-userpass' => [
        ...
        'core:loginpage_links' => [
            [
                'href' => 'https://example.com/reset',
                'text' => 'Forgot your password?',
            ],
            [
                'href' => 'https://example.com/news',
                'text' => 'Latest news about us',
            ],
        ],
        ...
    ],
```

--------------------------------

### Customizing Buttons with Pure.css

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/New-UI

Add the 'pure-button-red' class to a 'pure-button' element to style it as a red button.

```html
<button class="pure-button pure-button-red">Red Button</button>
```

--------------------------------

### Attribute Map in Module File

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributemap.md

Specify an attribute map file located within a module's 'attributemap/' directory using the 'module:file' syntax. This allows for modular and reusable attribute mapping configurations.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeMap',
            'module:src2dst'
        ],
    ],
```

--------------------------------

### Map using Regular Expressions

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributevaluemap.md

Adds 'student' to eduPersonAffiliation if the 'memberOf' attribute matches a regex pattern. Uses '%regex' option for pattern matching and merges values by default.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeValueMap',
            'sourceattribute' => 'memberOf',
            'targetattribute' => 'eduPersonAffiliation',
            '%regex',
            'values' => [
                'student' => [
                    '/^cn=student,o=[a-z]+,o=organization,dc=org$/',
                ],
            ],
        ],
    ],
```

--------------------------------

### Configure IDPList for Scoping

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-scoping.md

Specify a list of trusted Identity Provider entity IDs for scoping. This is typically used in authentication source configurations or metadata.

```php
# Add the IDPList
'IDPList' => [
    'IdPEntityID1',
    'IdPEntityID2',
    'IdPEntityID3',
],
```

--------------------------------

### Basic FilterScopes Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/filterscopes.md

This is the most basic configuration for the FilterScopes filter. It uses the default attributes.

```php
    'authproc' => [
        90 => [
            'class' => 'saml:FilterScopes',
        ],
    ],
```

--------------------------------

### Construct Single Value from Multi-Value Attribute using First Value

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_cardinalitysingle.md

This snippet first copies 'eduPersonAffiliation' to 'eduPersonPrimaryAffiliation' using 'core:AttributeCopy', then uses 'core:CardinalitySingle' with the 'firstValue' parameter to ensure 'eduPersonPrimaryAffiliation' is single-valued by taking the first value from the copied attribute.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeCopy',
            'eduPersonAffiliation' => 'eduPersonPrimaryAffiliation',
        ],
        51 => [
            'class' => 'core:CardinalitySingle',
            'firstValue' => ['eduPersonPrimaryAffiliation'],
        ],
    ],
```

--------------------------------

### Preselect Authentication Source in Login Call

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/multiauth/docs/multiauth.md

Use the 'multiauth:preselect' parameter in the login call to directly authenticate with a specific source. This bypasses the multiauth selection page.

```php
$as = new \SimpleSAML\Auth\Simple('my-multiauth-authsource');
$as->login([
    'multiauth:preselect' => 'default-sp',
]);
```

--------------------------------

### Configure Attribute NameFormat and Mapping

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-idp.md

Enables the 'urn:oasis:names:tc:SAML:2.0:attrname-format:uri' NameFormat for attributes, as recommended by the interoperable SAML 2 profile. Includes a configuration to convert LDAP names to OIDs.

```php
'attributes.NameFormat' => 'urn:oasis:names:tc:SAML:2.0:attrname-format:uri',
'authproc' => [
    // Convert LDAP names to oids.
    100 => ['class' => 'core:AttributeMap', 'name2oid'],
],

```

--------------------------------

### Translate with placeholders using PHP

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

In PHP, use the `$this->t()` method to translate strings with placeholders, passing an array of replacements.

```php
$this->t('Session size: %SIZE%', array('%SIZE%' => $this->data['sessionsize']))
```

--------------------------------

### Enable Message Validation for Remote IdP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-remote.md

Configure SimpleSAMLphp to validate incoming logout requests and responses from a remote IdP. This requires specifying a certificate for validation.

```php
'redirect.validate' => true,
'certificate' => 'example.org.crt',
```

--------------------------------

### Default LanguageAdaptor Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_languageadaptor.md

This snippet shows the default configuration for the LanguageAdaptor, using the 'preferredLanguage' attribute.

```php
'authproc' => [
    50 => [
        'class' => 'core:LanguageAdaptor',
    ],
],
```

--------------------------------

### Generate Secret Salt

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Generate a random string for the 'secretsalt' configuration option on Unix-like systems.

```bash
tr -c -d '0123456789abcdefghijklmnopqrstuvwxyz' </dev/urandom | dd bs=32 count=1 2>/dev/null;echo
```

--------------------------------

### Add Attribute with Multiple AND Conditions

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Configures adding an attribute ('groups') when multiple conditions are met simultaneously (logical AND). It checks for the existence of 'staffId' and a specific 'departmentName'.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrExistsAny' => [
                    'staffId',
                ],
                'attrValueIsAny' => [
                    'departmentName' => ['Physics'],
                ],
            ],
            'attributes' => [
                'groups' => ['StaffPhysics'],
            ],
        ],
    ],
```

--------------------------------

### Dump All Attributes with core:AttributeDump

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributedump.md

If no attribute list or regular expressions are provided, this configuration will dump all attributes to the logs. Use this for general debugging when you need to see all available attributes.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeDump',
    ],
]
```

--------------------------------

### Update SP Configuration for New Key

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/keyrollover.md

Update the 'certificate', 'privatekey', and 'privatekey_pass' options in your SP's authsources.php configuration to use the new key details.

```php
    'default-sp' => [
        'saml:SP',
        'certificate' => 'new.crt',
        'privatekey' => 'new.pem',
        // When private key is passphrase protected.
        'privatekey_pass' => '<new-secret>',
    ],
```

--------------------------------

### Custom Authentication Module Class

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

The main class for a custom authentication module. It extends the base authentication source and implements the login method.

```php
<?php

class SimpleSAML_Auth_MyAuth extends SimpleSAML_Auth_Source {

    /* The database DSN.
     * See the documentation for the various database drivers for information about the syntax:
     *     http://www.php.net/manual/en/pdo.drivers.php
     */
    private $dsn;

    /* The database username, password & options. */
    private $username;
    private $password;
    private $options;

    public function __construct($info, $config) {
        parent::__construct($info, $config);

        if (!is_string($config['dsn'])) {
            throw new Exception('Missing or invalid dsn option in config.');
        }
        $this->dsn = $config['dsn'];

        if (!is_string($config['username'])) {
            throw new Exception('Missing or invalid username option in config.');
        }
        $this->username = $config['username'];

        if (!is_string($config['password'])) {
            throw new Exception('Missing or invalid password option in config.');
        }
        $this->password = $config['password'];

        if (isset($config['options'])) {
            if (!is_array($config['options'])) {
                throw new Exception('Missing or invalid options option in config.');
            }
            $this->options = $config['options'];
        }
    }

    /**
     * A helper function for validating a password hash.
     *
     * In this example we check a SSHA-password, where the database
     * contains a base64 encoded byte string, where the first 20 bytes
     * from the byte string is the SHA1 sum, and the remaining bytes is
     * the salt.
     */
    private function checkPassword($passwordHash, $password) {
        $passwordHash = base64_decode($passwordHash, true);
        if (empty($passwordHash)) {
            throw new \InvalidArgumentException("Password hash is empty or not a valid base64 encoded string.");
        }

        $digest = substr($passwordHash, 0, 20);
        $salt = substr($passwordHash, 20);

        $checkDigest = sha1($password . $salt, true);
        return $digest === $checkDigest;
    }

    protected function login(string $username, string $password): array {
        /* Connect to the database. */
        $db = new PDO($this->dsn, $this->username, $this->password, $this->options);
        $db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
        $db->setAttribute(PDO::ATTR_EMULATE_PREPARES, false);

        /* Ensure that we are operating with UTF-8 encoding.
         * This command is for MySQL. Other databases may need different commands.
         */
        $db->exec("SET NAMES 'utf8'");

        /* With PDO we use prepared statements. This saves us from having to escape
         * the username in the database query.
         */
        $st = $db->prepare('SELECT username, password_hash, full_name FROM userdb WHERE username=:username');

        if (!$st->execute(['username' => $username])) {
            throw new Exception('Failed to query database for user.');
        }

        /* Retrieve the row from the database. */
        $row = $st->fetch(PDO::FETCH_ASSOC);
        if (!$row) {
            /* User not found. */
            SimpleSAML\Logger::warning('MyAuth: Could not find user ' . var_export($username, true) . '.');
            throw new \SimpleSAML\Error\Error(\SimpleSAML\Error\ErrorCodes::WRONGUSERPASS);
        }

        /* Check the password. */
        if (!$this->checkPassword($row['password_hash'], $password)) {
            /* Invalid password. */
            SimpleSAML\Logger::warning('MyAuth: Wrong password for user ' . var_export($username, true) . '.');
            throw new \SimpleSAML\Error\Error(\SimpleSAML\Error\ErrorCodes::WRONGUSERPASS);
        }

        /* Create the attribute array of the user. */
        $attributes = [
            'uid' => [$username],
            'displayName' => [$row['full_name']],
            'eduPersonAffiliation' => ['member', 'employee'],
        ];

        /* Return the attributes. */
        return $attributes;
    }
}

```

--------------------------------

### Acceptable NameID Formats

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Specify the acceptable NameID formats the SP will accept from the IdP.

```php
'NameIDFormat' => [
            \SAML2\Constants::NAMEID_PERSISTENT,
            \SAML2\Constants::NAMEID_TRANSIENT,
        ],
```

--------------------------------

### Push New Major Version Branch

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

After creating a new major version branch, push it to the remote repository to make it available for collaboration and further development.

```bash
% git push -u origin simplesamlphp-X.Y
```

--------------------------------

### Require Signed SAML Responses

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/saml2int.md

Enable this option to enforce that SAML <Response> messages must be signed. This enforces the SAML2Int v2.00 requirement [SDP-IDP30].

```php
<?php

declare(strict_types=1);

return [
    'response.require_signed' => true,
];

```

--------------------------------

### Dump Specific and Regex-Matched Attributes with core:AttributeDump

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributedump.md

This configuration outputs both specific attributes ('uid', 'groups') and any attributes matching the regex '/n$/' to the logs. Use this for a combined filtering approach.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeDump',
        'attributes' => ['uid', 'groups'],
        'attributesRegex' => ['/n$/'],
    ],
]
```

--------------------------------

### Copy Base Template for Extensive Customization

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-theming.md

Copy the base Twig template to your module's theme directory for extensive base template modifications.

```bash
cp templates/base.twig modules/mymodule/themes/fancytheme/default/
```

--------------------------------

### Dynamically Constructing Service Provider EntityID

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-2.0.md

A PHP code snippet demonstrating a common method for dynamically constructing the Service Provider (SP) entityID using server variables. This is useful for ensuring the entityID matches the server's hostname.

```php
$entityid_sp = 'https://'
   . $_SERVER['HTTP_HOST']
   . '/simplesaml/module.php/saml/sp/metadata.php/default-sp';
```

--------------------------------

### Set Secret Salt in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Configure a cryptographically secure random string for the 'secretsalt' option. Changing this may affect user access to services.

```php
'secretsalt' => 'randombytesinsertedhere',
```

--------------------------------

### requireAuth

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Ensures the user is authenticated. If not, it initiates the authentication process. This function only returns if authentication is successful.

```APIDOC
## requireAuth

### Description
Make sure that the user is authenticated. This function will only return if the user is authenticated. If the user isn't authenticated, this function will start the authentication process.

### Parameters
* **params** (array) - Optional - An associative array with named parameters for this function. See the documentation for the `login`-function for a description of the parameters.

### Example 1
```php
$auth->requireAuth();
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
print("Hello, authenticated user!");
```

### Example 2
```php
/*
 * Return the user to the frontpage after authentication, don't post
 * the current POST data.
 */
$auth->requireAuth([
    'ReturnTo' => 'https://sp.example.org/',
    'KeepPost' => FALSE,
]);
\SimpleSAML\Session::getSessionFromRequest()->cleanup();
print("Hello, authenticated user!");
```
```

--------------------------------

### Implement Custom Theme Controller

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-theming.md

Implement the TemplateControllerInterface in a custom module to modify the Twig environment and template data.

```php
<?php

namespace SimpleSAML\Module\mymodule;

use Twig\Environment;
use SimpleSAML\XHTML\TemplateControllerInterface;

class FancyThemeController implements TemplateControllerInterface
{
    /**
     * Modify the twig environment after its initialization (e.g. add filters or extensions).
     *
     * @param \Twig\Environment $twig The current twig environment.
     * @return void
     */
    public function setUpTwig(Environment &$twig): void
    {
    }

    /**
     * Add, delete or modify the data passed to the template.
     *
     * This method will be called right before displaying the template.
     *
     * @param array $data The current data used by the template.
     * @return void
     */
    public function display(array &$data): void
    {
        $data['extra_info'] = 'Extra information to use in your template';
    }
}
```

--------------------------------

### Generated XML Metadata for Identity Provider Discovery

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-idpdisc.md

This XML metadata snippet shows how the 'DiscoveryResponse' configuration in `authsources.php` is translated into the SAML V2.0 Metadata Extensions for Identity Provider Discovery.

```xml
<?xml version="1.0"?>
<md:EntityDescriptor xmlns:md="urn:oasis:names:tc:SAML:2.0:metadata" xmlns:idpdisc="urn:oasis:names:tc:SAML:profiles:SSO:idp-discovery-protocol" xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" xmlns:ds="http://www.w3.org/2000/09/xmldsig#" entityID="https://example.com/saml-idp">
  <md:SPSSODescriptor protocolSupportEnumeration="urn:oasis:names:tc:SAML:2.0:protocol">
    <md:Extensions>
      <idpdisc:DiscoveryResponse xmlns:idpdisc="urn:oasis:names:tc:SAML:profiles:SSO:idp-discovery-protocol" Binding="urn:oasis:names:tc:SAML:profiles:SSO:idp-discovery-protocol" Location="https://simplesamlphp.org/some/endpoint" index="1" isDefault="true" />
    </md:Extensions>
    <md:KeyDescriptor use="signing">
      <ds:KeyInfo xmlns:ds="http://www.w3.org/2000/09/xmldsig#">
        <ds:X509Data>
        ...

```

--------------------------------

### Process Logout State in Return Page

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Loads the logout state from the request parameters on the return page to check the status of the logout operation. This is specific to SAML SP.

```php
$state = \SimpleSAML\Auth\State::loadState((string)$_REQUEST['LogoutState'], 'MyLogoutState');
$ls = $state['saml:sp:LogoutStatus']; /* Only works for SAML SP */
if ($ls['Code'] === 'urn:oasis:names:tc:SAML:2.0:status:Success' && !isset($ls['SubCode'])) {
    /* Successful logout. */
    echo("You have been logged out.");
} else {
    /* Logout failed. Tell the user to close the browser. */
    echo("We were unable to log you out of all your sessions. To be completely sure that you are logged out, you need to close your web browser.");
}
```

--------------------------------

### Throwing Exception After Redirect using State

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-errorhandling.md

When an exception needs to be thrown after a redirect has occurred, use `\SimpleSAML\Auth\State::throwException()`. This function ensures the exception is serialized and transferred to the appropriate error handler.

```php
<?php

$id = $_REQUEST['StateId'];
$state = \SimpleSAML\Auth\State::loadState($id, 'somestage...');
\SimpleSAML\Auth\State::throwException(
    $state,
    new \SimpleSAML\Error\Exception('Something is wrong...')
);
```

--------------------------------

### Translate Organization Display Name to Multiple Languages

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-sp-remote.md

Configure the display name of the organization responsible for the Service Provider (SP) in various languages. This option requires 'OrganizationName' to be specified.

--------------------------------

### Clear Symfony Cache

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-2.5.md

Run this command after updating SimpleSAMLphp to remove potentially stale cached objects. This is particularly useful if encountering errors related to constructor arguments or service definitions.

```sh
composer clear-symfony-cache
```

--------------------------------

### Cleanup SimpleSAMLphp Session

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

If using PHP sessions in both SimpleSAMLphp and your application, clean up SimpleSAMLphp's session to restore your application's session.

```php
$session = \SimpleSAML\Session::getSessionFromRequest();
$session->cleanup();
```

--------------------------------

### Configure SingleLogoutService with ResponseLocation

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-endpoints.md

Specifies a SingleLogoutService endpoint including the ResponseLocation attribute. This is useful for defining where logout responses should be sent.

```php
'SingleLogoutService' => [
    [
        'Location' => 'https://sp.example.org/LogoutRequest',
        'ResponseLocation' => 'https://sp.example.org/LogoutResponse',
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect',
    ],
],
```

--------------------------------

### Configure Password-Protected Redis Sentinels

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Configures connection details for Redis Sentinels where each sentinel may have a unique password. This is used when sentinels have different passwords than the Redis servers themselves.

```php
[
    'tcp://[yoursentinel1]:[port]?password=[password1]',
    'tcp://[yoursentinel2]:[port]?password=[password2]',
    'tcp://[yoursentinel3]:[port]?password=[password3]',
]
```

--------------------------------

### Write to Database with Specific Data Type Binding

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-database.md

Insert data into a table using a prepared statement, explicitly specifying the PDO data type for a bound parameter.

```php
$table = $db->applyPrefix("test");
$values = [
    'id' => [20, PDO::PARAM_INT],
    'data' => 'Some data',
];

$query = $db->write("INSERT INTO $table (id, data) VALUES (:id, :data)", $values);
```

--------------------------------

### Custom LanguageAdaptor Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_languageadaptor.md

This snippet demonstrates how to configure the LanguageAdaptor to use a custom attribute name, 'lang', for preferred language.

```php
'authproc' => [
    50 => [
        'class' => 'core:LanguageAdaptor',
        'attributename' => 'lang',
    ],
],
```

--------------------------------

### Adjust Include Path in SimpleSAMLphp

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Modify the include path in '_include.php' when the 'public' directory has been moved. This ensures that SimpleSAMLphp can locate its core source files.

```php
require_once(dirname(__FILE__, 3) . '/src/_autoload.php');
```

--------------------------------

### Remote IdP Metadata Structure

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-idp-remote.md

Defines the basic structure for configuring remote IdP metadata. The entity ID of the IdP is used as the key in the metadata array.

```php
<?php
/* The index of the array is the entity ID of this IdP. */
$metadata['entity-id-1'] = [
    /* Configuration options for the first IdP. */
];
$metadata['entity-id-2'] = [
    /* Configuration options for the second IdP. */
];
/* ... */

```

--------------------------------

### Append to Existing Attribute Without Duplicates

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

This configuration appends to an existing attribute ('groups') if a condition is met. The '%nodupe' option prevents duplicate values, ensuring 'management' is added only if not already present.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            '%nodupe',
            'conditions' => [
                'attrValueIsAny' => [
                    'role' => ['Manager', 'Director']
                ],
            ],
            'attributes' => [
                'groups' => ['management'],
            ],
        ],
    ],
```

--------------------------------

### Read from Database with Specific Data Type Binding

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-database.md

Select data from a table using a prepared statement, explicitly specifying the PDO data type for a bound parameter.

```php
$table = $db->applyPrefix("test");
$values = [
    'id' => [20, PDO::PARAM_INT],
];

$query = $db->read("SELECT * FROM $table WHERE id = :id", $values);
```

--------------------------------

### Translate with placeholders using trans tag

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

Replace strings containing placeholders like `%SIZE%` with variable content using the `trans` tag. Ensure the variable values are provided in the context.

```twig
{% trans %}Session size: {{ size }}{% endtrans %}
```

--------------------------------

### Update SimpleSAML_Session::isValid() Usage

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-upgrade-notes-1.5.md

Calls to `SimpleSAML_Session::isValid()` must now include an argument, typically 'saml2', to prevent potential security vulnerabilities.

```php
$session->isValid('saml2');
```

--------------------------------

### Define Cardinality Rules for Attributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_cardinality.md

Use this snippet to enforce minimum and maximum value counts for attributes like 'givenName', 'mail', and 'eduPersonScopedAffiliation'. Specify rules using 'min' and 'max' parameters.

```php
'authproc' => [
    50 => [
        'class' => 'core:Cardinality',
        'givenName' => ['min' => 1],
        'mail' => ['max' => 2],
        'eduPersonScopedAffiliation' => ['min' => 2, 'max' => 4],
    ],
],
```

--------------------------------

### Set eduPersonPrimaryAffiliation from DN

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Creates or updates the 'eduPersonPrimaryAffiliation' attribute based on a pattern match in the 'dn' attribute. Useful for mapping distinguished names to affiliations.

```php
10 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'dn',
        'pattern' => '/OU=Staff/',
        'replacement' => 'staff',
        'target' => 'eduPersonPrimaryAffiliation',
    ]
```

--------------------------------

### Configure Session Cookie Domain in SimpleSAMLphp

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/State-Information-Lost

Set the session cookie domain to ensure session persistence across subdomains. This is crucial when the domain name might change during the authentication process.

```php
'session.cookie.domain' => '.example.org',
```

--------------------------------

### Request Authentication with Specific IdP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

Optionally, specify a particular Identity Provider (IdP) for authentication by passing its identifier to the login() method.

```php
$as->login([
    'saml:idp' => 'https://example.org/saml-idp',
]);
```

--------------------------------

### Disable Memcache Failover in PHP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Configures the Memcache extension in php.ini to disable internal failover. This is a PHP-level configuration, not SimpleSAMLphp specific.

```ini
memcache.allow_failover = Off
```

--------------------------------

### Dump Specific Attributes with core:AttributeDump

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributedump.md

This configuration outputs only the 'uid' and 'groups' attributes to the logs. Use this when you are interested in a specific set of attributes.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeDump',
        'attributes' => ['uid', 'groups'],
    ],
]
```

--------------------------------

### Add Multiple Attributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeadd.md

Adds multiple attributes, some single-valued and some multi-valued, to the user.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeAdd',
            'eduPersonPrimaryAffiliation' => 'student',
            'eduPersonAffiliation' => ['student', 'employee', 'members'],
        ],
    ],
```

--------------------------------

### Replace and Keep Attribute Values

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributevaluemap.md

Replaces all existing values in the 'affiliation' attribute and keeps the 'groups' source attribute. Maps specific group DNs to 'student' and 'employee' affiliations.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeValueMap',
            'sourceattribute' => 'groups',
            'targetattribute' => 'affiliation',
            '%replace',
            '%keep',
            'values' => [
                'student' => [
                    'cn=student,o=some,o=organization,dc=org',
                    'cn=student,o=other,o=organization,dc=org',
                ],
                'employee' => [
                    'cn=employees,o=some,o=organization,dc=org',
                    'cn=employee,o=other,o=organization,dc=org',
                    'cn=workers,o=any,o=organization,dc=org',
                ],
            ],
        ],
    ],
```

--------------------------------

### Require Authentication

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

Call the requireAuth() method to enforce user authentication for a protected resource.

```php
$as->requireAuth();
```

--------------------------------

### Trigger Cron Jobs via CLI

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/cron/docs/cron.md

Execute cron jobs using the CLI script, specifying the tag with '-t'. It's recommended to run this as the web server user.

```shell
su -s "/bin/sh" \
   -c "nice -n 10 \
       php -d max_execution_time=120 -d memory_limit=600M \
       /var/simplesamlphp/modules/cron/bin/cron.php -t hourly" \
    apache
```

--------------------------------

### Configure ProxyCount for Scoping

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-scoping.md

Set the maximum number of proxying indirections allowed between the initial identity provider and the final authentication provider. A count of zero permits no proxying.

```php
# Set ProxyCount
'ProxyCount' => 2,
```

--------------------------------

### Update Changelog and Commit on Feature Branch

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

Update the changelog file on the feature branch and commit the changes. This is part of the process for preparing a new release.

```bash
% git checkout simplesamlphp-X.Y
% git pull origin simplesamlphp-X.Y
% editor docs/simplesamlphp-changelog.md
## copy updates here to clipboard.
% git add docs/simplesamlphp-changelog.md
% git commit -m "update changelog"
```

--------------------------------

### Extend Base Twig Template

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Twig:-Migrating-templates

All Twig templates should extend the base.twig file, which provides the overall structure and layout.

```twig
{% extends 'base.twig' %}
```

--------------------------------

### Custom Attributes for core:GenerateGroups

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_generategroups.md

Configure the core:GenerateGroups filter to use a specific list of attributes for generating groups. Provide the attribute names as arguments.

```php
'authproc' => [
    50 => [
        'class' => 'core:GenerateGroups',
        'someAttribute',
        'someOtherAttribute',
    ],
],
```

--------------------------------

### Disable Error Display in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Set 'showerrors' to false to hide error descriptions and backtraces from the browser for security.

```php
'showerrors' => false,
```

--------------------------------

### Check Authentication Status

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Checks if the user is currently authenticated with the specified authentication source. Displays a login link if the user is not authenticated.

```php
if (!$auth->isAuthenticated()) {
    \SimpleSAML\Session::getSessionFromRequest()->cleanup();
    /* Show login link. */
    print('<a href="/login">Login</a>');
}
```

--------------------------------

### Create New Major Version Branch

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

When releasing a major version (e.g., X.Y), create a new branch from the current state. This isolates major version development.

```bash
% git checkout -b simplesamlphp-X.Y
```

--------------------------------

### Unconditionally Add SAML Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

This snippet shows the most basic usage of AttributeConditionalAdd to unconditionally add a SAML attribute named 'source' with a value of 'myidp'.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'attributes' => [
                'source' => ['myidp'],
            ],
        ],
    ],
```

--------------------------------

### Using noop() for Variable Translation Tags

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translations-(pre-migration)

Wrap variable contents with a noop function when declaring the variable to ensure translation extractors can identify the string. This is useful when the translation tag's content is dynamic.

```php
# declare the variable
$myValue = $something->noop('some string');

# use it
$something->t($myValue);
```

--------------------------------

### Configure PairwiseID Filter

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/authproc_pairwiseid.md

Configure the saml:PairwiseID filter in your SimpleSAMLphp authentication processing pipeline. Specify the 'identifyingAttribute' and 'scopeAttribute' to define how the pairwise ID is generated. Only the first value of these attributes is considered.

```php
    'authproc' => [
        50 => [
            'class' => 'saml:PairwiseID',
            'identifyingAttribute' => 'uid',
            'scopeAttribute' => 'scope',
        ],
    ],
```

--------------------------------

### Allow default attributes with metadata override

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This snippet allows 'eduPersonTargetedID' and 'eduPersonAffiliation' by default, but permits the SP metadata to override this limitation.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeLimit',
        'default' => true,
        'eduPersonTargetedID', 'eduPersonAffiliation',
    ],
],
```

--------------------------------

### XML Representation of SAML Attribute with Custom NameFormat

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-attributes.md

The XML output for a SAML Attribute where a custom NameFormat ('urn:simplesamlphp:v1') is specified using curly braces in the configuration key.

```xml
<saml:Attribute xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" Name="foo" NameFormat="urn:simplesamlphp:v1">
  <saml:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:string">bar</saml:AttributeValue>
</saml:Attribute>

```

--------------------------------

### Attribute Maps Embedded as Parameters

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributemap.md

Use this snippet to define attribute mappings directly within the authproc configuration. It shows how to map single attributes and create multiple attributes from a single source attribute.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeMap',
            'mail' => 'email',
            'uid' => 'user'
            'cn' => ['name', 'displayName'],
        ],
    ],
```

--------------------------------

### Set Attribute to Blank String

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Replaces a matched pattern in the 'cn' attribute with an empty string. The '%replace' option ensures the entire attribute value is replaced with an empty string.

```php
10 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'cn',
        'pattern' => '/No name/',
        'replacement' => '',
        '%replace',
    ]
```

--------------------------------

### Translate static text with predefined variable

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

Use the `trans` tag for static blocks of text. The `%var%` notation is required for placeholders.

```twig
{% trans %}Hello %name%{% endtrans %}
```

--------------------------------

### Use attributes defined in SP metadata

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This configuration relies solely on attributes defined in the service provider's metadata for attribute filtering.

```php
'authproc' => [
    50 => 'core:AttributeLimit',
],
```

--------------------------------

### Set Default Identity Provider in authsources.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp.md

Configure the 'idp' option within your Service Provider's authentication source to specify which Identity Provider should be contacted by default. If unset, users will see a list of available IdPs.

```php
<?php
$config = [

    'default-sp' => [
        'saml:SP',

        /*
         * The entity ID of the IdP this should SP should contact.
         * Can be NULL/unset, in which case the user will be shown a list of available IdPs.
         */
        'idp' => 'https://example.org/saml-idp',
    ],
];

```

--------------------------------

### Translate with placeholders using trans filter

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

When using placeholders like `%placeholder%`, pass an associative array to the `trans` filter to provide replacement values.

```twig
{{ variable|trans({'%placeholder%': strg_value}) }}
```

--------------------------------

### Retrieve Specific Authentication Data

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Retrieves a specific piece of authentication data for the current session, such as the Identity Provider (IdP) or NameID. Returns NULL if the user is not authenticated.

```php
$idp = $auth->getAuthData('saml:sp:IdP');
$nameID = $auth->getAuthData('saml:sp:NameID')->getValue();
printf('You are %s, logged in from %s', htmlspecialchars($nameID), htmlspecialchars($idp));
```

--------------------------------

### Multiple Attribute Value Mappings

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributevaluemap.md

Assigns multiple affiliations ('student', 'employee', 'both') to the eduPersonAffiliation attribute based on different sets of LDAP group memberships in the 'memberOf' attribute.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeValueMap',
            'sourceattribute' => 'memberOf',
            'targetattribute' => 'eduPersonAffiliation',
            'values' => [
                'student' => [
                    'cn=student,o=some,o=organization,dc=org',
                    'cn=student,o=other,o=organization,dc=org',
                ],
                'employee' => [
                    'cn=employees,o=some,o=organization,dc=org',
                    'cn=employee,o=other,o=organization,dc=org',
                    'cn=workers,o=any,o=organization,dc=org',
                ],
                'both' => [
                    'cn=student,o=some,o=organization,dc=org',
                    'cn=student,o=other,o=organization,dc=org',
                    'cn=employees,o=some,o=organization,dc=org',
                    'cn=employee,o=other,o=organization,dc=org',
                    'cn=workers,o=any,o=organization,dc=org',
                ],
            ],
        ],
    ],
```

--------------------------------

### Twig Migration Comments

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Twig:-Migrating-templates

Use comments to mark code for future refactoring or removal during the migration process. These comments help track necessary changes for future versions.

```shell
# TODO 2.0: rename 'key2' to 'key' and update template
# TODO 2.0: remove 'otherkey'
```

--------------------------------

### Force Specific NameIDFormat

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_php.md

Use this snippet to force a specific NameIDFormat, such as 'transient', when an SP might misbehave or publish an incorrect format. It also allows setting 'AllowCreate'.

```php
90 => [
     'class' => 'core:PHP',
     'code' => '
         $state["saml:NameIDFormat"] = ["Format" => "urn:oasis:names:tc:SAML:2.0:nameid-format:transient", "AllowCreate" => true];
     '
],
```

--------------------------------

### Namespace for Test Classes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/TESTING.md

This is the required namespace definition for test classes located in modules.

```php
namespace SimpleSAML\Test\Utils;
```

--------------------------------

### Allow specific values matching a regex pattern

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This snippet allows specific values for 'eduPersonEntitlement' that match provided regular expressions, including case-insensitive matching.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeLimit',
        'eduPersonEntitlement' => [
            'regex' => true,
            '/^urn:mace:surf/',
            '/^urn:x-IGNORE_Case/i',
        ]
    ],
],
```

--------------------------------

### Generate Logout URL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Generates a static URL to trigger the logout process. The user will be redirected to the specified URL after logout. The default return URL is the current page.

```php
$url = $auth->getLogoutURL();

print('<a href="
```

--------------------------------

### Update SP Metadata for ECP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-ecp-idp.md

When using the ECP profile, your IdP metadata will include an additional ECP SingleSignOnService endpoint. Update the 'saml20-idp-remote' metadata at your SPs to reflect this change.

```php
'SingleSignOnService' => [
    0 => [
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect',
        'Location' => 'https://idp.example.org/simplesaml/module.php/saml/idp/singleSignOnService',
    ],
    1 => [
        'index' => 0,
        'Location' => 'https://didp.example.org/simplesaml/module.php/saml/idp/singleSignOnService',
        'Binding' => 'urn:oasis:names:tc:SAML:2.0:bindings:SOAP',
    ],
],
```

--------------------------------

### NameIDPolicy Configuration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Define the NameID format requested from the IdP in the AuthnRequest.

```php
'NameIDPolicy' => [
            'Format' => \SAML2\Constants::NAMEID_TRANSIENT,
            'AllowCreate' => true
        ],
```

--------------------------------

### FilterScopes with Specific Attributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/filterscopes.md

Configure FilterScopes to evaluate specific attributes like 'mail' and 'eduPersonPrincipalName'.

```php
    'authproc' => [
        90 => [
            'class' => 'saml:FilterScopes',
            'attributes' => [
                'mail',
                'eduPersonPrincipalName',
            ],
        ],
    ],
```

--------------------------------

### Allow specific values for an attribute (case-insensitive)

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This snippet allows specific values for 'eduPersonEntitlement', ignoring case during comparison.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeLimit',
        'eduPersonEntitlement' => [
            'ignoreCase' => true,
            'URN:mace:surf.nl:SURFDRIVE:quota:100'
         ]
    ],
],
```

--------------------------------

### Default Attribute with Conditional Replacement

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Sets a default value for 'myAttribute' using 'core:AttributeAdd' and then conditionally replaces it based on the 'entitlement' attribute using 'core:AttributeAlter' with '%replace'.

```php
10 => [
        'class' => 'core:AttributeAdd',
        'myAttribute' => 'default-value'
    ],
    11 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'entitlement',
        'pattern' => '/faculty/',
        'target' => 'myAttribute',
        '%replace',
    ]
```

--------------------------------

### getLogoutURL

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Generates a URL that can be used to trigger the logout process. The URL can optionally specify a page to return to after logout.

```APIDOC
## getLogoutURL

### Description
Generates a URL that can be used to trigger the logout process. The URL can optionally specify a page to return to after logout.

### Method Signature
`string getLogoutURL(string $returnTo = NULL)`

### Parameters
*   **$returnTo** (string) - Optional. The URL the user should be returned to after logout. Defaults to the current page.

### Return Value
A string representing the logout URL.

### Example
```php
$url = $auth->getLogoutURL();

print('<a href="' . htmlspecialchars($url) . '">Logout</a>');
```

### Note
The URL format is `.../simplesaml/module.php/core/logout/<authentication source>?ReturnTo=<return URL>`.
```

--------------------------------

### Duplicate Attributes Based on Map File

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributemap.md

Configure the filter to duplicate attributes based on multiple map file references. The '%duplicate' keyword indicates that all specified mappings should be applied, potentially creating duplicate attributes.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeMap',
            'name2urn', 'name2oid',
            '%duplicate',
        ],
    ],
```

--------------------------------

### Configure Scoped IdPs for SP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-reference-sp-remote.md

Limit the Identity Providers (IdPs) that a Service Provider (SP) can use when acting as a proxy or bridge. This is achieved by providing a list of allowed IdP entity IDs.

```php
'IDPList' => ['https://idp1.wayf.dk', 'https://idp2.wayf.dk'],
```

--------------------------------

### Do not allow any attributes by default

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This snippet prevents any attributes from being released by default, allowing metadata to override this setting.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeLimit',
        'default' => true,
    ],
],
```

--------------------------------

### Update Changelog on Master Branch

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Release-process

After updating the changelog on the feature branch, switch to the master branch and apply the same updates. This ensures consistency across branches.

```bash
% git checkout master
% editor docs/simplesamlphp-changelog.md
## either cherry-pick the update from above or
```

--------------------------------

### getAttributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Retrieves the attributes of the currently authenticated user. If the user is not authenticated, an empty array is returned. Attributes are returned as an associative array where keys are attribute names and values are arrays of strings.

```APIDOC
## getAttributes

### Description
Retrieves the attributes of the currently authenticated user. If the user is not authenticated, an empty array is returned. Attributes are returned as an associative array where keys are attribute names and values are arrays of strings.

### Method Signature
`array getAttributes()`

### Return Value
An associative array of attributes, e.g., `['uid' => ['testuser'], 'eduPersonAffiliation' => ['student', 'member']]`.

### Example
```php
$attrs = $auth->getAttributes();
if (!isset($attrs['displayName'][0])) {
    throw new Exception('displayName attribute missing.');
}
$name = $attrs['displayName'][0];

print('Hello, ' . htmlspecialchars($name));
```
```

--------------------------------

### Default Attributes for core:GenerateGroups

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_generategroups.md

Use this snippet to enable the core:GenerateGroups filter with its default attribute set. No additional configuration is needed.

```php
'authproc' => [
    50 => [
        'class' => 'core:GenerateGroups',
    ],
],
```

--------------------------------

### Normalize attribute values with default override

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This snippet normalizes 'eduPersonAffiliation' values to a predefined list, preventing custom values from being released. This configuration can be overridden by metadata.

```php
'authproc' => [
    50 => 'core:AttributeLimit',
    'default' => true,
    'eduPersonAffiliation' => [
        'student',
        'staff',
        'member',
        'faculty',
        'employee',
        'affiliate',
    ],
],
```

--------------------------------

### Retrieve User Attributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Retrieves the attributes of the currently authenticated user. If the user is not authenticated, an empty array is returned. Attributes are returned as an associative array.

```php
$attrs = $auth->getAttributes();
if (!isset($attrs['displayName'][0])) {
    throw new Exception('displayName attribute missing.');
}
$name = $attrs['displayName'][0];

print('Hello, ' . htmlspecialchars($name));
```

--------------------------------

### Add Attributes if Any Attribute Value Matches (attrValueIsAny)

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Adds new attributes if any of the specified attributes contain at least one of the listed values. Useful for broad matching criteria.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrValueIsAny' => [
                    'departmentName' => ['Physics', Chemistry],
                    'managementRole' => ['Vice Chancellor'],
                ],
            ],
            'attributes' => [
                'newSystemPilotUser' => ['true'],
            ],
        ],
    ],
```

--------------------------------

### Set Crontab Editor

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/cron/docs/cron.md

Set the EDITOR environment variable to specify your preferred command-line editor for crontab.

```shell
[user@simplesamlphp config]# export EDITOR=emacs
```

--------------------------------

### SP Limiting ACS Bindings

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/sp.md

Configure an SP to support only specific AssertionConsumerService endpoint bindings, such as HTTP-POST.

```php
'example-acs-limit' => [
    'saml:SP',
    'entityID' => 'https://myapp.example.org',
    'acs.Bindings' => [
        'urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST',
    ],
],
```

--------------------------------

### Set Timezone in config.php

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-install.md

Configure the server's timezone for accurate timestamping and date-related operations.

```php
'timezone' => 'Europe/Oslo',
```

--------------------------------

### isAuthenticated

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Checks if the user is currently authenticated with the configured authentication source. Returns `TRUE` if authenticated, `FALSE` otherwise.

```APIDOC
## isAuthenticated

### Description
Check whether the user is authenticated with this authentication source.

### Returns
* **bool** - `TRUE` if the user is authenticated, `FALSE` if not.

### Example
```php
if (!$auth->isAuthenticated()) {
    \SimpleSAML\Session::getSessionFromRequest()->cleanup();
    /* Show login link. */
    print('<a href="/login">Login</a>');
}
```
```

--------------------------------

### FilterScopes with OID Attribute Format

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/filterscopes.md

Configure FilterScopes to evaluate attributes using their OID format, such as 'urn:oid:0.9.2342.19200300.100.1.3' and 'urn:oid:1.3.6.1.4.1.5923.1.1.1.6'.

```php
    'authproc' => [
        90 => [
            'class' => 'saml:FilterScopes',
            'attributes' => [
                'urn:oid:0.9.2342.19200300.100.1.3',
                'urn:oid:1.3.6.1.4.1.5923.1.1.1.6',
            ],
        ],
    ],
```

--------------------------------

### Namespacing array for translations in PHP

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

Define an array with namespaced keys in PHP to manage translation replacements and avoid conflicts. This array can then be referenced in the Twig template.

```php
$this->data['login_stats'] = array('succeeded': 43214213, 'failed': 32112};
```

--------------------------------

### Generate SSHA Password Hash in PHP

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-customauth.md

PHP code snippet to generate a base64 encoded SSHA password hash with a random salt.

```php
$password = 'secret';
$numSalt = 8; /* Number of bytes with salt. */
$salt = '';
for ($i = 0; $i < $numSalt; $i++) {
    $salt .= chr(mt_rand(0, 255));
}
$digest = sha1($password . $salt, true);
$password_hash = base64_encode($digest . $salt);

```

--------------------------------

### Configure Memcache Session Expiration

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-maintenance.md

Sets the duration for which session data is retained in Memcache. This value should be larger than session.duration to prevent premature data deletion.

```php
'memcache_store.expires' =>  36 * (60*60), // 36 hours.
```

--------------------------------

### Add Attributes if All Attribute Values Match Regex (attrValueIsRegexAll)

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Adds new attributes only if all specified attributes have all their values matching any of the provided regular expressions. Useful for ensuring all values conform to specific patterns.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrValueIsRegexAll' => [
                    'email' => ['/@staff.example.edu$/', '/@student.example.edu$/'],
                ],
            ],
            'attributes' => [
                'internalUser' => ['true'],
            ],
        ],
    ],
```

--------------------------------

### Merge Master into Current Release Branch

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-developer-information.md

Merges the 'master' branch into the 'simplesamlphp-2.5' branch, typically done after commits intended for v2.5.* have been added to master.

```bash
# After some commits have been added to master intended for v2.5.*
git checkout simplesamlphp-2.5
git merge master
```

--------------------------------

### XML Representation of a SAML Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-metadata-extensions-attributes.md

The resulting XML structure for a SAML Attribute with multiple values, generated from the 'urn:simplesamlphp:v1:simplesamlphp' configuration.

```xml
<saml:Attribute xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion" Name="urn:simplesamlphp:v1:simplesamlphp" NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri">
  <saml:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:string">is</saml:AttributeValue>
  <saml:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:string">really</saml:AttributeValue>
  <saml:AttributeValue xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xsi:type="xs:string">cool</saml:AttributeValue>
</saml:Attribute>

```

--------------------------------

### Merge Master into Next Release Branch

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-developer-information.md

Merges the 'master' branch into the 'simplesamlphp-2.6' branch. This is done periodically to bring changes from master into the next release branch, potentially requiring conflict resolution.

```bash
# After some commits have been added to master and "next-release-branch" separately...
git checkout simplesamlphp-2.6
git merge master
# This might have conflicts, but those should be easy to resolve, since we know what did we do for next release ...
```

--------------------------------

### Configure Session Cookie Domain in PHP.ini

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/State-Information-Lost

Alternatively, configure the session cookie domain directly in the PHP configuration file. This setting affects all PHP sessions on the server.

```ini
session.cookie_domain = ".example.org"
```

--------------------------------

### Load Exception State and Retrieve Exception

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-errorhandling.md

Retrieves the state array containing an exception from the request parameters and extracts the exception object. This is used when an exception has been previously saved and the user is redirected back to the application.

```php
if (array_key_exists("__Exception_ID__", $_REQUEST)) {
    $state = \SimpleSAML\Auth\State::loadExceptionState();
    $exception = $state["__Exception_Data__"];

    /* Process exception. */
}
```

--------------------------------

### Add Mail Attribute based on UID

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_php.md

This snippet demonstrates how to add a 'mail' attribute by deriving it from the 'uid' attribute. It includes error handling for a missing 'uid'.

```php
10 => [
    'class' => 'core:PHP',
    'code' => '
        if (empty($attributes["uid"])) {
            throw new Exception("Missing uid attribute.");
        }

        $uid = $attributes["uid"][0];
        $mail = $uid . "@example.net";
        $attributes["mail"] = [$mail];
    ',
],
```

--------------------------------

### Normalize eduPersonPrimaryAffiliation

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Normalizes the 'eduPersonPrimaryAffiliation' attribute by replacing a specific pattern with a standardized value. The '%replace' option ensures the entire attribute value is replaced if a match is found.

```php
10 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'eduPersonPrimaryAffiliation',
        'pattern' => '/Student in school/',
        'replacement' => 'student',
        '%replace',
    ]
```

--------------------------------

### Add Multi-Valued Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeadd.md

Adds a multi-valued attribute to the user. Values are merged if the attribute already exists.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeAdd',
            'groups' => ['users', 'members'],
        ],
    ],
```

--------------------------------

### Implement GeoIP Country Session Check

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-advancedfeatures.md

A custom session check function that verifies if the user's current GeoIP country matches the country they authenticated from. It requires the 'geoip' PHP module.

```php
public static function checkSession(\SimpleSAML\Session $session, bool $init = false)
{
    $data_type = 'example:check_session';
    $data_key = 'remote_addr';

    $remote_addr = strval($_SERVER['REMOTE_ADDR']);

    if ($init) {
        $session->setData(
            $data_type,
            $data_key,
            $remote_addr,
            \SimpleSAML\Session::DATA_TIMEOUT_SESSION_END
        );
        return;
    }

    if (!function_exists('geoip_country_code_by_name')) {
        \SimpleSAML\Logger::warning('geoip php module required.');
        return true;
    }

    $stored_remote_addr = $session->getData($data_type, $data_key);
    if ($stored_remote_addr === null) {
        \SimpleSAML\Logger::warning('Stored data not found.');
        return false;
    }

    $country_a = geoip_country_code_by_name($remote_addr);
    $country_b = geoip_country_code_by_name($stored_remote_addr);

    if ($country_a === $country_b) {
        if ($stored_remote_addr !== $remote_addr) {
            $session->setData(
                $data_type,
                $data_key,
                $remote_addr,
                \SimpleSAML\Session::DATA_TIMEOUT_SESSION_END
            );
        }

        return true;
    }

    return false;
}
```

--------------------------------

### Dump Attributes Matching Regex with core:AttributeDump

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributedump.md

This configuration outputs attributes whose names end with the letter 'n' (e.g., 'fn', 'sn', 'cn') to the logs. Use this to capture attributes based on a pattern.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeDump',
        'attributesRegex' => ['/n$/'],
    ],
]
```

--------------------------------

### Add Single-Valued Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeadd.md

Adds a single-valued attribute to the user. If the attribute already exists, its values will be merged.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeAdd',
            'source' => ['myidp'],
        ],
    ],
```

--------------------------------

### Conditional Add: Attribute Exists Regex Any

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Adds the 'isCustomer' attribute if any existing attribute name matches '/^cust/' or '/PhoneNumber$/'.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrExistsRegexAny' => [
                    '/^cust/',
                    '/PhoneNumber$/',
                ],
            ],
            'attributes' => [
                'isCustomer' => ['true'],
            ],
        ],
    ],
```

--------------------------------

### Create Random Number Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_php.md

This snippet shows how to add a new attribute named 'random' to the user's attributes, populated with a randomly generated number.

```php
10 => [
    'class' => 'core:PHP',
    'code' => '
        $attributes["random"] = [
            (string)rand(),
        ];
    ',
],
```

--------------------------------

### getAuthData

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-sp-api.md

Retrieves specific authentication data for the current session. Returns NULL if the user is not authenticated. The available data depends on the authentication module used.

```APIDOC
## getAuthData

### Description
Retrieves specific authentication data for the current session. Returns NULL if the user is not authenticated. The available data depends on the authentication module used.

### Method Signature
`mixed getAuthData(string $name)`

### Parameters
*   **$name** (string) - The name of the authentication data to retrieve (e.g., 'saml:sp:IdP').

### Return Value
Mixed data, or NULL if the user is not authenticated.

### Example
```php
$idp = $auth->getAuthData('saml:sp:IdP');
$nameID = $auth->getAuthData('saml:sp:NameID')->getValue();
printf('You are %s, logged in from %s', htmlspecialchars($nameID), htmlspecialchars($idp));
```
```

--------------------------------

### Add Attributes if All Attribute Values Match (attrValueIsAll)

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Adds new attributes only if all specified attributes contain all of the listed values. Useful for strict, multi-factor attribute matching.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrValueIsAll' => [
                    'departmentName' => ['Physics'],
                    'managementRole' => ['Dean'],
                ],
            ],
            'attributes' => [
                'newSystemPilotUser' => ['true'],
            ],
        ],
    ],
```

--------------------------------

### Map LDAP Group Membership to Student Affiliation

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributevaluemap.md

Adds 'student' to the eduPersonAffiliation attribute if the memberOf attribute contains specific LDAP group DNs. The source attribute 'memberOf' is removed by default.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeValueMap',
            'sourceattribute' => 'memberOf',
            'targetattribute' => 'eduPersonAffiliation',
            'values' => [
                'student' => [
                    'cn=student,o=some,o=organization,dc=org',
                    'cn=student,o=other,o=organization,dc=org',
                ],
            ],
        ],
    ],
```

--------------------------------

### Copy Single Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributecopy.md

Copies a single attribute from its source name to a single target name. Use this when you need to rename an attribute or make it available under a different identifier.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeCopy',
        'uid' => 'username',
    ],
],
```

--------------------------------

### Implement User Blocking Session Check

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-advancedfeatures.md

A custom session check function that logs out and prevents a specific user ('badboy@localhost.localdomain') from logging in by checking their 'uid' attribute.

```php
declare(strict_types=1);

namespace SimpleSAML;

class CustomCode
{
    /**
     * The session.check_function can be used to throw away a session object
     * during normal processing. If we throw it away by returning `false` then
     * the user will be forced to create a new session.
     * 
     * There are two call modes: during session init which can not fail and 
     * during testing. When testing returning false will cause the session to 
     * be discarded.
     *
     * @param \SimpleSAML\Session $session The session to approve/reject
     * @param bool $init true if called during session init.
     */
    public static function checkSession(\SimpleSAML\Session $session, bool $init = false): bool
    {
        $authority = "default-sp";
        
        if ($init) {
            // init can not fail
            // return value is ignored
            return true;
        }
        
        $ad = $session->getAuthData($authority, "Attributes");
        if (empty($ad)) {
            return true;
        }
        $uid = $ad["uid"];
        
        if (in_array("badboy@localhost.localdomain", $uid)) {
            // drop the session
            return false;
        }

        // normal functionality
        return true;
    }
};
```

--------------------------------

### Translate a string using the trans filter

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

Apply the `trans` filter to a string literal to translate it.

```twig
{{ 'Untranslated string'|trans }}
```

--------------------------------

### Namespacing array for translations in template

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

To prevent naming conflicts when multiple replacements are needed, namespace the array of values in the context. This allows for cleaner access in the template.

```twig
{% trans %}There were {{ login_stats.succeeded }} logins and {{ login_stats.failed }} failures.{% endtrans %}
```

--------------------------------

### Set Attribute to NULL Value

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Replaces a matched pattern in the 'telephone' attribute with a NULL value. The '%replace' option ensures the entire attribute value is replaced with NULL.

```php
10 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'telephone',
        'pattern' => '/NULL/',
        'replacement' => null,
        '%replace',
    ]
```

--------------------------------

### Replace Existing Attribute Based on Conditions

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

This snippet replaces an existing attribute ('uid') if specific conditions are met. The '%replace' option ensures the attribute is overwritten with the new value.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            '%replace',
            'conditions' => [
                'attrValueIsAll' => [
                    'userType' => ['Customer'],
                    'onStopSupply' => ['true'],
                ],
            ],
            'attributes' => [
                'uid' => ['guest'],
            ],
        ],
    ],
```

--------------------------------

### Update Mail Domain with Regex

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Updates the domain of the 'mail' attribute to a new domain using a regular expression. This is useful when the old domain is not explicitly known.

```php
10 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'mail',
        'pattern' => '/(?:[A-Za-z0-9-]+\.)+[A-Za-z]{2,6}$/',
        'replacement' => 'newdomain.com',
    ]
```

--------------------------------

### Conditional Add: Attribute Exists Regex All

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Adds the 'isCustomer' attribute if at least one existing attribute name matches '/^email/' AND at least one matches '/^member/'.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrExistsRegexAll' => [
                    '/^email/',
                    '/^member/',
                ],
            ],
            'attributes' => [
                'isCustomer' => ['true'],
            ],
        ],
    ],
```

--------------------------------

### Add Attributes if Any Attribute Value Matches Regex (attrValueIsRegexAny)

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Adds new attributes if any of the specified attributes contain a value matching any of the provided regular expressions. Useful for pattern-based matching.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrValueIsRegexAny' => [
                    'qualifications' => ['/^Certfied/', '/Assessor$/'],
                ],
            ],
            'attributes' => [
                'qualifiedTradie' => ['true'],
            ],
        ],
    ],
```

--------------------------------

### Copy Single Attribute to Multiple Targets

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributecopy.md

Copies a single attribute from its source name to multiple target names simultaneously. This is useful when an attribute needs to be represented by several different identifiers or formats.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeCopy',
        'uid' => ['username', 'urn:mace:dir:attribute-def:uid'],
    ],
],
```

--------------------------------

### Define Content Block in Twig

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Twig:-Migrating-templates

Content specific to a template is placed within a 'content' block, which is defined by extending the base template.

```twig
{% block content %}
  ...your code...
{% endblock %}
```

--------------------------------

### Conditional Add: Attribute Exists All

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Adds the 'isCompanyUser' attribute only if both 'customerId' and 'companyName' attributes exist.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrExistsAll' => [
                    'customerId',
                    'companyName',
                ],
            ],
            'attributes' => [
                'isCompanyUser' => ['true'],
            ],
        ],
    ],
```

--------------------------------

### Edit Crontab

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/cron/docs/cron.md

Edit the system's crontab file to add or modify scheduled cron jobs.

```shell
[user@simplesamlphp config]# crontab -e
```

--------------------------------

### Replace Existing Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeadd.md

Replaces an existing attribute with new values using the %replace option. This prevents merging.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeAdd',
            '%replace',
            'uid' => ['guest'],
        ],
    ],
```

--------------------------------

### Translate Entity Name from Metadata

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/List-of-tasks

Directly translate an entity's name from metadata using the current language. This avoids the translation infrastructure for external translations.

```php
$translated_name = $spname[$template->getLanguage()];
$template->data['SPName'] = $translated_name;
```

--------------------------------

### Conditional Add: Attribute Exists Any

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributeconditionaladd.md

Adds the 'isExternalUser' attribute if either 'customerId' or 'supplierId' attributes already exist.

```php
'authproc' => [
        50 => [
            'class' => 'core:AttributeConditionalAdd',
            'conditions' => [
                'attrExistsAny' => [
                    'customerId',
                    'supplierId',
                ],
            ],
            'attributes' => [
                'isExternalUser' => ['true'],
            ],
        ],
    ],
```

--------------------------------

### Limit to specific attributes

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This snippet limits the attributes released to only 'cn' and 'mail'.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeLimit',
        'cn', 'mail'
    ],
],
```

--------------------------------

### Set Page Title in Twig

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Twig:-Migrating-templates

Set the page title using the 'trans' filter for translation. This is typically done at the beginning of a Twig template.

```twig
{% set pagetitle = 'TITLE_ID'|trans %}
```

--------------------------------

### Extract Email Domain to New Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Extracts the domain part of an email address from the 'mail' attribute and places it into a new 'domain' attribute. The '%replace' option ensures only the matched domain is used.

```php
10 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'mail',
        'pattern' => '/(?:[A-Za-z0-9-]+\.)+[A-Za-z]{2,6}$/',
        'target' => 'domain',
        '%replace',
    ]
```

--------------------------------

### Retrieve RequesterID from State

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-scoping.md

Access the RequesterID elements from the state array, which identifies the original requester and any proxying identity providers. This is available via the authenticate method on an authentication source.

```php
$requesterIDs = $state['saml:RequesterID'];
```

--------------------------------

### Translate a variable using the trans filter

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

Use the `trans` filter to translate the content of a variable.

```twig
{{ variable|trans }}
```

--------------------------------

### Enforce Single-Valued Attributes with Error on Multi-Value

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_cardinalitysingle.md

Use this snippet to abort with an error if any attribute defined as single-valued in eduPerson or SCHAC schemas has more than one value. It configures the 'singleValued' parameter with a comprehensive list of attributes.

```php
'authproc' => [
        50 => [
            'class' => 'core:CardinalitySingle',
            'singleValued' => [
                /* from eduPerson (internet2-mace-dir-eduperson-201602) */
                'eduPersonOrgDN', 'eduPersonPrimaryAffiliation', 'eduPersonPrimaryOrgUnitDN',
                'eduPersonPrincipalName', 'eduPersonUniqueId',
                /* from inetOrgPerson (RFC2798), referenced by internet2-mace-dir-eduperson-201602 */
                'displayName', 'preferredLanguage',
                /* from SCHAC-IAD Version 1.3.0 */
                'schacMotherTongue', 'schacGender', 'schacDateOfBirth', 'schacPlaceOfBirth',
                'schacPersonalTitle', 'schacHomeOrganization', 'schacHomeOrganizationType',
                'schacExpiryDate',
            ],
        ],
    ],
```

--------------------------------

### Generate TargetedID with Custom Attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_targetedid.md

Use this snippet to configure the core:TargetedID filter to use a custom attribute, such as 'eduPersonPrincipalName', as the unique user identifier.

```php
'authproc' => [
    50 => [
        'class' => 'core:TargetedID',
        'identifyingAttribute' => 'eduPersonPrincipalName'
    ],
],
```

--------------------------------

### Translate an array using translateFromArray filter

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

Utilize the `translateFromArray` filter for translating array contents.

```twig
{{ array_var|translateFromArray }}
```

--------------------------------

### Simplifying Concatenated Translation Tags

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translations-(pre-migration)

Avoid concatenating strings directly within the t() function call. Instead, create a mapping from error codes to translatable strings using noop() and then use the mapped string.

```php
# Somewhere
$errorCodeStrings = array(
   '404' => noop('{errors:descr_404}'),
   '500' => noop('{errors:descr_500}')
);

# Later in some place that has access to $errorCodeStrings
$something->t($errorCodeStrings[$this->data['errorcode']]);
```

--------------------------------

### Reference Custom CSS in Twig Template

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/docs/simplesamlphp-theming.md

Include a custom CSS stylesheet in your theme by referencing it using the `asset()` function within a Twig template's `preload` block. The `asset()` function correctly generates the URL for resources within your module's public assets.

```twig
{% block preload %}
<link rel="stylesheet" href="{{ asset('style.css', 'mymodule') }}">
{% endblock %}
```

--------------------------------

### Translate static text with inline variable

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Migrating-translation-in-Twig

Set translation variables directly within the `trans` tag when translating static text.

```twig
{% trans with {'%name%': 'Marko'}%}Hello %name%{% endtrans %}
```

--------------------------------

### Extract Only NameID Value

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/nameidattribute.md

Configure the saml:NameIDAttribute filter to extract only the value of the NameID. Use the 'format' option set to '%V' to achieve this.

```php
'default-sp' => [
        'saml:SP',
        'authproc' => [
            20 => [
                'class' => 'saml:NameIDAttribute',
                'format' => '%V',
            ],
        ],
    ],
```

--------------------------------

### Change Mail Domain

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Replaces an old domain with a new one in the 'mail' attribute when both are known. This snippet is useful for direct domain updates.

```php
10 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'mail',
        'pattern' => '/olddomain.com/',
        'replacement' => 'newdomain.com',
    ]
```

--------------------------------

### Custom Attribute Name for NameIDAttribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/saml/docs/nameidattribute.md

Configure the saml:NameIDAttribute filter to store the extracted NameID in a custom attribute. Specify the desired attribute name using the 'attribute' option.

```php
'default-sp' => [
        'saml:SP',
        'authproc' => [
            20 => [
                'class' => 'saml:NameIDAttribute',
                'attribute' => 'someattributename',
            ],
        ],
    ],
```

--------------------------------

### Allow specific values for an attribute

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributelimit.md

This snippet restricts the 'eduPersonEntitlement' attribute to only release a specific URN value.

```php
'authproc' => [
    50 => [
        'class' => 'core:AttributeLimit',
        'eduPersonEntitlement' => ['urn:mace:surf.nl:surfdrive:quota:100']
    ],
],
```

--------------------------------

### Disabling header_register_callback in php.ini

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Segmentation-faults-in-Apache

To prevent segmentation faults, you can disable the `header_register_callback` function by adding it to the `disable_functions` directive in your `php.ini` file. Ensure functions are comma-separated.

```ini
disable_functions = header_register_callback
```

--------------------------------

### Pass Page Title from PHP

Source: https://github.com/simplesamlphp/simplesamlphp/wiki/Twig:-Migrating-templates

Alternatively, the page title can be passed from the PHP page using the $this->t() method for translation.

```php
$t->data['pagetitle'] = $this->t('TITLE_ID');
```

--------------------------------

### Remove Private Values from eduPersonEntitlement

Source: https://github.com/simplesamlphp/simplesamlphp/blob/master/modules/core/docs/authproc_attributealter.md

Removes specific internal or private values from the 'eduPersonEntitlement' attribute using a pattern match and the '%remove' option. This helps in sanitizing attribute data.

```php
10 => [
        'class' => 'core:AttributeAlter',
        'subject' => 'eduPersonEntitlement',
        'pattern' => '/ldap-admin/',
        '%remove',
    ]
```

=== COMPLETE CONTENT === This response contains all available snippets from this library. No additional content exists. Do not make further requests.