# Drupal7-SimpleSAML-WSO2
Configuración Drupal7 SimpleSAMLPHP y WSO2.

vim /var/simplesamlphp/config/config.php

Cambiar a:
```
'auth.adminpassword' => 'MISUPER_PASSWORD',
```

Cambiar a:
```
// tr -c -d '0123456789abcdefghijklmnopqrstuvwxyz' </dev/urandom | dd bs=32 count=1 2>/dev/null;echo
'secretsalt' => 'NUMALEATEATORIO_COMANDO ANTERIOR',
```

Cambiar a:
```
'technicalcontact_name' => 'Jorge Useche',
'technicalcontact_email' => 'jorgenator2@yahoo.es',
```

vim /var/simplesamlphp/config/authsources.php

Agregar coherentemente:
```
    'wso2-sp' => array(

        'saml:SP',

        // The entity ID of this SP. 

        // Can be NULL/unset, in which case an entity ID is generated based on the metadata URL. 

        'entityID' => 'simplesaml',

        // The entity ID of the IdP this should SP should contact. 

        // Can be NULL/unset, in which case the user will be shown a list of available IdPs. 

        'idp' => 'https://devops.red:9443/samlsso',

        // The URL to the discovery service. 

        // Can be NULL/unset, in which case a builtin discovery service will be used. 

        'discoURL' => NULL,

    ),
```


